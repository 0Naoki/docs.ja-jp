---
title: .NET Framework の開発ガイド
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, development guide
ms.assetid: 26e3d285-24c3-435c-a797-9fe5affb8525
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a21f4cd8657a9d2c26ac481e7f2b00e6a2f502c9
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581104"
---
# <a name="net-framework-development-guide"></a><span data-ttu-id="5a1a2-102">.NET Framework の開発ガイド</span><span class="sxs-lookup"><span data-stu-id="5a1a2-102">.NET Framework Development Guide</span></span>
<span data-ttu-id="5a1a2-103">ここでは、.NET Framework アプリの作成、構成、デバッグ、保護、および配置を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-103">This section explains how to create, configure, debug, secure, and deploy your .NET Framework apps.</span></span> <span data-ttu-id="5a1a2-104">また、動的プログラミング、相互運用性、拡張性、メモリ管理、スレッド処理などの技術領域に関する情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-104">The section also provides information about technology areas such as dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a1a2-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5a1a2-105">In This Section</span></span>  
 [<span data-ttu-id="5a1a2-106">アプリケーションの基本事項</span><span class="sxs-lookup"><span data-stu-id="5a1a2-106">Application Essentials</span></span>](../../docs/standard/application-essentials.md)  
 <span data-ttu-id="5a1a2-107">アプリ ドメインとアセンブリを利用したプログラミング、属性の使用、基本型の書式指定と解析、コレクションの使用、イベントおよび例外の処理、ファイルおよびデータ ストリームの使用、ジェネリックの使用など、基本的なアプリ開発タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-107">Provides information about basic app development tasks, such as programming with app domains and assemblies, using attributes, formatting and parsing base types, using collections, handling events and exceptions, using files and data streams, and using generics.</span></span>  
  
 [<span data-ttu-id="5a1a2-108">データとモデリング</span><span class="sxs-lookup"><span data-stu-id="5a1a2-108">Data and Modeling</span></span>](../../docs/framework/data/index.md)  
 <span data-ttu-id="5a1a2-109">ADO.NET、統合言語クエリ (LINQ: Language-Integrated Query)、WCF Data Services、および XML を使用してデータにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-109">Provides information about how to access data using ADO.NET, Language Integrated Query (LINQ), WCF Data Services, and XML.</span></span>  
  
 [<span data-ttu-id="5a1a2-110">クライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5a1a2-110">Client Applications</span></span>](../../docs/framework/develop-client-apps.md)  
 <span data-ttu-id="5a1a2-111">Windows Presentation Foundation (WPF) または Windows フォームを使用して Windows ベースのアプリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-111">Explains how to create Windows-based apps by using Windows Presentation Foundation (WPF) or Windows Forms.</span></span>  
  
 [<span data-ttu-id="5a1a2-112">ASP.NET を使用した Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5a1a2-112">Web Applications with ASP.NET</span></span>](../../docs/framework/develop-web-apps-with-aspnet.md)  
 <span data-ttu-id="5a1a2-113">ASP.NET を使用して最小限のコーディングでエンタープライズ クラスの Web アプリケーションを構築する方法に関する情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-113">Provides links to information about using ASP.NET to build enterprise-class web apps with a minimum of coding.</span></span>  
  
 [<span data-ttu-id="5a1a2-114">WCF を使用したサービス指向アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5a1a2-114">Service-Oriented Applications with WCF</span></span>](../../docs/framework/wcf/index.md)  
 <span data-ttu-id="5a1a2-115">Windows Communication Foundation (WCF) を使用して、安全で信頼できるサービス指向のアプリを構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-115">Describes how to use Windows Communication Foundation (WCF) to build service-oriented apps that are secure and reliable.</span></span>  
  
 <span data-ttu-id="5a1a2-116">[Windows Workflow Foundation でワークフローを構築する](windows-workflow-foundation/index.md)   </span><span class="sxs-lookup"><span data-stu-id="5a1a2-116">[Building workflows with Windows Workflow Foundation](windows-workflow-foundation/index.md)   </span></span>  
 <span data-ttu-id="5a1a2-117">Windows Workflow Foundation (WF) を使用するためのプログラミング モデル、サンプル、およびツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-117">Provides information about the programming model, samples, and tools for using Windows Workflow Foundation (WF).</span></span>  

 [<span data-ttu-id="5a1a2-118">Windows サービス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5a1a2-118">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)  
 <span data-ttu-id="5a1a2-119">Visual Studio および .NET Framework を使用して、サービスとしてインストールされるアプリを作成し、その動作を開始、停止、制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-119">Explains how you can use Visual Studio and the .NET Framework to create an app that is installed as a service, and start, stop, and otherwise control its behavior.</span></span>  
  
 [<span data-ttu-id="5a1a2-120">.NET での並列処理、コンカレンシー、および非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="5a1a2-120">Parallel Processing, Concurrency, and Async Programming in .NET</span></span>](../../docs/standard/parallel-processing-and-concurrency.md)  
 <span data-ttu-id="5a1a2-121">マネージド スレッド処理、並列プログラミング、および非同期プログラミングのデザイン パターンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-121">Provides information about managed threading, parallel programming, and asynchronous programming design patterns.</span></span>  
  
 [<span data-ttu-id="5a1a2-122">.NET Framework のネットワーク プログラミング</span><span class="sxs-lookup"><span data-stu-id="5a1a2-122">Network Programming in the .NET Framework</span></span>](../../docs/framework/network-programming/index.md)  
 <span data-ttu-id="5a1a2-123">アプリにすばやく簡単に統合できる、複数層の拡張可能なインターネット サービスのマネージド実装について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-123">Describes the layered, extensible, and managed implementation of Internet services that you can quickly and easily integrate into your apps.</span></span>  
  
 <span data-ttu-id="5a1a2-124">[.NET Framework アプリの構成](configure-apps/index.md)  </span><span class="sxs-lookup"><span data-stu-id="5a1a2-124">[Configuring .NET Framework Apps](configure-apps/index.md)  </span></span>  
 <span data-ttu-id="5a1a2-125">構成ファイルを使用して、.NET Framework アプリを再コンパイルすることなく設定を変更する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-125">Explains how you can use configuration files to change settings without having to recompile your .NET Framework apps.</span></span>  
  
 [<span data-ttu-id="5a1a2-126">.NET ネイティブによるアプリのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5a1a2-126">Compiling Apps with .NET Native</span></span>](../../docs/framework/net-native/index.md)  
 <span data-ttu-id="5a1a2-127">[!INCLUDE[net_native](../../includes/net-native-md.md)] プリコンパイル テクノロジを使用して、Windows ストア アプリをビルドおよび配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-127">Explains how you can use the [!INCLUDE[net_native](../../includes/net-native-md.md)] precompilation technology to build and deploy Windows Store apps.</span></span> [!INCLUDE[net_native](../../includes/net-native-md.md)]<span data-ttu-id="5a1a2-128"> は、マネージド コード (C#) で記述され、.NET Framework を対象とするアプリをネイティブ コードにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-128"> compiles apps that are written in managed code (C#) and that target the .NET Framework to native code.</span></span>  
  
 [<span data-ttu-id="5a1a2-129">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="5a1a2-129">Security</span></span>](../../docs/standard/security/index.md)  
 <span data-ttu-id="5a1a2-130">.NET Framework において安全なアプリの開発を促進するクラスおよびサービスに関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-130">Provides information about the classes and services in the .NET Framework that facilitate secure app development.</span></span>  
  
 [<span data-ttu-id="5a1a2-131">デバッグ、トレース、およびプロファイリング</span><span class="sxs-lookup"><span data-stu-id="5a1a2-131">Debugging, Tracing, and Profiling</span></span>](../../docs/framework/debug-trace-profile/index.md)  
 <span data-ttu-id="5a1a2-132">.NET Framework アプリとアプリ環境のテスト、最適化、およびプロファイリングを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-132">Explains how to test, optimize, and profile .NET Framework apps and the app environment.</span></span> <span data-ttu-id="5a1a2-133">開発者向けの情報だけでなく、管理者向けの情報も記載されています。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-133">This section includes information for administrators as well as developers.</span></span>  
  
 [<span data-ttu-id="5a1a2-134">複数のプラットフォームの開発</span><span class="sxs-lookup"><span data-stu-id="5a1a2-134">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
 <span data-ttu-id="5a1a2-135">.NET Framework を使用して複数のプラットフォームおよび複数のデバイス (電話、デスクトップ、Web など) で共有できるアセンブリを作成する方法に関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-135">Provides information about how you can use the .NET Framework to build assemblies that can be shared across multiple platforms and multiple devices such as phones, desktop, and web.</span></span>  
  
 [<span data-ttu-id="5a1a2-136">配置</span><span class="sxs-lookup"><span data-stu-id="5a1a2-136">Deployment</span></span>](../../docs/framework/deployment/index.md)  
 <span data-ttu-id="5a1a2-137">.NET Framework アプリをパッケージ化して配布する方法を説明します。開発者および管理者向けの配置ガイドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-137">Explains how to package and distribute your .NET Framework app, and includes deployment guides for both developers and administrators.</span></span>  
  
 [<span data-ttu-id="5a1a2-138">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="5a1a2-138">Performance</span></span>](../../docs/framework/performance/index.md)  
 <span data-ttu-id="5a1a2-139">キャッシュ、遅延初期化、信頼性、および ETW イベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-139">Provides information about caching, lazy initialization, reliability, and ETW events.</span></span>  
 
## <a name="reference"></a><span data-ttu-id="5a1a2-140">参照</span><span class="sxs-lookup"><span data-stu-id="5a1a2-140">Reference</span></span>  
 [<span data-ttu-id="5a1a2-141">.NET Framework クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="5a1a2-141">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.7)  
 <span data-ttu-id="5a1a2-142">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] の名前空間に含まれる各クラスの構文、コード例、および使用情報を示します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-142">Supplies syntax, code examples, and usage information for each class that is contained in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5a1a2-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a1a2-143">Related Sections</span></span>  
 [<span data-ttu-id="5a1a2-144">はじめに</span><span class="sxs-lookup"><span data-stu-id="5a1a2-144">Getting Started</span></span>](../../docs/framework/get-started/index.md)  
 <span data-ttu-id="5a1a2-145">.NET Framework の包括的な概要と、追加リソースへのリンクを説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-145">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
 [<span data-ttu-id="5a1a2-146">新機能</span><span class="sxs-lookup"><span data-stu-id="5a1a2-146">What's New</span></span>](../../docs/framework/whats-new/index.md)  
 <span data-ttu-id="5a1a2-147">最新バージョンの .NET Framework の主要な新機能と変更点について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-147">Describes key new features and changes in the latest version of the .NET Framework.</span></span> <span data-ttu-id="5a1a2-148">新旧の型とメンバーのリストを含み、.NET Framework の以前のバージョンからアプリを移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-148">Includes lists of new and obsolete types and members, and provides a guide for migrating your apps from the previous version of the .NET Framework.</span></span>  
  
 [<span data-ttu-id="5a1a2-149">ツール</span><span class="sxs-lookup"><span data-stu-id="5a1a2-149">Tools</span></span>](../../docs/framework/tools/index.md)  
 <span data-ttu-id="5a1a2-150">.NET Framework テクノロジを使ってアプリを開発、構成、配置するのに役立つツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-150">Describes the tools that help you develop, configure, and deploy apps by using .NET Framework technologies.</span></span>  
  
 [<span data-ttu-id="5a1a2-151">.NET Framework のサンプル</span><span class="sxs-lookup"><span data-stu-id="5a1a2-151">.NET Framework Samples</span></span>](https://msdn.microsoft.com/library/177055f8-4a1f-43e7-aee6-995c196079b1)  
 <span data-ttu-id="5a1a2-152">.NET Framework のテクノロジを紹介するサンプル アプリを参照できる MSDN コード サンプル ギャラリーへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="5a1a2-152">Provides links to the MSDN Code Samples Gallery for sample apps that demonstrate .NET Framework technologies.</span></span>
