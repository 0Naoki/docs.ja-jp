---
title: ワークフロー サービスから OperationContext へのアクセス
ms.date: 03/30/2017
ms.assetid: b1dafe55-a20e-4db0-9ac8-90c315883cdd
ms.openlocfilehash: 15dd817dddbe3272b188f6b74697f8c5839d498b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111317"
---
# <a name="accessing-operationcontext-from-a-workflow-service"></a>ワークフロー サービスから OperationContext へのアクセス
ワークフロー サービス内の <xref:System.ServiceModel.OperationContext> にアクセスするには、カスタム実行プロパティに <xref:System.ServiceModel.Activities.IReceiveMessageCallback> インターフェイスを実装する必要があります。 これには、<xref:System.ServiceModel.Activities.IReceiveMessageCallback.OnReceiveMessage(System.ServiceModel.OperationContext,System.Activities.ExecutionProperties)> への参照が渡される <xref:System.ServiceModel.OperationContext> メソッドをオーバーライドします。 このトピックでは、カスタム ヘッダーを取得するためにこの実行プロパティを実装する方法に加え、実行時にこのプロパティを <xref:System.ServiceModel.Activities.Receive> に提示するカスタム アクティビティの実装方法を順に説明します。  このカスタム アクティビティが行う動作は、<xref:System.Activities.Statements.Sequence> アクティビティと同じですが、<xref:System.ServiceModel.Activities.Receive> がその内部に配置されるのに対し、<xref:System.ServiceModel.Activities.IReceiveMessageCallback> は呼び出されて <xref:System.ServiceModel.OperationContext> 情報を取得します。  このトピックでは、クライアント側 <xref:System.ServiceModel.OperationContext> にアクセスして、<xref:System.ServiceModel.Activities.ISendMessageCallback> インターフェイス経由で送信ヘッダーを追加する方法も説明します。  
  
### <a name="implement-the-service-side-ireceivemessagecallback"></a>サービス側の IReceiveMessageCallback の実装  
  
1.  空の [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] ソリューションを作成します。  
  
2.  `Service` という新しいコンソール アプリケーションをソリューションに追加します。  
  
3.  次のアセンブリへの参照を追加します。  
  
    1.  System.Runtime.Serialization  
  
    2.  System.ServiceModel  
  
    3.  System.ServiceModel.Activities  
  
4.  次の例に示すように、`ReceiveInstanceIdCallback` という新しいクラスを追加し、<xref:System.ServiceModel.Activities.IReceiveMessageCallback> を実装します。  
  
    ```csharp  
    class ReceiveInstanceIdCallback : IReceiveMessageCallback  
    {  
          public const string HeaderName = "InstanceIdHeader";  
          public const string HeaderNS = "http://Microsoft.Samples.AccessingOperationContext";  
  
         public void OnReceiveMessage(System.ServiceModel.OperationContext operationContext, System.Activities.ExecutionProperties activityExecutionProperties)  
          {              
                try  
                {  
                    Guid instanceId = operationContext.IncomingMessageHeaders.GetHeader<Guid>(HeaderName, HeaderNS);  
                    Console.WriteLine("Received a message from a workflow with instanceId = {0}", instanceId);  
                }  
                catch (MessageHeaderException)  
                {  
                    Console.WriteLine("This message must not be from a workflow.");  
                }  
            }  
    }  
    ```  
  
     このコードでは、メソッドに渡される <xref:System.ServiceModel.OperationContext> を使用して、着信メッセージのヘッダーにアクセスします。  
  
### <a name="implement-a-service-side-native-activity-to-add-the-ireceivemessagecallback-implementation-to-the-nativeactivitycontext"></a>IReceiveMessageCallback 実装を NativeActivityContext に追加するためのサービス側のネイティブ アクティビティの実装  
  
1.  <xref:System.Activities.NativeActivity> から派生した `ReceiveInstanceIdScope` という新しいクラスを追加します。  
  
2.  子アクティビティ、変数、現在のアクティビティ インデックス、および <xref:System.Activities.CompletionCallback> コールバックを追跡するためのローカル変数を追加します。  
  
    ```  
    public sealed class ReceiveInstanceIdScope : NativeActivity  
        {  
            Collection<Activity> children;  
            Collection<Variable> variables;  
            Variable<int> currentIndex;  
            CompletionCallback onChildComplete;  
    }  
    ```  
  
