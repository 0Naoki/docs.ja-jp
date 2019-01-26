---
title: '方法: DEVPATH を使用してアセンブリを検索します。'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 0d238ceb4f96905031cb4a30f50727050381277e
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084498"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="21620-102">方法: DEVPATH を使用してアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="21620-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="21620-103">開発者は、複数のアプリケーションの構築、共有アセンブリが正常に動作するかどうかを確認することがあります。</span><span class="sxs-lookup"><span data-stu-id="21620-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="21620-104">継続的に開発サイクル中にグローバル アセンブリ キャッシュにアセンブリを配置ではなく、開発者は、アセンブリのビルド出力ディレクトリを指す DEVPATH 環境変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="21620-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="21620-105">たとえば、MySharedAssembly と呼ばれる共有のアセンブリをビルドして、出力ディレクトリは C:\MySharedAssembly\Debug します。</span><span class="sxs-lookup"><span data-stu-id="21620-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="21620-106">DEVPATH 変数に C:\MySharedAssembly\Debug を配置することができます。</span><span class="sxs-lookup"><span data-stu-id="21620-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="21620-107">指定する必要がありますし、 [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)マシン構成ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="21620-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="21620-108">この要素は、アセンブリの検索に DEVPATH を使用する共通言語ランタイムを指示します。</span><span class="sxs-lookup"><span data-stu-id="21620-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="21620-109">共有アセンブリは、ランタイムによって探索可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="21620-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="21620-110">アセンブリ参照の使用を解決するためのプライベート ディレクトリを指定する、 [ \<codeBase > 要素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)または[ \<probing > 要素](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)」の説明に従って、構成ファイルで[アセンブリの場所を指定する](../../../docs/framework/configure-apps/specify-assembly-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="21620-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="21620-111">アプリケーション ディレクトリのサブディレクトリにアセンブリを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="21620-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="21620-112">詳細については、「 [ランタイムがアセンブリを検索する方法](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21620-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21620-113">これは、開発専用の高度な機能です。</span><span class="sxs-lookup"><span data-stu-id="21620-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="21620-114">次の例では、ランタイムが DEVPATH 環境変数で指定されたディレクトリでアセンブリを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="21620-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21620-115">例</span><span class="sxs-lookup"><span data-stu-id="21620-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="21620-116">この設定の既定値は false。</span><span class="sxs-lookup"><span data-stu-id="21620-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21620-117">開発時にのみ、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="21620-117">Use this setting only at development time.</span></span> <span data-ttu-id="21620-118">ランタイムは、DEVPATH に厳密な名前のアセンブリのバージョンをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="21620-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="21620-119">単に最初に見つかったアセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="21620-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21620-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="21620-120">See also</span></span>
- [<span data-ttu-id="21620-121">.NET Framework アプリの構成</span><span class="sxs-lookup"><span data-stu-id="21620-121">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
