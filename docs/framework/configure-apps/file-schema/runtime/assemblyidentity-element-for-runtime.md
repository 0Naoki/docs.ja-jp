---
title: '&lt;assemblyIdentity&gt;要素&lt;ランタイム&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 939e10e0c06e98f98e0c468358f4296fd1061a79
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593928"
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a><span data-ttu-id="9c16d-102">&lt;assemblyIdentity&gt;要素&lt;ランタイム&gt;</span><span class="sxs-lookup"><span data-stu-id="9c16d-102">&lt;assemblyIdentity&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="9c16d-103">アセンブリに関する識別情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c16d-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="9c16d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9c16d-104">\<configuration></span></span>  
<span data-ttu-id="9c16d-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="9c16d-105">\<runtime></span></span>  
<span data-ttu-id="9c16d-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="9c16d-106">\<assemblyBinding></span></span>  
<span data-ttu-id="9c16d-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="9c16d-107">\<dependentAssembly></span></span>  
<span data-ttu-id="9c16d-108">\<assemblyIdentity></span><span class="sxs-lookup"><span data-stu-id="9c16d-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c16d-109">構文</span><span class="sxs-lookup"><span data-stu-id="9c16d-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c16d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9c16d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9c16d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c16d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c16d-112">属性</span><span class="sxs-lookup"><span data-stu-id="9c16d-112">Attributes</span></span>  
  
|<span data-ttu-id="9c16d-113">属性</span><span class="sxs-lookup"><span data-stu-id="9c16d-113">Attribute</span></span>|<span data-ttu-id="9c16d-114">説明</span><span class="sxs-lookup"><span data-stu-id="9c16d-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="9c16d-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9c16d-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="9c16d-116">アセンブリの名前</span><span class="sxs-lookup"><span data-stu-id="9c16d-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="9c16d-117">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="9c16d-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9c16d-118">言語と国/地域のアセンブリを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="9c16d-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="9c16d-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="9c16d-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9c16d-120">アセンブリの厳密な名前を指定する 16 進値。</span><span class="sxs-lookup"><span data-stu-id="9c16d-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="9c16d-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="9c16d-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9c16d-122">いずれか、値"x86"、"amd64"、"msil"または"ia64"プロセッサ固有のコードを含むアセンブリのプロセッサ アーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c16d-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="9c16d-123">値小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="9c16d-123">The values are not case-sensitive.</span></span> <span data-ttu-id="9c16d-124">かどうか、属性が他の値、全体が割り当てられます`<assemblyIdentity>`要素は無視されます。</span><span class="sxs-lookup"><span data-stu-id="9c16d-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="9c16d-125">以下を参照してください。<xref:System.Reflection.ProcessorArchitecture></span><span class="sxs-lookup"><span data-stu-id="9c16d-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="9c16d-126">processorArchitecture の属性</span><span class="sxs-lookup"><span data-stu-id="9c16d-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="9c16d-127">[値]</span><span class="sxs-lookup"><span data-stu-id="9c16d-127">Value</span></span>|<span data-ttu-id="9c16d-128">説明</span><span class="sxs-lookup"><span data-stu-id="9c16d-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="9c16d-129">AMD の x86 アーキテクチャのみです。</span><span class="sxs-lookup"><span data-stu-id="9c16d-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="9c16d-130">Intel Itanium アーキテクチャの場合のみです。</span><span class="sxs-lookup"><span data-stu-id="9c16d-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="9c16d-131">プロセッサおよびワードあたりのビット数に関して中立です。</span><span class="sxs-lookup"><span data-stu-id="9c16d-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="9c16d-132">32 ビット x86 プロセッサ、ネイティブまたは 64 ビット プラットフォームでの Windows (WOW) 環境での Windows でします。</span><span class="sxs-lookup"><span data-stu-id="9c16d-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c16d-133">子要素</span><span class="sxs-lookup"><span data-stu-id="9c16d-133">Child Elements</span></span>  
 <span data-ttu-id="9c16d-134">なし。</span><span class="sxs-lookup"><span data-stu-id="9c16d-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c16d-135">親要素</span><span class="sxs-lookup"><span data-stu-id="9c16d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="9c16d-136">要素</span><span class="sxs-lookup"><span data-stu-id="9c16d-136">Element</span></span>|<span data-ttu-id="9c16d-137">説明</span><span class="sxs-lookup"><span data-stu-id="9c16d-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="9c16d-138">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c16d-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="9c16d-139">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9c16d-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="9c16d-140">各アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="9c16d-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="9c16d-141">1 つを使用して、`<dependentAssembly>`各アセンブリの要素。</span><span class="sxs-lookup"><span data-stu-id="9c16d-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="9c16d-142">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c16d-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c16d-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c16d-143">Remarks</span></span>  
 <span data-ttu-id="9c16d-144">すべて **\<dependentAssembly >** 要素が 1 つの **\<assemblyIdentity >** 子要素。</span><span class="sxs-lookup"><span data-stu-id="9c16d-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="9c16d-145">場合、`processorArchitecture`属性が存在する、`<assemblyIdentity>`要素は、対応するプロセッサ アーキテクチャを使用してアセンブリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c16d-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="9c16d-146">場合、`processorArchitecture`属性が存在しない、`<assemblyIdentity>`要素は、すべてのプロセッサ アーキテクチャを持つアセンブリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="9c16d-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="9c16d-147">次の例を対象に 2 つの 2 つの異なるプロセッサ アーキテクチャ、およびバージョンがない管理が同期して 2 つのアセンブリと同じ名前の構成ファイルを示しています。X86 では、アプリケーションが実行される場合、最初のプラットフォーム`<assemblyIdentity>`要素が適用され、その他は無視されます。</span><span class="sxs-lookup"><span data-stu-id="9c16d-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="9c16d-148">アプリケーションは、x86、または ia64 以外のプラットフォームで実行する場合は両方とも無視されます。</span><span class="sxs-lookup"><span data-stu-id="9c16d-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="9c16d-149">構成ファイルが含まれている場合、`<assemblyIdentity>`要素なしで`processorArchitecture`属性、およびプラットフォームでない要素に一致する要素が含まれていない、`processorArchitecture`属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="9c16d-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c16d-150">例</span><span class="sxs-lookup"><span data-stu-id="9c16d-150">Example</span></span>  
 <span data-ttu-id="9c16d-151">次の例では、アセンブリに関する情報を提供する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9c16d-151">The following example shows how to provide information about an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c16d-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c16d-152">See also</span></span>
- [<span data-ttu-id="9c16d-153">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9c16d-153">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9c16d-154">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="9c16d-154">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="9c16d-155">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="9c16d-155">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
