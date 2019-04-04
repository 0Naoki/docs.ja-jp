---
title: アセンブリの内容
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2be1aad4d222917364a57abc93b414af40b1e9ae
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675654"
---
# <a name="assembly-contents"></a><span data-ttu-id="1e614-102">アセンブリの内容</span><span class="sxs-lookup"><span data-stu-id="1e614-102">Assembly Contents</span></span>
<span data-ttu-id="1e614-103">一般に、静的アセンブリは次の 4 つの要素から構成されます。</span><span class="sxs-lookup"><span data-stu-id="1e614-103">In general, a static assembly can consist of four elements:</span></span>  
  
-   <span data-ttu-id="1e614-104">アセンブリ メタデータを保持する[アセンブリ マニフェスト](../../../docs/framework/app-domains/assembly-manifest.md)。</span><span class="sxs-lookup"><span data-stu-id="1e614-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
-   <span data-ttu-id="1e614-105">型メタデータ。</span><span class="sxs-lookup"><span data-stu-id="1e614-105">Type metadata.</span></span>  
  
-   <span data-ttu-id="1e614-106">型を実装する MSIL (Microsoft Intermediate Language) コード。</span><span class="sxs-lookup"><span data-stu-id="1e614-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
-   <span data-ttu-id="1e614-107">一連のリソース。</span><span class="sxs-lookup"><span data-stu-id="1e614-107">A set of resources.</span></span>  
  
 <span data-ttu-id="1e614-108">このうち必須なのはアセンブリ マニフェストだけですが、アセンブリになんらかの機能を与えるには、型またはリソースのいずれかが必要になります。</span><span class="sxs-lookup"><span data-stu-id="1e614-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="1e614-109">アセンブリのこれらの要素は、いくつかの方法でグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="1e614-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="1e614-110">1 つの方法として、次の図に示すように、すべての要素を 1 つの物理ファイルにまとめることができます。</span><span class="sxs-lookup"><span data-stu-id="1e614-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 ![MyAssembly.dll という名前のシングルファイル アセンブリを示す図。](./media/assembly-contents/single-file-assembly.gif)  
  
 <span data-ttu-id="1e614-112">別の方法として、1 つのアセンブリの要素を複数のファイルに分けることもできます。</span><span class="sxs-lookup"><span data-stu-id="1e614-112">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="1e614-113">この操作には、コンパイル済みコードのモジュール (.netmodule)、リソース (.bmp ファイルや .jpg ファイルなど)、アプリケーションで必要なその他のファイルなどを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e614-113">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="1e614-114">複数の言語で記述されたモジュールを組み合わせたり、使用頻度の低い型を必要なときにだけダウンロードされるモジュールに配置することでアプリケーションのダウンロードを最適化したりする場合は、マルチファイル アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e614-114">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="1e614-115">あるアプリケーションの開発において、特定のユーティリティ コードを独立したモジュールに配置し、サイズの大きいリソース ファイル (ここでは .bmp イメージ) を元のファイルに残しておく例を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1e614-115">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="1e614-116">.NET Framework では、ファイルが参照される場合にだけそのファイルがダウンロードされます。参照頻度の低いコードをアプリケーションとは別のファイルに保存することで、コードのダウンロードが最適化されます。</span><span class="sxs-lookup"><span data-stu-id="1e614-116">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 ![マルチファイル アセンブリを示す図。](./media/assembly-contents/multifile-assembly-diagram.gif) 
  
> [!NOTE]
>  <span data-ttu-id="1e614-118">マルチファイル アセンブリを構成する各ファイルは、ファイル システムによって物理的にリンクされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1e614-118">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="1e614-119">これらのファイルはアセンブリ マニフェストによってリンクされ、共通言語ランタイムがこれらのファイルをまとめて管理します。</span><span class="sxs-lookup"><span data-stu-id="1e614-119">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="1e614-120">この例では、MyAssembly.dll に含まれるアセンブリ マニフェストに記述されているように、3 つのファイルがすべて 1 つのアセンブリに属しています。</span><span class="sxs-lookup"><span data-stu-id="1e614-120">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="1e614-121">ファイル システムにとっては、これらは 3 つの独立したファイルです。</span><span class="sxs-lookup"><span data-stu-id="1e614-121">To the file system, they are three separate files.</span></span> <span data-ttu-id="1e614-122">Util.netmodule というファイルは、アセンブリ情報を含んでいないため、モジュールとしてコンパイルされています。</span><span class="sxs-lookup"><span data-stu-id="1e614-122">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="1e614-123">アセンブリの作成時に、アセンブリ マニフェストが MyAssembly.dll に追加され、その Util.netmodule および Graphic.bmp との関係が示されます。</span><span class="sxs-lookup"><span data-stu-id="1e614-123">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="1e614-124">ソース コードをデザインするときは、作成するアプリケーションの機能を 1 つのファイルにまとめるのか複数のファイルに分割するのか、分割する場合は機能をどのように分けるのかを明確に決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e614-124">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="1e614-125">.NET Framework コードをデザインする場合も同様に、機能を 1 つのアセンブリにまとめるのか複数のアセンブリに分割するのか、分割する場合は機能をどのように分割するのかを決めておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e614-125">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e614-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e614-126">See also</span></span>
- [<span data-ttu-id="1e614-127">共通言語ランタイムのアセンブリ</span><span class="sxs-lookup"><span data-stu-id="1e614-127">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="1e614-128">アセンブリ マニフェスト</span><span class="sxs-lookup"><span data-stu-id="1e614-128">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)
- [<span data-ttu-id="1e614-129">アセンブリのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1e614-129">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
