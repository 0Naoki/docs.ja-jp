---
title: '&lt;Uri&gt;要素 (Uri 設定)'
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 48769298246dd71e040aac1c682e0fddfb5de89b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655544"
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="e06ff-102">&lt;Uri&gt;要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="e06ff-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="e06ff-103">.NET Framework での uniform resource identifier (Uri) を使用して表現された web アドレスの処理方法を指定する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e06ff-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="e06ff-104">スキーマの階層</span><span class="sxs-lookup"><span data-stu-id="e06ff-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="e06ff-105">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="e06ff-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="e06ff-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="e06ff-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="e06ff-107">構文</span><span class="sxs-lookup"><span data-stu-id="e06ff-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e06ff-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e06ff-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e06ff-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e06ff-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e06ff-110">属性</span><span class="sxs-lookup"><span data-stu-id="e06ff-110">Attributes</span></span>  
 <span data-ttu-id="e06ff-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e06ff-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e06ff-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e06ff-112">Child Elements</span></span>  
  
|<span data-ttu-id="e06ff-113">**要素**</span><span class="sxs-lookup"><span data-stu-id="e06ff-113">**Element**</span></span>|<span data-ttu-id="e06ff-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="e06ff-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e06ff-115">idn</span><span class="sxs-lookup"><span data-stu-id="e06ff-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="e06ff-116">国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e06ff-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="e06ff-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="e06ff-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="e06ff-118">International Resource Identifier (IRI) 解析が適用されるかどうかを指定します。 <xref:System.Uri> IRI 解析規則を適用してください。</span><span class="sxs-lookup"><span data-stu-id="e06ff-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="e06ff-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="e06ff-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="e06ff-120"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="e06ff-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e06ff-121">親要素</span><span class="sxs-lookup"><span data-stu-id="e06ff-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e06ff-122">**要素**</span><span class="sxs-lookup"><span data-stu-id="e06ff-122">**Element**</span></span>|<span data-ttu-id="e06ff-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="e06ff-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e06ff-124">configuration</span><span class="sxs-lookup"><span data-stu-id="e06ff-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="e06ff-125">すべての名前空間の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e06ff-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e06ff-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="e06ff-126">Remarks</span></span>  
 <span data-ttu-id="e06ff-127">`uri`要素にはメンバーの設定が含まれています、<xref:System.Uri>クラスによって使用されるクラス、<xref:System.Net>名前空間。</span><span class="sxs-lookup"><span data-stu-id="e06ff-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="e06ff-128">設定は、IRI と IDN のサポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e06ff-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e06ff-129">例</span><span class="sxs-lookup"><span data-stu-id="e06ff-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e06ff-130">説明</span><span class="sxs-lookup"><span data-stu-id="e06ff-130">Description</span></span>  
 <span data-ttu-id="e06ff-131">次の例で使用する構成を示しています、<xref:System.Uri>解析する IRI と IDN 名をサポートするクラス。</span><span class="sxs-lookup"><span data-stu-id="e06ff-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="e06ff-132">例は、すべての構成設定を消去し、し、http スキームのパスをパーセントでエンコードされた区切り記号をエスケープしないを追加します。</span><span class="sxs-lookup"><span data-stu-id="e06ff-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e06ff-133">コード</span><span class="sxs-lookup"><span data-stu-id="e06ff-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e06ff-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e06ff-134">See also</span></span>
- [<span data-ttu-id="e06ff-135">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e06ff-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