3.  コンストラクターを実装します。  
  
    ```  
    public ReceiveInstanceIdScope()  
                : base()  
            {  
                this.children = new Collection<Activity>();  
                this.variables = new Collection<Variable>();  
                this.currentIndex = new Variable<int>();  
            }  
    }  
    ```  
  
4.  `Activities` プロパティと `Variables` プロパティを実装します。  
  
    ```  
    public Collection<Activity> Activities  
    {  
         get { return this.children; }  
    }  
  
    public Collection<Variable> Variables  
    {  
        get { return this.variables; }  
    }  
    ```  
  
5.  <xref:System.Activities.NativeActivity.CacheMetadata%2A> をオーバーライドします。  
  
    ```  
    protected override void CacheMetadata(NativeActivityMetadata metadata)  
    {  
        //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
        base.CacheMetadata(metadata);  
        //add the private implementation variable: currentIndex   
        metadata.AddImplementationVariable(this.currentIndex);  
    }  
    ```  
  
6.  <xref:System.Activities.NativeActivity.Execute%2A> をオーバーライドします。  
  
    ```  
    protected override void Execute(  
                NativeActivityContext context)  
            {  
                context.Properties.Add("ReceiveInstanceIdCallback", new ReceiveInstanceIdCallback());  
                InternalExecute(context, null);  
            }  
  
            void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
            {  
                //grab the index of the current Activity  
                int currentActivityIndex = this.currentIndex.Get(context);  
                if (currentActivityIndex == Activities.Count)  
                {  
                    //if the currentActivityIndex is equal to the count of MySequence's Activities  
                    //MySequence is complete  
                    return;  
                }  
  
                if (this.onChildComplete == null)  
                {  
                    //on completion of the current child, have the runtime call back on this method  
                    this.onChildComplete = new CompletionCallback(InternalExecute);  
                }  
  
                //grab the next Activity in MySequence.Activities and schedule it  
                Activity nextChild = Activities[currentActivityIndex];  
                context.ScheduleActivity(nextChild, this.onChildComplete);  
  
                //increment the currentIndex  
                this.currentIndex.Set(context, ++currentActivityIndex);  
            }  
    ```  
  
### <a name="implement-the-workflow-service"></a>ワークフロー サービスの実装  
  
1.  既存の開く`Program`クラス。  
  
2.  次の定数を定義します。  
  
    ```  
    class Program  
    {  
       const string addr = "http://localhost:8080/Service";  
       static XName contract = XName.Get("IService", "http://tempuri.org");  
    }  
    ```  
  
3.  ワークフロー サービスを作成する `GetWorkflowService` という静的メソッドを追加します。  
  
    ```  
    static Activity GetServiceWorkflow()  
            {  
                Variable<string> echoString = new Variable<string>();  
  
                Receive echoRequest = new Receive  
                {  
                    CanCreateInstance = true,  
                    ServiceContractName = contract,  
                    OperationName = "Echo",  
                    Content = new ReceiveParametersContent()  
                    {  
                        Parameters = { { "echoString", new OutArgument<string>(echoString) } }  
                    }  
                };  
  
                return new ReceiveInstanceIdScope  
                {  
                    Variables = { echoString },  
                    Activities =  
                    {  
                        echoRequest,  
                        new WriteLine { Text = new InArgument<string>( (e) => "Received: " + echoString.Get(e) ) },  
                        new SendReply  
                        {  
                            Request = echoRequest,  
                            Content = new SendParametersContent()  
                            {  
                                Parameters = { { "result", new InArgument<string>(echoString) } }   
                            }  
                        }  
                    }  
                };  
            }  
    ```  
  
4.  既存の `Main` メソッドで、ワークフロー サービスをホストします。  
  
    ```  
    static void Main(string[] args)  
            {  
                string addr = "http://localhost:8080/Service";  
  
                using (WorkflowServiceHost host = new WorkflowServiceHost(GetServiceWorkflow()))  
                {  
                    host.AddServiceEndpoint(contract, new BasicHttpBinding(), addr);  
  
                    host.Open();  
                    Console.WriteLine("Service waiting at: " + addr);  
                    Console.WriteLine("Press [ENTER] to exit");  
                    Console.ReadLine();  
                    host.Close();  
                }  
            }  
    ```  
  
### <a name="implement-the-client-side-isendmessagecallback"></a>クライアント側の ISendMessageCallback の実装  
  
1.  `Service` という新しいコンソール アプリケーションをソリューションに追加します。  
  
2.  次のアセンブリへの参照を追加します。  
  
    1.  System.Runtime.Serialization  
  
    2.  System.ServiceModel  
  
    3.  System.ServiceModel.Activities  
  
