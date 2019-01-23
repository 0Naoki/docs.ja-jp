---
title: WCF クライアントを使用したサービスへのアクセス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 97340f8583ef0900645f6db5c453475e85549c55
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620196"
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="05659-102">WCF クライアントを使用したサービスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="05659-102">Accessing Services Using a WCF Client</span></span>

<span data-ttu-id="05659-103">サービスを作成した後、次の手順では、WCF クライアント プロキシを作成します。</span><span class="sxs-lookup"><span data-stu-id="05659-103">After you create a service, the next step is to create a WCF client proxy.</span></span> <span data-ttu-id="05659-104">クライアント アプリケーションでは、WCF クライアント プロキシを使用して、サービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="05659-104">A client application uses the WCF client proxy to communicate with the service.</span></span> <span data-ttu-id="05659-105">クライアント アプリケーションは、通常、サービスを呼び出すために使用する WCF クライアント コードを生成するサービスのメタデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="05659-105">Client applications usually import a service's metadata to generate WCF client code that can be used to invoke the service.</span></span>

 <span data-ttu-id="05659-106">WCF クライアントを作成するための基本的な手順を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="05659-106">The basic steps for creating a WCF client include the following:</span></span>

1.  <span data-ttu-id="05659-107">サービス コードをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="05659-107">Compile the service code.</span></span>

2.  <span data-ttu-id="05659-108">WCF クライアント プロキシを生成します。</span><span class="sxs-lookup"><span data-stu-id="05659-108">Generate the WCF client proxy.</span></span>

3.  <span data-ttu-id="05659-109">WCF クライアント プロキシをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="05659-109">Instantiate the WCF client proxy.</span></span>

