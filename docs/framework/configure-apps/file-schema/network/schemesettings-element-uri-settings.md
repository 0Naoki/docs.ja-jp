---
title: '&lt;schemeSettings&gt;要素 (Uri 設定)'
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 7c75e9a6d29637e1701fe0b9e05adf0ccc3596b9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192552"
---
# <a name="ltschemesettingsgt-element-uri-settings"></a><span data-ttu-id="682c0-102">&lt;schemeSettings&gt;要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="682c0-102">&lt;schemeSettings&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="682c0-103"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="682c0-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="682c0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="682c0-104">\<configuration></span></span>  
<span data-ttu-id="682c0-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="682c0-105">\<uri></span></span>  
<span data-ttu-id="682c0-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="682c0-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="682c0-107">構文</span><span class="sxs-lookup"><span data-stu-id="682c0-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="682c0-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="682c0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="682c0-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="682c0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="682c0-110">属性</span><span class="sxs-lookup"><span data-stu-id="682c0-110">Attributes</span></span>  
 <span data-ttu-id="682c0-111">なし</span><span class="sxs-lookup"><span data-stu-id="682c0-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="682c0-112">子要素</span><span class="sxs-lookup"><span data-stu-id="682c0-112">Child Elements</span></span>  
  
|<span data-ttu-id="682c0-113">**要素**</span><span class="sxs-lookup"><span data-stu-id="682c0-113">**Element**</span></span>|<span data-ttu-id="682c0-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="682c0-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="682c0-115">add</span><span class="sxs-lookup"><span data-stu-id="682c0-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="682c0-116">スキーム名の設定の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="682c0-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="682c0-117">clear</span><span class="sxs-lookup"><span data-stu-id="682c0-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="682c0-118">既存のすべての構成設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="682c0-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="682c0-119">remove</span><span class="sxs-lookup"><span data-stu-id="682c0-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="682c0-120">スキーム名の構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="682c0-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="682c0-121">親要素</span><span class="sxs-lookup"><span data-stu-id="682c0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="682c0-122">**要素**</span><span class="sxs-lookup"><span data-stu-id="682c0-122">**Element**</span></span>|<span data-ttu-id="682c0-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="682c0-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="682c0-124">Uri</span><span class="sxs-lookup"><span data-stu-id="682c0-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="682c0-125">.NET Framework での uniform resource identifier (Uri) を使用して表現された web アドレスの処理方法を指定する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="682c0-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="682c0-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="682c0-126">Remarks</span></span>  
 <span data-ttu-id="682c0-127">既定で、<xref:System.Uri?displayProperty=nameWithType>クラスのエスケープを解除パーセントは、パスの圧縮を実行する前にパスの区切り文字をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="682c0-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="682c0-128">これは、次のような攻撃に対するセキュリティ メカニズムとして実装されていました。</span><span class="sxs-lookup"><span data-stu-id="682c0-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="682c0-129">この URI が渡される場合は、モジュール % を処理しないエンコードした文字を正しく、サーバーで実行されている次のコマンドになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="682c0-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="682c0-130">このため、<xref:System.Uri?displayProperty=nameWithType>クラスの最初のエスケープを解除パス区切り記号とし、パスの圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="682c0-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="682c0-131">上への悪意のある URL を渡すことの結果<xref:System.Uri?displayProperty=nameWithType>クラスに次の URI のコンス トラクターの結果。</span><span class="sxs-lookup"><span data-stu-id="682c0-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="682c0-132">SchemeSettings の構成オプションを使用して、特定のスキームのないのエスケープを解除のパーセントでエンコードされたパス区切りには、この既定の動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="682c0-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="682c0-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="682c0-133">Configuration Files</span></span>  
 <span data-ttu-id="682c0-134">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="682c0-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="682c0-135">例</span><span class="sxs-lookup"><span data-stu-id="682c0-135">Example</span></span>  
 <span data-ttu-id="682c0-136">次の例で使用する構成を示しています、 <xref:System.Uri> http スキームのパスをパーセントでエンコードされた区切り記号をエスケープしないをサポートするクラス。</span><span class="sxs-lookup"><span data-stu-id="682c0-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="682c0-137">要素情報</span><span class="sxs-lookup"><span data-stu-id="682c0-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="682c0-138">名前空間</span><span class="sxs-lookup"><span data-stu-id="682c0-138">Namespace</span></span>|<span data-ttu-id="682c0-139">システム</span><span class="sxs-lookup"><span data-stu-id="682c0-139">System</span></span>|  
|<span data-ttu-id="682c0-140">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="682c0-140">Schema Name</span></span>||  
|<span data-ttu-id="682c0-141">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="682c0-141">Validation File</span></span>||  
|<span data-ttu-id="682c0-142">空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="682c0-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="682c0-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="682c0-143">See Also</span></span>  
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
- <xref:System.Uri?displayProperty=nameWithType>  
- [<span data-ttu-id="682c0-144">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="682c0-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