3.  次の例に示すように、`SendInstanceIdCallback` という新しいクラスを追加し、<xref:System.ServiceModel.Activities.ISendMessageCallback> を実装します。  
  
    ```csharp  
    class SendInstanceIdCallback : ISendMessageCallback  
        {  
            public const string HeaderName = "InstanceIdHeader";  
            public const string HeaderNS = "http://Microsoft.Samples.AccessingOperationContext";  
  
            public Guid InstanceId { get; set; }  
  
            public void OnSendMessage(System.ServiceModel.OperationContext operationContext)  
            {  
                operationContext.OutgoingMessageHeaders.Add(MessageHeader.CreateHeader(HeaderName, HeaderNS, this.InstanceId));  
            }  
        }  
    ```  
  
     このコードでは、メソッドに渡される <xref:System.ServiceModel.OperationContext> を使用して、着信メッセージにカスタム ヘッダーを追加します。  
  
### <a name="implement-a-client-side-native-activity-to-add-the-client-side-isendmessagecallback-implementation-to-the-nativeactivitycontext"></a>クライアント側の ISendMessageCallback 実装を NativeActivityContext に追加するためのクライアント側のネイティブ アクティビティの実装  
  
1.  <xref:System.Activities.NativeActivity> から派生した `SendInstanceIdScope` という新しいクラスを追加します。  
  
2.  子アクティビティ、変数、現在のアクティビティ インデックス、および <xref:System.Activities.CompletionCallback> コールバックを追跡するためのローカル変数を追加します。  
  
    ```  
    public sealed class SendInstanceIdScope : NativeActivity  
        {  
            Collection<Activity> children;  
            Collection<Variable> variables;  
            Variable<int> currentIndex;  
            CompletionCallback onChildComplete;  
    }  
    ```  
  
3.  コンストラクターを実装します。  
  
    ```  
    public SendInstanceIdScope()  
                : base()  
            {  
                this.children = new Collection<Activity>();  
                this.variables = new Collection<Variable>();  
                this.currentIndex = new Variable<int>();  
            }  
    ```  
  
4.  `Activities` プロパティと `Variables` プロパティを実装します。  
  
    ```  
    public Collection<Activity> Activities  
    {  
         get { return this.children; }  
    }  
  
    public Collection<Variable> Variables  
    {  
        get { return this.variables; }  
    }  
    ```  
  
5.  <xref:System.Activities.NativeActivity.CacheMetadata%2A> をオーバーライドします。  
  
    ```  
    protected override void CacheMetadata(NativeActivityMetadata metadata)  
    {  
        //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
        base.CacheMetadata(metadata);  
        //add the private implementation variable: currentIndex   
        metadata.AddImplementationVariable(this.currentIndex);  
    }  
    ```  
  
6.  <xref:System.Activities.NativeActivity.Execute%2A> をオーバーライドします。  
  
    ```  
    protected override void Execute(  
                NativeActivityContext context)  
            {  
                context.Properties.Add("SendInstanceIdCallback", new SendInstanceIdCallback() { InstanceId = context.WorkflowInstanceId });  
                InternalExecute(context, null);  
            }  
  
            void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
            {  
                //grab the index of the current Activity  
                int currentActivityIndex = this.currentIndex.Get(context);  
                if (currentActivityIndex == Activities.Count)  
                {  
                    //if the currentActivityIndex is equal to the count of MySequence's Activities  
                    //MySequence is complete  
                    return;  
                }  
  
                if (this.onChildComplete == null)  
                {  
                    //on completion of the current child, have the runtime call back on this method  
                    this.onChildComplete = new CompletionCallback(InternalExecute);  
                }  
  
                //grab the next Activity in MySequence.Activities and schedule it  
                Activity nextChild = Activities[currentActivityIndex];  
                context.ScheduleActivity(nextChild, this.onChildComplete);  
  
                //increment the currentIndex  
                this.currentIndex.Set(context, ++currentActivityIndex);  
            }  
    protected override void Execute(  
                NativeActivityContext context)  
            {  
                context.Properties.Add("ReceiveInstanceIdCallback", new ReceiveInstanceIdCallback());  
                InternalExecute(context, null);  
            }  
  
            void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
            {  
                //grab the index of the current Activity  
                int currentActivityIndex = this.currentIndex.Get(context);  
                if (currentActivityIndex == Activities.Count)  
                {  
                    //if the currentActivityIndex is equal to the count of MySequence's Activities  
                    //MySequence is complete  
                    return;  
                }  
  
                if (this.onChildComplete == null)  
                {  
                    //on completion of the current child, have the runtime call back on this method  
                    this.onChildComplete = new CompletionCallback(InternalExecute);  
                }  
  
                //grab the next Activity in MySequence.Activities and schedule it  
                Activity nextChild = Activities[currentActivityIndex];  
                context.ScheduleActivity(nextChild, this.onChildComplete);  
  
                //increment the currentIndex  
                this.currentIndex.Set(context, ++currentActivityIndex);  
            }  
    ```  
  
