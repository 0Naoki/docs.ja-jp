---
title: '&lt;追加&gt;schemeSettings (Uri 設定) の要素'
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9cca5e35bfc0aef448d2d515f5ac55ed9e2e2258
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028798"
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="35326-102">&lt;追加&gt;schemeSettings (Uri 設定) の要素</span><span class="sxs-lookup"><span data-stu-id="35326-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="35326-103">スキーム名の設定の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="35326-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="35326-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="35326-104">\<configuration></span></span>  
<span data-ttu-id="35326-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="35326-105">\<uri></span></span>  
<span data-ttu-id="35326-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="35326-106">\<schemeSettings></span></span>  
<span data-ttu-id="35326-107">\<add></span><span class="sxs-lookup"><span data-stu-id="35326-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35326-108">構文</span><span class="sxs-lookup"><span data-stu-id="35326-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35326-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="35326-109">Attributes and Elements</span></span>  
 <span data-ttu-id="35326-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="35326-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35326-111">属性</span><span class="sxs-lookup"><span data-stu-id="35326-111">Attributes</span></span>  
  
|<span data-ttu-id="35326-112">属性</span><span class="sxs-lookup"><span data-stu-id="35326-112">Attribute</span></span>|<span data-ttu-id="35326-113">説明</span><span class="sxs-lookup"><span data-stu-id="35326-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35326-114">name</span><span class="sxs-lookup"><span data-stu-id="35326-114">name</span></span>|<span data-ttu-id="35326-115">スキーム名は、この設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="35326-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="35326-116">だけでサポートされる値は名前 ="http"と名前 ="https"。</span><span class="sxs-lookup"><span data-stu-id="35326-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="35326-117">{Name} 属性属性</span><span class="sxs-lookup"><span data-stu-id="35326-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="35326-118">[値]</span><span class="sxs-lookup"><span data-stu-id="35326-118">Value</span></span>|<span data-ttu-id="35326-119">説明</span><span class="sxs-lookup"><span data-stu-id="35326-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="35326-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="35326-120">genericUriParserOptions</span></span>|<span data-ttu-id="35326-121">このスキームのパーサー オプション。</span><span class="sxs-lookup"><span data-stu-id="35326-121">The parser options for this scheme.</span></span> <span data-ttu-id="35326-122">のみサポートされている値が genericUriParserOptions ="DontUnescapePathDotsAndSlashes"。</span><span class="sxs-lookup"><span data-stu-id="35326-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35326-123">子要素</span><span class="sxs-lookup"><span data-stu-id="35326-123">Child Elements</span></span>  
 <span data-ttu-id="35326-124">なし</span><span class="sxs-lookup"><span data-stu-id="35326-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35326-125">親要素</span><span class="sxs-lookup"><span data-stu-id="35326-125">Parent Elements</span></span>  
  
|<span data-ttu-id="35326-126">要素</span><span class="sxs-lookup"><span data-stu-id="35326-126">Element</span></span>|<span data-ttu-id="35326-127">説明</span><span class="sxs-lookup"><span data-stu-id="35326-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35326-128">\<schemeSettings> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="35326-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="35326-129"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="35326-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35326-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="35326-130">Remarks</span></span>  
 <span data-ttu-id="35326-131">既定で、<xref:System.Uri?displayProperty=nameWithType>クラスのエスケープを解除パーセントは、パスの圧縮を実行する前にパスの区切り文字をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="35326-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="35326-132">これは、次のような攻撃に対するセキュリティ メカニズムとして実装されていました。</span><span class="sxs-lookup"><span data-stu-id="35326-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="35326-133">この URI が渡される場合は、モジュール % を処理しないエンコードした文字を正しく、サーバーで実行されている次のコマンドになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35326-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="35326-134">このため、<xref:System.Uri?displayProperty=nameWithType>クラスの最初のエスケープを解除パス区切り記号とし、パスの圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="35326-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="35326-135">上への悪意のある URL を渡すことの結果<xref:System.Uri?displayProperty=nameWithType>クラスに次の URI のコンス トラクターの結果。</span><span class="sxs-lookup"><span data-stu-id="35326-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="35326-136">SchemeSettings の構成オプションを使用して、特定のスキームのないのエスケープを解除のパーセントでエンコードされたパス区切りには、この既定の動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="35326-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="35326-137">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="35326-137">Configuration Files</span></span>  
 <span data-ttu-id="35326-138">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="35326-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35326-139">例</span><span class="sxs-lookup"><span data-stu-id="35326-139">Example</span></span>  
 <span data-ttu-id="35326-140">次の例で使用する構成を示しています、 <xref:System.Uri> http スキームのパスをパーセントでエンコードされた区切り記号をエスケープしないをサポートするクラス。</span><span class="sxs-lookup"><span data-stu-id="35326-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="35326-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="35326-141">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="35326-142">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="35326-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
