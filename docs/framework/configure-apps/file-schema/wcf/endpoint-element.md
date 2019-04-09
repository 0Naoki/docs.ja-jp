---
title: <endpoint> 要素
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: 667086cda010daf51cb92116d636b9b526b4b34b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163411"
---
# <a name="endpoint-element"></a><span data-ttu-id="44d3d-102">\<エンドポイント > 要素</span><span class="sxs-lookup"><span data-stu-id="44d3d-102">\<endpoint> element</span></span>
<span data-ttu-id="44d3d-103">サービスの公開に使用されるサービス エンドポイントのバインディング、コントラクト、およびアドレスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="44d3d-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="44d3d-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="44d3d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="44d3d-105">\<service></span><span class="sxs-lookup"><span data-stu-id="44d3d-105">\<service></span></span>  
<span data-ttu-id="44d3d-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="44d3d-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44d3d-107">構文</span><span class="sxs-lookup"><span data-stu-id="44d3d-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44d3d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="44d3d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="44d3d-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="44d3d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44d3d-110">属性</span><span class="sxs-lookup"><span data-stu-id="44d3d-110">Attributes</span></span>  
  
|<span data-ttu-id="44d3d-111">属性</span><span class="sxs-lookup"><span data-stu-id="44d3d-111">Attribute</span></span>|<span data-ttu-id="44d3d-112">説明</span><span class="sxs-lookup"><span data-stu-id="44d3d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44d3d-113">アドレス</span><span class="sxs-lookup"><span data-stu-id="44d3d-113">address</span></span>|<span data-ttu-id="44d3d-114">エンドポイントのアドレスを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="44d3d-115">アドレスは、絶対または相対アドレスとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="44d3d-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="44d3d-116">相対アドレスが提供されている場合、ホストは、そのバインディングで使用されるトランスポート スキームに適したベース アドレスが提供されることを想定します。</span><span class="sxs-lookup"><span data-stu-id="44d3d-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="44d3d-117">アドレスが構成されていない場合、ベース アドレスはそのエンドポイントのアドレスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="44d3d-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="44d3d-118">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="44d3d-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="44d3d-119">behaviorConfiguration</span></span>|<span data-ttu-id="44d3d-120">エンドポイントで使用される動作の名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="44d3d-121">バインド</span><span class="sxs-lookup"><span data-stu-id="44d3d-121">binding</span></span>|<span data-ttu-id="44d3d-122">使用するバインディングの種類を指定する必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="44d3d-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="44d3d-123">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d3d-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="44d3d-124">種類は、バインディングの種類の名前ではなくセクション名で登録されます。</span><span class="sxs-lookup"><span data-stu-id="44d3d-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="44d3d-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="44d3d-125">bindingConfiguration</span></span>|<span data-ttu-id="44d3d-126">エンドポイントがインスタンス化されるときに使用するバインディングのバインディング名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="44d3d-127">バインディング名は、エンドポイントが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d3d-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="44d3d-128">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="44d3d-129">この属性は、構成ファイル内の特定のバインディング構成を参照するために、`binding` と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="44d3d-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="44d3d-130">カスタム バインドを使用しようとする場合にこの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="44d3d-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="44d3d-131">そうでない場合は、例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="44d3d-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="44d3d-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="44d3d-132">bindingName</span></span>|<span data-ttu-id="44d3d-133">WSDL を介した定義エクスポートに使用するバインディングの一意の修飾名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="44d3d-134">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="44d3d-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="44d3d-135">bindingNamespace</span></span>|<span data-ttu-id="44d3d-136">WSDL を介した定義エクスポートに使用するバインディングの名前空間の修飾名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="44d3d-137">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="44d3d-138">コントラクト</span><span class="sxs-lookup"><span data-stu-id="44d3d-138">contract</span></span>|<span data-ttu-id="44d3d-139">このエンドポイントが公開するコントラクトを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="44d3d-140">アセンブリは、コントラクト型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d3d-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="44d3d-141">サービス実装が単一のコントラクトの型を実装する場合は、このプロパティを省略できます。</span><span class="sxs-lookup"><span data-stu-id="44d3d-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="44d3d-142">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="44d3d-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="44d3d-143">endpointConfiguration</span></span>|<span data-ttu-id="44d3d-144">この標準エンドポイントの追加の構成情報を参照する `kind` 属性によって設定される標準エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="44d3d-145">同じ名前を `<standardEndpoints>` セクションに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d3d-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="44d3d-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="44d3d-146">isSystemEndpoint</span></span>|<span data-ttu-id="44d3d-147">インフラストラクチャ エンドポイントであるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="44d3d-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="44d3d-148">kind</span><span class="sxs-lookup"><span data-stu-id="44d3d-148">kind</span></span>|<span data-ttu-id="44d3d-149">適用する標準エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="44d3d-150">種類は `<extensions>` セクションまたは machine.config に登録する必要があります。何も指定されていない場合は、共通のサービス エンドポイントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="44d3d-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="44d3d-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="44d3d-151">listenUriMode</span></span>|<span data-ttu-id="44d3d-152">リッスンするサービスに提供される `ListenUri` をトランスポートが処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="44d3d-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="44d3d-153">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44d3d-153">Valid values are</span></span><br /><br /> <span data-ttu-id="44d3d-154">明示的</span><span class="sxs-lookup"><span data-stu-id="44d3d-154">-   Explicit</span></span><br /><span data-ttu-id="44d3d-155">一意</span><span class="sxs-lookup"><span data-stu-id="44d3d-155">-   Unique</span></span><br /><br /> <span data-ttu-id="44d3d-156">既定値は Explicit です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="44d3d-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="44d3d-157">listenUri</span></span>|<span data-ttu-id="44d3d-158">サービス エンドポイントがリッスンする URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="44d3d-159">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="44d3d-160">name</span><span class="sxs-lookup"><span data-stu-id="44d3d-160">name</span></span>|<span data-ttu-id="44d3d-161">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-161">Optional attribute.</span></span> <span data-ttu-id="44d3d-162">サービス エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="44d3d-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="44d3d-163">既定値は、バインディング名とコントラクトの説明の名前を連結した値です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="44d3d-164">サービスには複数のエンドポイントが存在する場合があるため、エンドポイントの `name` 属性はサービスの名前とは異なります。</span><span class="sxs-lookup"><span data-stu-id="44d3d-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44d3d-165">子要素</span><span class="sxs-lookup"><span data-stu-id="44d3d-165">Child Elements</span></span>  
  