### <a name="implement-a-workflow-client"></a>ワークフロー クライアントの実装  
  
1.  `Client` という新しいコンソール アプリケーション プロジェクトを作成します。  
  
2.  次のアセンブリへの参照を追加します。  
  
    1.  System.Activities  
  
    2.  System.ServiceModel  
  
    3.  System.ServiceModel.Activities  
  
3.  生成された Program.cs ファイルを開き、`GetClientWorkflow` という静的メソッドを追加してクライアント ワークフローを作成します。  
  
    ```  
    static Activity GetClientWorkflow()  
            {  
                Variable<string> echoString = new Variable<string>();  
  
                // Define the endpoint  
                Endpoint clientEndpoint = new Endpoint  
                {  
                    Binding = new BasicHttpBinding(),  
                    AddressUri = new Uri("http://localhost:8080/Service")  
                };  
  
                // Configure the Send activity used to send a message  
                Send echoRequest = new Send  
                {  
                    Endpoint = clientEndpoint,  
                    ServiceContractName = XName.Get("IService", "http://tempuri.org"),  
                    OperationName = "Echo",  
                    Content = new SendParametersContent()  
                    {  
                        Parameters = { { "echoString", new InArgument<string>("Hello, World") } }   
                    }  
                };  
  
                // Place the Send activity in a SendInstanceIdScope. This hooks up the ISendMessageCallback   
                // implementation to the client workflow.  
                return new SendInstanceIdScope  
                {  
                    Variables = { echoString },  
                    Activities =  
                    {                      
                        new CorrelationScope  
                        {  
                            Body = new Sequence  
                            {  
                                Activities =   
                                {  
                                    // Send the request message  
                                    echoRequest,  
  
                                   // Receive the reply from the service  
                                    new ReceiveReply  
                                    {  
                                        Request = echoRequest,  
                                        Content = new ReceiveParametersContent  
                                        {  
                                            Parameters = { { "result", new OutArgument<string>(echoString) } }  
                                        }  
                                    }  
                                }  
                            }  
                        },                      
                        new WriteLine { Text = new InArgument<string>( (e) => "Received Text: " + echoString.Get(e) ) },                      
                    }  
                };  
            }  
    ```  
  
4.  次のホスティング コードを `Main()` メソッドに追加します。  
  
    ```  
    static void Main(string[] args)  
    {  
       Activity workflow = GetClientWorkflow();  
       WorkflowInvoker.Invoke(workflow);  
       WorkflowInvoker.Invoke(workflow);  
       Console.WriteLine("Press [ENTER] to exit");  
       Console.ReadLine();  
    }  
    ```  
  
## <a name="example"></a>例  
 このトピックで使用されているソース コードの完全な一覧を次に示します。  
  
```  
// ReceiveInstanceIdScope.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System.Activities;  
using System.Collections.ObjectModel;  
  
namespace Microsoft.Samples.AccessingOperationContext.Service  
{  
    public sealed class ReceiveInstanceIdScope : NativeActivity  
    {  
        Collection<Activity> children;  
        Collection<Variable> variables;  
        Variable<int> currentIndex;  
        CompletionCallback onChildComplete;  
  
        public ReceiveInstanceIdScope()  
            : base()  
        {  
            this.children = new Collection<Activity>();  
            this.variables = new Collection<Variable>();  
            this.currentIndex = new Variable<int>();  
        }  
  
        public Collection<Activity> Activities  
        {  
            get  
            {  
                return this.children;  
            }  
        }  
  
        public Collection<Variable> Variables  
        {  
            get  
            {  
                return this.variables;  
            }  
        }  
  
        protected override void CacheMetadata(NativeActivityMetadata metadata)  
        {  
            //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
            base.CacheMetadata(metadata);  
            //add the private implementation variable: currentIndex   
            metadata.AddImplementationVariable(this.currentIndex);  
        }                     
  
        protected override void Execute(  
            NativeActivityContext context)  
        {  
            context.Properties.Add("ReceiveInstanceIdCallback", new ReceiveInstanceIdCallback());  
            InternalExecute(context, null);  
        }  
  
        void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
        {  
            //grab the index of the current Activity  
            int currentActivityIndex = this.currentIndex.Get(context);  
            if (currentActivityIndex == Activities.Count)  
            {  
                //if the currentActivityIndex is equal to the count of MySequence's Activities  
                //MySequence is complete  
                return;  
            }  
  
            if (this.onChildComplete == null)  
            {  
                //on completion of the current child, have the runtime call back on this method  
                this.onChildComplete = new CompletionCallback(InternalExecute);  
            }  
  
            //grab the next Activity in MySequence.Activities and schedule it  
            Activity nextChild = Activities[currentActivityIndex];  
            context.ScheduleActivity(nextChild, this.onChildComplete);  
  
            //increment the currentIndex  
            this.currentIndex.Set(context, ++currentActivityIndex);  
        }  
    }  
}  
```  
  
