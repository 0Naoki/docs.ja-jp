---
title: WorkflowInvoker クラスの使用
ms.date: 03/30/2017
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
ms.openlocfilehash: d6525dbbd30aae95be4c4ee1de267736e557a541
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748710"
---
# <a name="using-the-workflowinvoker-class"></a><span data-ttu-id="389c8-102">WorkflowInvoker クラスの使用</span><span class="sxs-lookup"><span data-stu-id="389c8-102">Using the WorkflowInvoker Class</span></span>
<span data-ttu-id="389c8-103">このサンプルでは、<xref:System.Activities.WorkflowInvoker> クラスを使用して、メソッドのようにアクティビティを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="389c8-103">This sample demonstrates how to use the <xref:System.Activities.WorkflowInvoker> class to invoke an activity as if it were a method.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="389c8-104">サンプルの詳細</span><span class="sxs-lookup"><span data-stu-id="389c8-104">Sample Details</span></span>  
 <span data-ttu-id="389c8-105">アクティビティを実行するための最も簡単な方法は、<xref:System.Activities.WorkflowInvoker> クラスを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="389c8-105">Using the <xref:System.Activities.WorkflowInvoker> class is the simplest way to execute an activity.</span></span> <span data-ttu-id="389c8-106">このクラスは、メソッドを呼び出すようにアクティビティを直接実行することを目的として設計されています。</span><span class="sxs-lookup"><span data-stu-id="389c8-106">It is designed for directly running an activity as if it were a method call.</span></span> <span data-ttu-id="389c8-107">このクラスは、軽量で高性能な、使いやすい API で、アクティビティを実行する際に他のホスティングのバリエーションが提供する制御インフラストラクチャを必要としないシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="389c8-107">It is a lightweight, high-performing, easy to use API for use in scenarios where an activity’s execution does not require the control infrastructure provided by other hosting variations.</span></span>  
  
 <span data-ttu-id="389c8-108">サンプルから派生したカスタム アクティビティを使用して<xref:System.Activities.CodeActivity%601>< Int32\>という名前`Add`2 つ追加する<xref:System.Activities.InArgument%601>、`X`と`Y`、しを返します、 `Result`<xref:System.Activities.OutArgument%601>します。</span><span class="sxs-lookup"><span data-stu-id="389c8-108">The sample uses a custom activity that derives from <xref:System.Activities.CodeActivity%601><Int32\> named `Add` that adds two <xref:System.Activities.InArgument%601>, `X` and `Y`, and returns a `Result`<xref:System.Activities.OutArgument%601>.</span></span> <span data-ttu-id="389c8-109">(<xref:System.Activities.CodeActivity%601>\<T > から派生した<xref:System.Activities.Activity%601>< T\>を持つ、 <xref:System.Activities.OutArgument%601> \<T > という名前の`Result`)。A `Dictionary` \<object > を介して呼び出されるアクティビティに引数を渡すために使用<xref:System.Activities.WorkflowInvoker>します。</span><span class="sxs-lookup"><span data-stu-id="389c8-109">(<xref:System.Activities.CodeActivity%601>\<T> derives from <xref:System.Activities.Activity%601><T\>, which has an <xref:System.Activities.OutArgument%601>\<T> named `Result`.) A `Dictionary`\<string, object> is used to pass arguments into an activity being invoked through <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="389c8-110">ディクショナリのキーは、呼び出し先のアクティビティにおける引数名に対応します。</span><span class="sxs-lookup"><span data-stu-id="389c8-110">The key of the dictionary corresponds to the name of an argument on the invoked activity.</span></span> <span data-ttu-id="389c8-111">特定のキーに関連付けられた値は、キーによって識別される引数にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="389c8-111">The value associated with a particular key is bound to the argument identified by the key.</span></span>  
  
 <span data-ttu-id="389c8-112">このサンプルは、<xref:System.Activities.WorkflowInvoker.Invoke%2A> を呼び出して、`X` および `Y` の値を含むディクショナリを渡します。</span><span class="sxs-lookup"><span data-stu-id="389c8-112">The sample calls <xref:System.Activities.WorkflowInvoker.Invoke%2A> and passes a dictionary that contains values for `X` and `Y`.</span></span> <span data-ttu-id="389c8-113"><xref:System.Activities.WorkflowInvoker> クラスは、これらの値を `Add` アクティビティの引数にバインドし、アクティビティを実行して、結果を返します。</span><span class="sxs-lookup"><span data-stu-id="389c8-113">The <xref:System.Activities.WorkflowInvoker> class binds these values to the `Add` activity’s arguments, executes the activity, and returns the result.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="389c8-114">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="389c8-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="389c8-115">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、Invoker.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="389c8-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Invoker.sln solution file.</span></span>  
  
2.  <span data-ttu-id="389c8-116">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="389c8-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="389c8-117">ソリューションを実行するには、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="389c8-117">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="389c8-118">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="389c8-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="389c8-119">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="389c8-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="389c8-120">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="389c8-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="389c8-121">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="389c8-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`