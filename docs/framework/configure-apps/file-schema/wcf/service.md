---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 68bddc01b02d9885b3f0fc4c2cbc5c3249de03f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197959"
---
# <a name="service"></a><span data-ttu-id="64d20-101">\<service></span><span class="sxs-lookup"><span data-stu-id="64d20-101">\<service></span></span>
<span data-ttu-id="64d20-102">`service` 要素には Windows Communication Foundation (WCF) サービスの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="64d20-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="64d20-103">また、サービスを公開するエンドポイントも含まれます。</span><span class="sxs-lookup"><span data-stu-id="64d20-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="64d20-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="64d20-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="64d20-105">\<services></span><span class="sxs-lookup"><span data-stu-id="64d20-105">\<services></span></span>  
<span data-ttu-id="64d20-106">\<service></span><span class="sxs-lookup"><span data-stu-id="64d20-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d20-107">構文</span><span class="sxs-lookup"><span data-stu-id="64d20-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64d20-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="64d20-108">Attributes and Elements</span></span>  
 <span data-ttu-id="64d20-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="64d20-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64d20-110">属性</span><span class="sxs-lookup"><span data-stu-id="64d20-110">Attributes</span></span>  
  
|<span data-ttu-id="64d20-111">属性</span><span class="sxs-lookup"><span data-stu-id="64d20-111">Attribute</span></span>|<span data-ttu-id="64d20-112">説明</span><span class="sxs-lookup"><span data-stu-id="64d20-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64d20-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="64d20-113">behaviorConfiguration</span></span>|<span data-ttu-id="64d20-114">サービスのインスタンス化に使用される動作の動作名を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="64d20-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="64d20-115">動作名は、サービスが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="64d20-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="64d20-116">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="64d20-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="64d20-117">name</span><span class="sxs-lookup"><span data-stu-id="64d20-117">name</span></span>|<span data-ttu-id="64d20-118">インスタンス化するサービスの型を指定する必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="64d20-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="64d20-119">この設定は有効な型と同じでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="64d20-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="64d20-120">形式は、</span><span class="sxs-lookup"><span data-stu-id="64d20-120">The format should be</span></span> `Namespace.Class.`|  
  
### <a name="child-elements"></a><span data-ttu-id="64d20-121">子要素</span><span class="sxs-lookup"><span data-stu-id="64d20-121">Child Elements</span></span>  
  
|<span data-ttu-id="64d20-122">要素</span><span class="sxs-lookup"><span data-stu-id="64d20-122">Element</span></span>|<span data-ttu-id="64d20-123">説明</span><span class="sxs-lookup"><span data-stu-id="64d20-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64d20-124">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="64d20-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="64d20-125">このサービスを公開する `endpoint` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="64d20-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="64d20-126">\<host></span><span class="sxs-lookup"><span data-stu-id="64d20-126">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="64d20-127">このサービス インスタンスのホストを指定します。</span><span class="sxs-lookup"><span data-stu-id="64d20-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="64d20-128">この要素は <xref:System.ServiceModel.Configuration.HostElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="64d20-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64d20-129">親要素</span><span class="sxs-lookup"><span data-stu-id="64d20-129">Parent Elements</span></span>  
  
|<span data-ttu-id="64d20-130">要素</span><span class="sxs-lookup"><span data-stu-id="64d20-130">Element</span></span>|<span data-ttu-id="64d20-131">説明</span><span class="sxs-lookup"><span data-stu-id="64d20-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64d20-132">\<services></span><span class="sxs-lookup"><span data-stu-id="64d20-132">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="64d20-133">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="64d20-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64d20-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="64d20-134">Remarks</span></span>  
 <span data-ttu-id="64d20-135">サービスは、設定ファイルの `services` セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="64d20-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="64d20-136">アセンブリには、任意の数のサービスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="64d20-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="64d20-137">各サービスには、独自の `service` 設定セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="64d20-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="64d20-138">このセクションとその内容は、サービス コントラクト、動作、および特定のサービスのエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="64d20-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="64d20-139">`behaviorConfiguration` 要素も省略可能です。</span><span class="sxs-lookup"><span data-stu-id="64d20-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="64d20-140">サービスが使用する動作を識別します。</span><span class="sxs-lookup"><span data-stu-id="64d20-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="64d20-141">この属性で指定された動作は、同じ設定ファイルの範囲にある動作にリンクしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="64d20-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="64d20-142">各サービスでは、固有のアドレスとバインディングを持つ 1 つまたは複数のエンドポイントが公開されます。</span><span class="sxs-lookup"><span data-stu-id="64d20-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="64d20-143">構成ファイル内で使用されるすべてのバインディングは、そのファイルのスコープ内で定義される必要があります。</span><span class="sxs-lookup"><span data-stu-id="64d20-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="64d20-144">バインディングは、`name` 属性と `bindingConfiguration` 属性の組み合わせによってエンドポイントにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="64d20-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="64d20-145">`name` 属性は、バインディングが定義されているセクションを示します。</span><span class="sxs-lookup"><span data-stu-id="64d20-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="64d20-146">`bindingConfiguration` 属性は、バインディング セクション内の使用される構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="64d20-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="64d20-147">バインディング セクションでは、複数の設定を定義できます。</span><span class="sxs-lookup"><span data-stu-id="64d20-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64d20-148">例</span><span class="sxs-lookup"><span data-stu-id="64d20-148">Example</span></span>  
 <span data-ttu-id="64d20-149">これはサービスの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="64d20-149">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="64d20-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="64d20-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="64d20-151">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="64d20-151">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