|<span data-ttu-id="44d3d-166">要素</span><span class="sxs-lookup"><span data-stu-id="44d3d-166">Element</span></span>|<span data-ttu-id="44d3d-167">説明</span><span class="sxs-lookup"><span data-stu-id="44d3d-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44d3d-168">\<headers></span><span class="sxs-lookup"><span data-stu-id="44d3d-168">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="44d3d-169">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="44d3d-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="44d3d-170">\<identity></span><span class="sxs-lookup"><span data-stu-id="44d3d-170">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="44d3d-171">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44d3d-172">親要素</span><span class="sxs-lookup"><span data-stu-id="44d3d-172">Parent Elements</span></span>  
  
|<span data-ttu-id="44d3d-173">要素</span><span class="sxs-lookup"><span data-stu-id="44d3d-173">Element</span></span>|<span data-ttu-id="44d3d-174">説明</span><span class="sxs-lookup"><span data-stu-id="44d3d-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44d3d-175">\<service></span><span class="sxs-lookup"><span data-stu-id="44d3d-175">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="44d3d-176">クライアントが接続可能なエンドポイントの一覧を定義する設定セクションです。</span><span class="sxs-lookup"><span data-stu-id="44d3d-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="44d3d-177">例</span><span class="sxs-lookup"><span data-stu-id="44d3d-177">Example</span></span>  
 <span data-ttu-id="44d3d-178">これはサービス エンドポイントの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="44d3d-178">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="44d3d-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="44d3d-179">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="44d3d-180">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="44d3d-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="44d3d-181">方法: 構成にサービス エンドポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="44d3d-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