```  
// ReceiveInstanceIdScope.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.ServiceModel;  
using System.ServiceModel.Activities;  
  
namespace Microsoft.Samples.AccessingOperationContext.Service  
{  
    class ReceiveInstanceIdCallback : IReceiveMessageCallback  
    {  
        public const string HeaderName = "InstanceIdHeader";  
        public const string HeaderNS = "http://Microsoft.Samples.AccessingOperationContext";  
  
        public void OnReceiveMessage(System.ServiceModel.OperationContext operationContext, System.Activities.ExecutionProperties activityExecutionProperties)  
        {              
            try  
            {  
                Guid instanceId = operationContext.IncomingMessageHeaders.GetHeader<Guid>(HeaderName, HeaderNS);  
                Console.WriteLine("Received a message from a workflow with instanceId = {0}", instanceId);  
            }  
            catch (MessageHeaderException)  
            {  
                Console.WriteLine("This message must not be from a workflow.");  
            }  
        }  
    }  
}  
```  
  
```  
// Service.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.Activities;  
using System.Activities.Statements;  
using System.ServiceModel;  
using System.ServiceModel.Activities;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.AccessingOperationContext.Service  
{      
    class Program  
    {  
        const string addr = "http://localhost:8080/Service";  
        static XName contract = XName.Get("IService", "http://tempuri.org");  
  
        static void Main(string[] args)  
        {  
            string addr = "http://localhost:8080/Service";  
  
            using (WorkflowServiceHost host = new WorkflowServiceHost(GetServiceWorkflow()))  
            {  
                host.AddServiceEndpoint(contract, new BasicHttpBinding(), addr);  
  
                host.Open();  
                Console.WriteLine("Service waiting at: " + addr);  
                Console.WriteLine("Press [ENTER] to exit");  
                Console.ReadLine();  
                host.Close();  
            }  
  
        }  
  
        static Activity GetServiceWorkflow()  
        {  
            Variable<string> echoString = new Variable<string>();  
  
            Receive echoRequest = new Receive  
            {  
                CanCreateInstance = true,  
                ServiceContractName = contract,  
                OperationName = "Echo",  
                Content = new ReceiveParametersContent()  
                {  
                    Parameters = { { "echoString", new OutArgument<string>(echoString) } }  
                }  
            };  
  
            return new ReceiveInstanceIdScope  
            {  
                Variables = { echoString },  
                Activities =  
                {  
                    echoRequest,  
                    new WriteLine { Text = new InArgument<string>( (e) => "Received: " + echoString.Get(e) ) },  
                    new SendReply  
                    {  
                        Request = echoRequest,  
                        Content = new SendParametersContent()  
                        {  
                            Parameters = { { "result", new InArgument<string>(echoString) } }   
                        }  
                    }  
                }  
            };  
        }  
    }  
  
}  
```  
  
```  
// SendInstanceIdCallback.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Channels;  
  
namespace Microsoft.Samples.AccessingOperationContext.Client  
{  
    class SendInstanceIdCallback : ISendMessageCallback  
    {  
        public const string HeaderName = "InstanceIdHeader";  
        public const string HeaderNS = "http://Microsoft.Samples.AccessingOperationContext";  
  
        public Guid InstanceId { get; set; }  
  
        public void OnSendMessage(System.ServiceModel.OperationContext operationContext)  
        {  
            operationContext.OutgoingMessageHeaders.Add(MessageHeader.CreateHeader(HeaderName, HeaderNS, this.InstanceId));  
        }  
    }  
}  
```  
  
