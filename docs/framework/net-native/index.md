---
title: .NET ネイティブによるアプリのコンパイル
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3c845cefad451c608f5c095e4941c3368dc9975
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650548"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="ff9da-102">.NET ネイティブによるアプリのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ff9da-102">Compiling Apps with .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="ff9da-103">Visual Studio 2015 と以降のバージョンに含まれているビルドと Windows アプリを展開するためのプリコンパイル テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="ff9da-103">is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="ff9da-104">マネージド コード (C# または Visual Basic) で記述された、.NET Framework および Windows 10 を対象とするアプリのリリース バージョンを自動的にネイティブ コードにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ff9da-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="ff9da-105">通常、.NET Framework を対象とするアプリは中間言語 (IL) にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="ff9da-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="ff9da-106">実行時に、Just-In-Time (JIT) コンパイラによって IL がネイティブ コードに変換されます。</span><span class="sxs-lookup"><span data-stu-id="ff9da-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="ff9da-107">これに対し、 [!INCLUDE[net_native](../../../includes/net-native-md.md)] は、Windows アプリを直接ネイティブ コードにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ff9da-107">In contrast, [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiles Windows apps directly to native code.</span></span> <span data-ttu-id="ff9da-108">開発者にとって、これは次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ff9da-108">For developers, this means:</span></span>  
  
- <span data-ttu-id="ff9da-109">ネイティブ コードのパフォーマンスをアプリに機能します。</span><span class="sxs-lookup"><span data-stu-id="ff9da-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="ff9da-110">通常、パフォーマンスは、まず IL にコンパイルされ、JIT コンパイラでネイティブ コードにコンパイルし、コードに優れたになります。</span><span class="sxs-lookup"><span data-stu-id="ff9da-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
- <span data-ttu-id="ff9da-111">引き続き C# または Visual Basic でプログラムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ff9da-111">You can continue to program in C# or Visual Basic.</span></span>  
  
- <span data-ttu-id="ff9da-112">クラス ライブラリ、自動メモリ管理とガベージ コレクション、例外処理など、.NET Framework で提供されるリソースを引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="ff9da-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="ff9da-113">アプリのユーザーにとっては、[!INCLUDE[net_native](../../../includes/net-native-md.md)]には次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="ff9da-113">For users of your apps, [!INCLUDE[net_native](../../../includes/net-native-md.md)] offers these advantages:</span></span>  
  
- <span data-ttu-id="ff9da-114">ほとんどのアプリやシナリオの実行時間が高速化します。</span><span class="sxs-lookup"><span data-stu-id="ff9da-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
- <span data-ttu-id="ff9da-115">アプリやシナリオの大半はスタートアップ時間が短くします。</span><span class="sxs-lookup"><span data-stu-id="ff9da-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
- <span data-ttu-id="ff9da-116">配置と更新コストが低い。</span><span class="sxs-lookup"><span data-stu-id="ff9da-116">Low deployment and update costs.</span></span>  
  
- <span data-ttu-id="ff9da-117">アプリのメモリ使用量を最適化します。</span><span class="sxs-lookup"><span data-stu-id="ff9da-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ff9da-118">大半のアプリおよびシナリオでは、.NET ネイティブは提供が大幅に高速起動時間、または NGEN イメージに IL にコンパイルされたアプリと比較して優れたパフォーマンスを発揮します。</span><span class="sxs-lookup"><span data-stu-id="ff9da-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="ff9da-119">ただし、結果は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff9da-119">However, your results may vary.</span></span> <span data-ttu-id="ff9da-120">アプリが .NET ネイティブのパフォーマンス向上による恩恵を受けていることを確認するには、.NET ネイティブ以外のバージョンのアプリのパフォーマンスを比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff9da-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="ff9da-121">詳細については、次を参照してください。[パフォーマンス セッションの概要](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview)します。</span><span class="sxs-lookup"><span data-stu-id="ff9da-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="ff9da-122">ただし、 [!INCLUDE[net_native](../../../includes/net-native-md.md)] では、ネイティブ コードへのコンパイル以上の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="ff9da-122">But [!INCLUDE[net_native](../../../includes/net-native-md.md)] involves more than a compilation to native code.</span></span> <span data-ttu-id="ff9da-123">.NET Framework アプリのビルド方法と実行方法が変更されます。</span><span class="sxs-lookup"><span data-stu-id="ff9da-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="ff9da-124">特に次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ff9da-124">In particular:</span></span>  
  
- <span data-ttu-id="ff9da-125">プリコンパイル時に、.NET Framework の必要な部分がアプリに静的にリンクされます。</span><span class="sxs-lookup"><span data-stu-id="ff9da-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="ff9da-126">これにより、アプリは .NET Framework のアプリ ローカルのライブラリを使用して実行でき、コンパイラはグローバル分析を実行してパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="ff9da-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="ff9da-127">その結果、.NET Framework の更新後であっても、アプリは常に高速に起動します。</span><span class="sxs-lookup"><span data-stu-id="ff9da-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
- <span data-ttu-id="ff9da-128">[!INCLUDE[net_native](../../../includes/net-native-md.md)]ランタイム静的プリコンパイル用が最適化され、ほとんどの場合よりも優れたパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ff9da-128">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="ff9da-129">同時に、開発者に役立つ主要なリフレクション機能もあります。</span><span class="sxs-lookup"><span data-stu-id="ff9da-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
- [!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="ff9da-130">は、静的プリコンパイル シナリオ用に最適化されている、C++ コンパイラと同じバックエンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ff9da-130">uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="ff9da-131">は、この表に示すように、内部で C++ と同じか類似のツールを使用しているため、マネージド コードの開発者に C++ のパフォーマンス上の利点を提供できます。</span><span class="sxs-lookup"><span data-stu-id="ff9da-131">is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|<span data-ttu-id="ff9da-132">C++</span><span class="sxs-lookup"><span data-stu-id="ff9da-132">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="ff9da-133">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ff9da-133">Libraries</span></span>|<span data-ttu-id="ff9da-134">.NET Framework + Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="ff9da-134">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="ff9da-135">Win32 + Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="ff9da-135">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="ff9da-136">コンパイラ</span><span class="sxs-lookup"><span data-stu-id="ff9da-136">Compiler</span></span>|<span data-ttu-id="ff9da-137">UTC 最適化コンパイラ</span><span class="sxs-lookup"><span data-stu-id="ff9da-137">UTC optimizing compiler</span></span>|<span data-ttu-id="ff9da-138">UTC 最適化コンパイラ</span><span class="sxs-lookup"><span data-stu-id="ff9da-138">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="ff9da-139">配置</span><span class="sxs-lookup"><span data-stu-id="ff9da-139">Deployed</span></span>|<span data-ttu-id="ff9da-140">実行可能バイナリ</span><span class="sxs-lookup"><span data-stu-id="ff9da-140">Ready-to-run binaries</span></span>|<span data-ttu-id="ff9da-141">実行可能バイナリ (ASM)</span><span class="sxs-lookup"><span data-stu-id="ff9da-141">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="ff9da-142">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ff9da-142">Runtime</span></span>|<span data-ttu-id="ff9da-143">MRT.dll (最小 CLR ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ff9da-143">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="ff9da-144">CRT.dll (C ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ff9da-144">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="ff9da-145">Windows 10 用の Windows アプリの場合は、.NET ネイティブ コード コンパイル バイナリをアプリ パッケージ (.appx ファイル) に入れて Windows ストアにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ff9da-145">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff9da-146">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ff9da-146">In This Section</span></span>  
 <span data-ttu-id="ff9da-147">.NET ネイティブ コード コンパイルを使用したアプリ開発の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff9da-147">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
- [<span data-ttu-id="ff9da-148">.NET ネイティブの概要</span><span class="sxs-lookup"><span data-stu-id="ff9da-148">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- <span data-ttu-id="ff9da-149">[.NET ネイティブとコンパイル:](../../../docs/framework/net-native/net-native-and-compilation.md)どのネイティブ コードに、プロジェクトのコンパイルは .NET ネイティブのようにします。</span><span class="sxs-lookup"><span data-stu-id="ff9da-149">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
- [<span data-ttu-id="ff9da-150">リフレクションおよび .NET ネイティブ</span><span class="sxs-lookup"><span data-stu-id="ff9da-150">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    - [<span data-ttu-id="ff9da-151">リフレクションに依存する API</span><span class="sxs-lookup"><span data-stu-id="ff9da-151">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    - [<span data-ttu-id="ff9da-152">リフレクション API リファレンス</span><span class="sxs-lookup"><span data-stu-id="ff9da-152">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [<span data-ttu-id="ff9da-153">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="ff9da-153">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- [<span data-ttu-id="ff9da-154">シリアル化とメタデータ</span><span class="sxs-lookup"><span data-stu-id="ff9da-154">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
- [<span data-ttu-id="ff9da-155">Windows ストア アプリの .NET ネイティブへの移行</span><span class="sxs-lookup"><span data-stu-id="ff9da-155">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
- [<span data-ttu-id="ff9da-156">.NET ネイティブの一般的なトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ff9da-156">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
