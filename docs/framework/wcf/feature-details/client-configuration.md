---
title: クライアント構成
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: eef3d4743c26a06bd114618522aff9f68e46628c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423756"
---
# <a name="client-configuration"></a><span data-ttu-id="c321a-102">クライアント構成</span><span class="sxs-lookup"><span data-stu-id="c321a-102">Client Configuration</span></span>
<span data-ttu-id="c321a-103">Windows Communication Foundation (WCF) クライアントの構成を使用して、アドレス、バインディング、動作、およびコントラクト、サービス エンドポイントへの接続にクライアントを使用して、クライアント エンドポイントの"ABC"プロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c321a-103">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="c321a-104">[\<クライアント >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md)要素には、 [\<エンドポイント >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)要素の属性を使用して、エンドポイントの abc プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="c321a-104">The [\<client>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="c321a-105">これらの属性については、このトピックの「エンドポイントの構成」で説明します。</span><span class="sxs-lookup"><span data-stu-id="c321a-105">These attributes are discussed in the "Configuring Endpoints" section of this topic.</span></span>  
  
 <span data-ttu-id="c321a-106">[\<エンドポイント >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)要素も含まれています、 [\<メタデータ >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)のインポートとエクスポートのメタデータの設定を指定するために使用する要素を[ \<ヘッダー >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)カスタム アドレス ヘッダーのコレクションを格納する要素と[ \<identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)他のエンドポイントによるエンドポイントの認証を有効にする要素メッセージを交換します。</span><span class="sxs-lookup"><span data-stu-id="c321a-106">The [\<endpoint>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element also contains a [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata , a [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="c321a-107">[\<ヘッダー >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)と[ \<identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)要素の一部である、<xref:System.ServiceModel.EndpointAddress>詳細については、[アドレス](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="c321a-107">The [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span> <span data-ttu-id="c321a-108">メタデータ拡張の使用法に関するトピックへのリンクは、このトピックの「メタデータの構成」にあります。</span><span class="sxs-lookup"><span data-stu-id="c321a-108">Links to topics that explain the use of metadata extensions are provided in the Configuring Metadata sub-section of this topic.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="c321a-109">エンドポイントの構成</span><span class="sxs-lookup"><span data-stu-id="c321a-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="c321a-110">クライアントの構成が 1 つ指定するクライアントを許可するように設計、またはそれぞれ独自の名前を持つ複数のエンドポイント アドレス、および各を参照すると、契約、 [\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)と[ \<動作 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)そのエンドポイントを構成に使用するクライアント構成内の要素。</span><span class="sxs-lookup"><span data-stu-id="c321a-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="c321a-111">クライアント構成ファイルに名前を付ける"App.config"ため、これは、WCF ランタイムが予期される名前です。</span><span class="sxs-lookup"><span data-stu-id="c321a-111">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="c321a-112">クライアント構成ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c321a-112">The following example shows a client configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
// Add another endpoint by adding another <endpoint> element.  
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"   
                 bypassProxyOnLocal="false"   
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"   
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
        //Configure this binding here.  
        </binding>  
          </wsHttpBinding>  
        </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="c321a-113">省略可能な `name` 属性は、特定のコントラクトのエンドポイントを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="c321a-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="c321a-114">この属性は、サービスへのチャネルの作成時に、クライアント構成のどのエンドポイントをターゲットとし、読み込む必要があるかを指定するために、<xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> または <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> が使用します。</span><span class="sxs-lookup"><span data-stu-id="c321a-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="c321a-115">エンドポイント構成名としてワイルドカード "\*" を使用できます。これは、使用できるエンドポイント構成が 1 つだけ存在する場合はファイル内のエンドポイント構成を読み込み、それ以外の場合は例外をスローするように <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> メソッドに指示します。</span><span class="sxs-lookup"><span data-stu-id="c321a-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="c321a-116">この属性が省略されている場合、指定されたコントラクトの種類に関連する既定のエンドポイントとして、対応するエンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c321a-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="c321a-117">`name` 属性の既定値は、他の名前と同様に一致する空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="c321a-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="c321a-118">すべてのエンドポイントには、エンドポイントを検索および識別するために、アドレスが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c321a-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="c321a-119">`address` 属性は、エンドポイントの場所を示す URL を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c321a-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="c321a-120">ただし、サービス エンドポイントのアドレスは、コードで指定することもできます。その場合は、URI (Uniform Resource Identifier) を作成し、<xref:System.ServiceModel.ServiceHost> メソッドのいずれかを使用して、この URI を <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> に追加します。</span><span class="sxs-lookup"><span data-stu-id="c321a-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="c321a-121">詳細については、次を参照してください。[アドレス](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)します。</span><span class="sxs-lookup"><span data-stu-id="c321a-121">For more information, see [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="c321a-122">導入が示すとおり、 [\<ヘッダー >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)と[ \<identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)要素の一部である、<xref:System.ServiceModel.EndpointAddress>も詳細については、 [アドレス](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="c321a-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="c321a-123">`binding` 属性は、エンドポイントがサービスに接続する際に使用するバインディングの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c321a-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="c321a-124">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c321a-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="c321a-125">前の例では、 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)セクションで、エンドポイントが使用することを示す、<xref:System.ServiceModel.WSHttpBinding>します。</span><span class="sxs-lookup"><span data-stu-id="c321a-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="c321a-126">ただし、エンドポイントが使用できる、指定された種類のバインディングが複数存在することもあります。</span><span class="sxs-lookup"><span data-stu-id="c321a-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="c321a-127">独自のこれらの各[\<バインド >](../../../../docs/framework/misc/binding.md) (バインド) 型の要素内の要素。</span><span class="sxs-lookup"><span data-stu-id="c321a-127">Each of these has its own [\<binding>](../../../../docs/framework/misc/binding.md) element within the (binding) type element.</span></span> <span data-ttu-id="c321a-128">`bindingconfiguration` 属性は、同じ種類のバインディングを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c321a-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="c321a-129">その値と対応している、`name`の属性、 [\<バインド >](../../../../docs/framework/misc/binding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="c321a-129">Its value is matched with the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element.</span></span> <span data-ttu-id="c321a-130">詳細については、クライアントを構成する方法についての構成を使用してバインドを参照してください[方法: 構成でクライアント バインディングを指定](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)します。</span><span class="sxs-lookup"><span data-stu-id="c321a-130">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="c321a-131">`behaviorConfiguration`を指定する属性が使用される[\<動作 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)の[ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)エンドポイントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c321a-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="c321a-132">その値と対応している、`name`の属性、 [\<動作 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)要素。</span><span class="sxs-lookup"><span data-stu-id="c321a-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="c321a-133">クライアントの動作を指定する構成を使用しての例は、次を参照してください。[クライアントの動作を構成する](../../../../docs/framework/wcf/configuring-client-behaviors.md)します。</span><span class="sxs-lookup"><span data-stu-id="c321a-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="c321a-134">`contract` 属性は、エンドポイントが公開するコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c321a-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="c321a-135">この値は、<xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> の <xref:System.ServiceModel.ServiceContractAttribute> にマップされます。</span><span class="sxs-lookup"><span data-stu-id="c321a-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="c321a-136">既定値は、サービスを実装するクラスの完全な型名です。</span><span class="sxs-lookup"><span data-stu-id="c321a-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="c321a-137">メタデータの構成</span><span class="sxs-lookup"><span data-stu-id="c321a-137">Configuring Metadata</span></span>  
 <span data-ttu-id="c321a-138">[\<メタデータ >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)要素を使用して、拡張機能をインポートするメタデータを登録するための設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="c321a-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="c321a-139">メタデータ システムの拡張の詳細については、次を参照してください。[メタデータ システムの拡張](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="c321a-139">For more information about extending the metadata system, see [Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c321a-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="c321a-140">See Also</span></span>  
 [<span data-ttu-id="c321a-141">エンドポイント : アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="c321a-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="c321a-142">クライアントの動作の構成</span><span class="sxs-lookup"><span data-stu-id="c321a-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
