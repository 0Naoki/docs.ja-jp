---
title: POX アプリケーションとの相互運用性
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: b7fdb4e16bce52025515ced065d0f48cffb7fa3f
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035033"
---
# <a name="interoperability-with-pox-applications"></a><span data-ttu-id="f4cb2-102">POX アプリケーションとの相互運用性</span><span class="sxs-lookup"><span data-stu-id="f4cb2-102">Interoperability with POX applications</span></span>

<span data-ttu-id="f4cb2-103">"Plain Old XML"(POX) アプリケーションは、SOAP エンベロープで囲まれていない XML アプリケーション データのみを含んだ生の HTTP メッセージの交換によって通信します。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-103">"Plain Old XML" (POX) applications communicate by exchanging raw HTTP messages that contain only XML application data that is not enclosed within a SOAP envelope.</span></span> <span data-ttu-id="f4cb2-104">Windows Communication Foundation (WCF) には、サービスと POX メッセージを使用するクライアントの両方を提供できます。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-104">Windows Communication Foundation (WCF) can provide both services and clients that use POX messages.</span></span> <span data-ttu-id="f4cb2-105">サービスでは、Web ブラウザーなどのクライアント エンドポイントを公開するサービスと POX メッセージを送受信するためのスクリプト言語を実装するために WCF を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-105">On the service, WCF can be used to implement services that expose endpoints to clients such as Web browsers and scripting languages that send and receive POX messages.</span></span> <span data-ttu-id="f4cb2-106">クライアントでは、POX ベースのサービスと通信するクライアントを実装するために、WCF プログラミング モデルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-106">On the client, the WCF programming model can be used to implement clients that communicate with POX-based services.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4cb2-107">このドキュメントはもともと [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0 用に書かれたものです。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-107">This document was originally written for the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.</span></span>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] <span data-ttu-id="f4cb2-108">3.5 には POX アプリケーション用のサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-108"> 3.5 has built-in support for working with POX applications.</span></span> <span data-ttu-id="f4cb2-109">参照の詳細については[WCF Web HTTP プログラミング モデル](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-109">For more information about see [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span></span>
  
## <a name="pox-programming-with-wcf"></a><span data-ttu-id="f4cb2-110">WCF による POX プログラミング</span><span class="sxs-lookup"><span data-stu-id="f4cb2-110">POX programming with WCF</span></span>

<span data-ttu-id="f4cb2-111">POX メッセージを使用して HTTP 経由で通信する WCF サービスを[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-111">WCF services that communicate over HTTP using POX messages use a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

<span data-ttu-id="f4cb2-112">このカスタム バインドには、次の 2 つの要素があります。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-112">This custom binding contains two elements:</span></span>

- [<span data-ttu-id="f4cb2-113">\<httpTransport ></span><span class="sxs-lookup"><span data-stu-id="f4cb2-113">\<httpTransport></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)

- [<span data-ttu-id="f4cb2-114">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="f4cb2-114">\<textMessageEncoding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)

<span data-ttu-id="f4cb2-115">標準の WCF のテキスト メッセージ エンコーダーが使用する特別に構成された、<xref:System.ServiceModel.Channels.MessageVersion.None%2A>値で、XML メッセージ ペイロードされずに到着する SOAP エンベロープにラップを処理するようになります。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-115">The standard WCF Text Message Encoder is specially configured to use the <xref:System.ServiceModel.Channels.MessageVersion.None%2A> value, which allows it to process XML message payloads that do not arrive wrapped in a SOAP envelope.</span></span>

<span data-ttu-id="f4cb2-116">POX メッセージを使用して HTTP を介して通信する WCF クライアントは、(次の命令型コードに示す) のようなバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-116">WCF clients that communicate over HTTP using POX messages use a similar binding (shown in the following imperative code).</span></span>

```csharp
private static Binding CreatePoxBinding()
{
    TextMessageEncodingBindingElement encoder =
        new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );
    HttpTransportBindingElement transport = new HttpTransportBindingElement();
    transport.ManualAddressing = true;
    return new CustomBinding( new BindingElement[] { encoder, transport } );
}
```

<span data-ttu-id="f4cb2-117">POX クライアントでは、メッセージの送信先となる URI を明示的に指定する必要があるため、クライアントの <xref:System.ServiceModel.Channels.HttpTransportBindingElement> プロパティを <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> に設定することで、通常、`true` を手動アドレス指定モードに構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-117">Because POX clients must explicitly specify the URIs to which they send messages, they usually must configure the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> to a manual addressing mode by setting the <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> property to `true` on the element.</span></span> <span data-ttu-id="f4cb2-118">これにより、アプリケーション コードによってメッセージのアドレスが明示的に指定されることになり、アプリケーションで異なる HTTP URI にメッセージを送信するたびに、新しい <xref:System.ServiceModel.ChannelFactory> を作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-118">This allows messages to be addressed explicitly by application code and it is not necessary to create a new <xref:System.ServiceModel.ChannelFactory> every time an application sends a message to a different HTTP URI.</span></span>

<span data-ttu-id="f4cb2-119">POX メッセージでは重要なプロトコル情報の搬送に SOAP ヘッダーを使用しないため、POX クライアントおよびサービスでは、メッセージの送受信に使用される、基になる HTTP 要求の情報を操作する必要が生じる場合がよく起こります。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-119">Because POX messages do not use SOAP headers to convey important protocol information, POX clients and services often must manipulate pieces of the underlying HTTP request used to send or receive a message.</span></span> <span data-ttu-id="f4cb2-120">HTTP ヘッダーやステータス コードなどの HTTP 固有のプロトコル情報は、2 つのクラスを使用して、WCF プログラミング モデルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-120">HTTP-specific protocol information such as the HTTP headers and status codes are surfaced in the WCF programming model through two classes:</span></span>

- <span data-ttu-id="f4cb2-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty> には、HTTP メソッドと要求ヘッダーなど、HTTP 要求についての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, which contains information about the HTTP request, such as the HTTP method and request headers.</span></span>

- <span data-ttu-id="f4cb2-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty> には、HTTP ステータス コード、ステータスの説明、および任意の HTTP 応答ヘッダーなど、HTTP 応答についての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, which contains information about the HTTP response, such as the HTTP status code and status description, as well as any HTTP response headers.</span></span>
  
<span data-ttu-id="f4cb2-123">次のコード例は、宛先は、HTTP GET 要求メッセージを作成する方法を示します`http://localhost:8100/customers`します。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-123">The following code example shows how to create an HTTP GET request message that is addressed to `http://localhost:8100/customers`.</span></span>

```csharp
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );
request.Headers.To = "http://localhost:8100/customers";

HttpRequestMessageProperty property = new HttpRequestMessageProperty();
property.Method = "GET";
property.SuppressEntityBody = true;
request.Properties.Add( HttpRequestMessageProperty.Name, property );
```

<span data-ttu-id="f4cb2-124">初めに、<xref:System.ServiceModel.Channels.Message> を呼び出すことで、空の <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29> 要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-124">First, an empty request <xref:System.ServiceModel.Channels.Message> is created by calling <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span></span> <span data-ttu-id="f4cb2-125"><xref:System.ServiceModel.Channels.MessageVersion.None%2A> パラメーターを使用して SOAP エンベロープが不要であることを示し、<xref:System.String.Empty> パラメーターをアクションとして渡します。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-125">The <xref:System.ServiceModel.Channels.MessageVersion.None%2A> parameter is used to indicate that a SOAP envelope is not required and <xref:System.String.Empty> parameter is passed as the Action.</span></span> <span data-ttu-id="f4cb2-126">次に、<xref:System.ServiceModel.Channels.MessageHeaders.To%2A> を目的の URI に設定することで、要求メッセージをアドレス指定します。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-126">The request message is then addressed by setting <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> header to the desired URI.</span></span> <span data-ttu-id="f4cb2-127">さらに、<xref:System.ServiceModel.Channels.HttpRequestMessageProperty> を作成し、<xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> を HTTP 動詞の GET メソッドに設定し、また <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> を `true` に設定して、送信 HTTP 要求メッセージの本文でデータが送信されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-127">Next, an <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> is created and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> is set to the HTTP verb GET method and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> is set to `true` to indicate that no data should be sent in the body of the outgoing HTTP request message.</span></span> <span data-ttu-id="f4cb2-128">最後に、要求プロパティを要求メッセージの <xref:System.ServiceModel.Channels.Message.Properties%2A> コレクションに追加して、HTTP トランスポートによる要求の送信方法に影響を与えることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-128">Finally, the request property is added to the <xref:System.ServiceModel.Channels.Message.Properties%2A> collection of the request message so it can influence how the HTTP Transport sends the request.</span></span> <span data-ttu-id="f4cb2-129">これで <xref:System.ServiceModel.Channels.IRequestChannel> の適切なインスタンスを使用してメッセージを送信する用意が整いました。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-129">The message is then ready to be sent over an appropriate instance of the <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span>

<span data-ttu-id="f4cb2-130">サービスにおいても、受信メッセージから <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> を抽出して応答を構築する際に同様のテクニックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4cb2-130">Similar techniques can be used on the service to extract the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> from an incoming message and construct a response.</span></span>