<span data-ttu-id="05659-110">WCF クライアント プロキシは、サービス モデル メタデータ ユーティリティ ツール (SvcUtil.exe) を使用することによって、手動で生成することができます。詳細は「[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05659-110">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="05659-111">Visual Studio 内で WCF クライアント プロキシを生成することもを使用して、**サービス参照の追加**機能します。</span><span class="sxs-lookup"><span data-stu-id="05659-111">The WCF client proxy can also be generated within Visual Studio using the **Add Service Reference**  feature.</span></span> <span data-ttu-id="05659-112">いずれかの方法で WCF クライアント プロキシを生成するには、サービスが実行中であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="05659-112">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="05659-113">サービスが自己ホスト型の場合は、ホストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05659-113">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="05659-114">サービスが IIS/WAS でホストされている場合、特に必要な操作はありません。</span><span class="sxs-lookup"><span data-stu-id="05659-114">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>

## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="05659-115">ServiceModel メタデータ ユーティリティ ツール</span><span class="sxs-lookup"><span data-stu-id="05659-115">ServiceModel Metadata Utility Tool</span></span>
 <span data-ttu-id="05659-116">[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)はメタデータからコードを生成するためのコマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="05659-116">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="05659-117">基本的な Svcutil.exe コマンドの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="05659-117">The following use is an example of a basic Svcutil.exe command.</span></span>

```
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 <span data-ttu-id="05659-118">また、Svcutil.exe は、ファイル システム上の Web サービス記述言語 (WSDL) ファイルや XML スキーマ定義言語 (XSD) ファイルを指定して使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="05659-118">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>

```
Svcutil.exe <list of WSDL and XSD files on file system>
```

 <span data-ttu-id="05659-119">サービスを呼び出すクライアント アプリケーションが使用できる WCF クライアント コードを含むコード ファイルになります。</span><span class="sxs-lookup"><span data-stu-id="05659-119">The result is a code file that contains WCF client code that the client application can use to invoke the service.</span></span>

 <span data-ttu-id="05659-120">このツールを使用して構成ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="05659-120">You can also use the tool to generate configuration files.</span></span>

```
Svcutil.exe <file1 [,file2]>
```

 <span data-ttu-id="05659-121">ファイル名を 1 つだけ指定した場合、それは出力ファイルの名前になります。</span><span class="sxs-lookup"><span data-stu-id="05659-121">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="05659-122">ファイル名を 2 つ指定した場合は、1 番目のファイルが入力構成ファイルになり、そのファイルの内容と生成された構成がマージされ、2 番目のファイルに書き出されます。</span><span class="sxs-lookup"><span data-stu-id="05659-122">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> <span data-ttu-id="05659-123">構成の詳細については、次を参照してください。[サービスのバインドを構成する](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="05659-123">For more information about configuration, see [Configuring Bindings for Services](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05659-124">セキュリティ保護されていないメタデータ要求には、すべてのセキュリティ保護されていないネットワーク要求を行うのと同じ方法で特定のリスクが発生し得る。通信しているエンドポイントが書かれているユーザーが不明な取得した情報が悪意のあるサービスからメタデータにあります。</span><span class="sxs-lookup"><span data-stu-id="05659-124">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>

## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="05659-125">Visual Studio の "サービス参照の追加"</span><span class="sxs-lookup"><span data-stu-id="05659-125">Add Service Reference in Visual Studio</span></span>

 <span data-ttu-id="05659-126">サービスの実行とプロジェクトを右クリックは、WCF クライアント プロキシが含まれてし、**追加** > **サービス参照の**します。</span><span class="sxs-lookup"><span data-stu-id="05659-126">With the service running, right click the project that will contain the WCF client proxy and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="05659-127">**サービス参照の追加 ダイアログ ボックス**を呼び出すし、をクリックするサービスの URL を入力、**移動**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="05659-127">In the **Add Service Reference Dialog**, type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="05659-128">このダイアログ ボックスには、指定したアドレスで利用可能なサービスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05659-128">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="05659-129">サービス契約および使用可能な操作を参照してください、生成されたコードの名前空間を指定し、クリックをダブルクリックします、 **OK**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="05659-129">Double click the service to see the contracts and operations available, specify a namespace for the generated code, and click the **OK** button.</span></span>

## <a name="example"></a><span data-ttu-id="05659-130">例</span><span class="sxs-lookup"><span data-stu-id="05659-130">Example</span></span>
 <span data-ttu-id="05659-131">サービス用に作成されたコントラクトのコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="05659-131">The following code example shows a service contract created for a service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```

```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```

 <span data-ttu-id="05659-132">ServiceModel メタデータ ユーティリティ ツールと**サービス参照の追加**Visual Studio で、次の WCF クライアント クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="05659-132">The ServiceModel Metadata utility tool and **Add Service Reference** in Visual Studio generates the following WCF client class.</span></span> <span data-ttu-id="05659-133">このクラスは <xref:System.ServiceModel.ClientBase%601> ジェネリック クラスから継承されたもので、`ICalculator` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="05659-133">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="05659-134">このツールは、`ICalculator` インターフェイス (この例には表示されていません) も生成します。</span><span class="sxs-lookup"><span data-stu-id="05659-134">The tool also generates the `ICalculator` interface (not shown here).</span></span>

```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```

```vb
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```

## <a name="using-the-wcf-client"></a><span data-ttu-id="05659-135">WCF クライアントの使用</span><span class="sxs-lookup"><span data-stu-id="05659-135">Using the WCF Client</span></span>
 <span data-ttu-id="05659-136">WCF クライアントを使用するには、WCF クライアントのインスタンスを作成し、次のコードに示すように、そのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="05659-136">To use the WCF client, create an instance of the WCF client, and then call its methods, as shown in the following code.</span></span>

```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```

## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="05659-137">クライアントによってスローされた例外のデバッグ</span><span class="sxs-lookup"><span data-stu-id="05659-137">Debugging Exceptions Thrown by a Client</span></span>

<span data-ttu-id="05659-138">WCF クライアントによってスローされる多くの例外は、サービスで例外が原因です。</span><span class="sxs-lookup"><span data-stu-id="05659-138">Many exceptions thrown by a WCF client are caused by an exception on the service.</span></span> <span data-ttu-id="05659-139">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="05659-139">Some examples of this are:</span></span>

-   <span data-ttu-id="05659-140"><xref:System.Net.Sockets.SocketException>:既存の接続は、リモート ホストによって強制的に切断されました。</span><span class="sxs-lookup"><span data-stu-id="05659-140"><xref:System.Net.Sockets.SocketException>: An existing connection was forcibly closed by the remote host.</span></span>

-   <span data-ttu-id="05659-141"><xref:System.ServiceModel.CommunicationException>:基になる接続が予期せず閉じられました。</span><span class="sxs-lookup"><span data-stu-id="05659-141"><xref:System.ServiceModel.CommunicationException>: The underlying connection was closed unexpectedly.</span></span>

-   <span data-ttu-id="05659-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>:ソケット接続が中止されました。</span><span class="sxs-lookup"><span data-stu-id="05659-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: The socket connection was aborted.</span></span> <span data-ttu-id="05659-143">これは、メッセージ処理時のエラー、リモート ホストでの受信タイムアウトの超過、または基になるネットワーク リソースの問題が原因で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05659-143">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>

<span data-ttu-id="05659-144">このような種類の例外が発生した場合、問題を解決するには、サービス側でトレースをオンにし、そこで発生した例外を特定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05659-144">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> <span data-ttu-id="05659-145">トレースの詳細については、次を参照してください。[トレース](../../../docs/framework/wcf/diagnostics/tracing/index.md)と[を使用して、アプリケーションのトラブルシューティングのトレース](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="05659-145">For more information about tracing, see [Tracing](../../../docs/framework/wcf/diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="05659-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="05659-146">See also</span></span>

- [<span data-ttu-id="05659-147">方法: クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="05659-147">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="05659-148">方法: Access Services と双方向コントラクト</span><span class="sxs-lookup"><span data-stu-id="05659-148">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="05659-149">方法: サービス操作を非同期的に呼び出す</span><span class="sxs-lookup"><span data-stu-id="05659-149">How to: Call Service Operations Asynchronously</span></span>](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [<span data-ttu-id="05659-150">方法: 一方向のサービスにアクセスし、要求/応答コントラクト</span><span class="sxs-lookup"><span data-stu-id="05659-150">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [<span data-ttu-id="05659-151">方法: WSE 3.0 にアクセス サービス</span><span class="sxs-lookup"><span data-stu-id="05659-151">How to: Access a WSE 3.0 Service</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [<span data-ttu-id="05659-152">生成されたクライアント コードの理解</span><span class="sxs-lookup"><span data-stu-id="05659-152">Understanding Generated Client Code</span></span>](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)
- [<span data-ttu-id="05659-153">方法: アプリケーション起動時間の WCF クライアント、XmlSerializer を使用して向上させる</span><span class="sxs-lookup"><span data-stu-id="05659-153">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [<span data-ttu-id="05659-154">クライアントのランタイム動作の指定</span><span class="sxs-lookup"><span data-stu-id="05659-154">Specifying Client Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="05659-155">クライアントの動作の構成</span><span class="sxs-lookup"><span data-stu-id="05659-155">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)
