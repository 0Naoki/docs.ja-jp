---
title: '&lt;cryptoClasses&gt;要素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 671302003c3a1f3a37e1773aeeae9cb09a457d13
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "47215874"
---
# <a name="ltcryptoclassesgt-element"></a><span data-ttu-id="bcb34-102">&lt;cryptoClasses&gt;要素</span><span class="sxs-lookup"><span data-stu-id="bcb34-102">&lt;cryptoClasses&gt; Element</span></span>
<span data-ttu-id="bcb34-103">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="bcb34-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="bcb34-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bcb34-104">\<configuration></span></span>  
<span data-ttu-id="bcb34-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="bcb34-105">\<mscorlib></span></span>  
<span data-ttu-id="bcb34-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="bcb34-106">\<cryptographySettings></span></span>  
<span data-ttu-id="bcb34-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="bcb34-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="bcb34-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="bcb34-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcb34-109">構文</span><span class="sxs-lookup"><span data-stu-id="bcb34-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcb34-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bcb34-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bcb34-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bcb34-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcb34-112">属性</span><span class="sxs-lookup"><span data-stu-id="bcb34-112">Attributes</span></span>  
 <span data-ttu-id="bcb34-113">なし。</span><span class="sxs-lookup"><span data-stu-id="bcb34-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bcb34-114">子要素</span><span class="sxs-lookup"><span data-stu-id="bcb34-114">Child Elements</span></span>  
  
|<span data-ttu-id="bcb34-115">要素</span><span class="sxs-lookup"><span data-stu-id="bcb34-115">Element</span></span>|<span data-ttu-id="bcb34-116">説明</span><span class="sxs-lookup"><span data-stu-id="bcb34-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcb34-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="bcb34-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="bcb34-118">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスを含みます。</span><span class="sxs-lookup"><span data-stu-id="bcb34-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bcb34-119">親要素</span><span class="sxs-lookup"><span data-stu-id="bcb34-119">Parent Elements</span></span>  
  
|<span data-ttu-id="bcb34-120">要素</span><span class="sxs-lookup"><span data-stu-id="bcb34-120">Element</span></span>|<span data-ttu-id="bcb34-121">説明</span><span class="sxs-lookup"><span data-stu-id="bcb34-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bcb34-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="bcb34-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="bcb34-123">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="bcb34-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="bcb34-124">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="bcb34-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="bcb34-125">`cryptographySettings`要素を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="bcb34-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bcb34-126">例</span><span class="sxs-lookup"><span data-stu-id="bcb34-126">Example</span></span>  
 <span data-ttu-id="bcb34-127">次の例では、  **\<cryptoClass >** 暗号化クラスを参照して、ランタイムを構成する要素。</span><span class="sxs-lookup"><span data-stu-id="bcb34-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="bcb34-128">文字列"RSA"を渡すことができますし、<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドを使用して、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>を返すメソッドを`MyCryptoRSAClass`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bcb34-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcb34-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcb34-129">See Also</span></span>  
 <xref:System.Security.Cryptography>  
 [<span data-ttu-id="bcb34-130">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="bcb34-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="bcb34-131">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="bcb34-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="bcb34-132">暗号サービス</span><span class="sxs-lookup"><span data-stu-id="bcb34-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="bcb34-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="bcb34-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)  
 [<span data-ttu-id="bcb34-134">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="bcb34-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