```  
// SendInstanceIdScope.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System.Activities;  
using System.Collections.ObjectModel;  
  
namespace Microsoft.Samples.AccessingOperationContext.Client  
{  
    public sealed class SendInstanceIdScope : NativeActivity  
    {  
        Collection<Activity> children;  
        Collection<Variable> variables;  
        Variable<int> currentIndex;  
        CompletionCallback onChildComplete;  
  
        public SendInstanceIdScope()  
            : base()  
        {  
            this.children = new Collection<Activity>();  
            this.variables = new Collection<Variable>();  
            this.currentIndex = new Variable<int>();  
        }  
  
        public Collection<Activity> Activities  
        {  
            get  
            {  
                return this.children;  
            }  
        }  
  
        public Collection<Variable> Variables  
        {  
            get  
            {  
                return this.variables;  
            }  
        }  
  
        protected override void CacheMetadata(NativeActivityMetadata metadata)  
        {  
            //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
            base.CacheMetadata(metadata);  
            //add the private implementation variable: currentIndex   
            metadata.AddImplementationVariable(this.currentIndex);  
        }  
  
        protected override void Execute(  
            NativeActivityContext context)  
        {  
            context.Properties.Add("SendInstanceIdCallback", new SendInstanceIdCallback() { InstanceId = context.WorkflowInstanceId });  
            InternalExecute(context, null);  
        }  
  
        void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
        {  
            //grab the index of the current Activity  
            int currentActivityIndex = this.currentIndex.Get(context);  
            if (currentActivityIndex == Activities.Count)  
            {  
                //if the currentActivityIndex is equal to the count of MySequence's Activities  
                //MySequence is complete  
                return;  
            }  
  
            if (this.onChildComplete == null)  
            {  
                //on completion of the current child, have the runtime call back on this method  
                this.onChildComplete = new CompletionCallback(InternalExecute);  
            }  
  
            //grab the next Activity in MySequence.Activities and schedule it  
            Activity nextChild = Activities[currentActivityIndex];  
            context.ScheduleActivity(nextChild, this.onChildComplete);  
  
            //increment the currentIndex  
            this.currentIndex.Set(context, ++currentActivityIndex);  
        }  
    }  
}  
```  
  
```  
// Client.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.Activities;  
using System.Activities.Statements;  
using System.ServiceModel;  
using System.ServiceModel.Activities;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.AccessingOperationContext.Client  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Activity workflow = GetClientWorkflow();  
            WorkflowInvoker.Invoke(workflow);  
            WorkflowInvoker.Invoke(workflow);  
            Console.WriteLine("Press [ENTER] to exit");  
            Console.ReadLine();  
        }  
  
        static Activity GetClientWorkflow()  
        {  
            Variable<string> echoString = new Variable<string>();  
  
            Endpoint clientEndpoint = new Endpoint  
            {  
                Binding = new BasicHttpBinding(),  
                AddressUri = new Uri("http://localhost:8080/Service")  
            };  
  
            Send echoRequest = new Send  
            {  
                Endpoint = clientEndpoint,  
                ServiceContractName = XName.Get("IService", "http://tempuri.org"),  
                OperationName = "Echo",  
                Content = new SendParametersContent()  
                {  
                    Parameters = { { "echoString", new InArgument<string>("Hello, World") } }   
                }  
            };  
  
            return new SendInstanceIdScope  
            {  
                Variables = { echoString },  
                Activities =  
                {                      
                    new CorrelationScope  
                    {  
                        Body = new Sequence  
                        {  
                            Activities =   
                            {  
                                echoRequest,  
                                new ReceiveReply  
                                {  
                                    Request = echoRequest,  
                                    Content = new ReceiveParametersContent  
                                    {  
                                        Parameters = { { "result", new OutArgument<string>(echoString) } }  
                                    }  
                                }  
                            }  
                        }  
                    },                      
                    new WriteLine { Text = new InArgument<string>( (e) => "Received Text: " + echoString.Get(e) ) },                      
                }  
            };  
        }  
    }  
}  
```  
  
 オプション コメント。  
  
## <a name="see-also"></a>関連項目  
 [ワークフロー サービス](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [OperationContext へのアクセス](../../../../docs/framework/windows-workflow-foundation/samples/accessing-operationcontext.md)  
 [命令型コードを使用してワークフロー、アクティビティ、および式を作成する方法](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)
