---
title: CLR ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d64ee6942d9397ceb45b812ef3c26179fac9b2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540300"
---
# <a name="clr-etw-events"></a><span data-ttu-id="8565c-102">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-102">CLR ETW Events</span></span>
<span data-ttu-id="8565c-103">このセクションのトピックでは、Windows イベント トレーシング (ETW) イベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8565c-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="8565c-104">各イベントは、キーワードとレベルに関連付けられています。詳細については、「[CLR ETW のキーワードとレベル](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8565c-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="8565c-105">CLR には、イベントのプロバイダーが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="8565c-105">The CLR has two providers for the events:</span></span>  
  
-   <span data-ttu-id="8565c-106">ランタイム プロバイダー。有効になっているキーワードに応じてイベントを発生させます (キーワードとはイベントのカテゴリです)。</span><span class="sxs-lookup"><span data-stu-id="8565c-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="8565c-107">CLR ランタイム プロバイダーの GUID は e13c0d23-ccbc-4e12-931b-d9cc2eee27e4 です。</span><span class="sxs-lookup"><span data-stu-id="8565c-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
-   <span data-ttu-id="8565c-108">ランダウン プロバイダー。特殊な用途があります。</span><span class="sxs-lookup"><span data-stu-id="8565c-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="8565c-109">CLR ランダウン プロバイダーの GUID は a669021c-c450-4609-a035-5af59af4df18 です。</span><span class="sxs-lookup"><span data-stu-id="8565c-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="8565c-110">プロバイダーの詳細については、「[CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md)」(CLR ETW プロバイダー) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8565c-110">For more information about the providers, see [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8565c-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8565c-111">In This Section</span></span>  
 [<span data-ttu-id="8565c-112">ランタイム情報イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-112">Runtime Information Events</span></span>](../../../docs/framework/performance/runtime-information-etw-events.md)  
 <span data-ttu-id="8565c-113">SKU、バージョン番号、アクティブ化の方法、起動時に使用されたコマンド ライン パラメーター、GUID (該当する場合) などのランタイムに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="8565c-114">Exception Thrown_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-114">Exception Thrown_V1 Event</span></span>](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="8565c-115">スローされる例外に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="8565c-116">競合イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-116">Contention Events</span></span>](../../../docs/framework/performance/contention-etw-events.md)  
 <span data-ttu-id="8565c-117">ランタイムが使用するモニター ロックまたはネイティブ ロックの競合に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="8565c-118">スレッド プール イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-118">Thread Pool Events</span></span>](../../../docs/framework/performance/thread-pool-etw-events.md)  
 <span data-ttu-id="8565c-119">ワーカー スレッド プールと I/O スレッド プールに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="8565c-120">ローダー イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-120">Loader Events</span></span>](../../../docs/framework/performance/loader-etw-events.md)  
 <span data-ttu-id="8565c-121">アプリケーションのドメイン、アセンブリ、およびモジュールのロードとアンロードに関連する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="8565c-122">メソッド イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-122">Method Events</span></span>](../../../docs/framework/performance/method-etw-events.md)  
 <span data-ttu-id="8565c-123">CLR メソッド シンボルの解決に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="8565c-124">ガベージ コレクション イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-124">Garbage Collection Events</span></span>](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 <span data-ttu-id="8565c-125">診断とデバッグに役立つガベージ コレクションに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="8565c-126">JIT トレース イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-126">JIT Tracing Events</span></span>](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 <span data-ttu-id="8565c-127">Just-In-Time (JIT) インライン展開と末尾呼び出しに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="8565c-128">相互運用イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-128">Interop Events</span></span>](../../../docs/framework/performance/interop-etw-events.md)  
 <span data-ttu-id="8565c-129">Microsoft intermediate language (MSIL) のスタブ生成とキャッシュに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="8565c-130">ARM のイベント</span><span class="sxs-lookup"><span data-stu-id="8565c-130">ARM Events</span></span>](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="8565c-131">アプリケーション ドメインの状態に関する詳細な診断情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="8565c-132">セキュリティ イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-132">Security Events</span></span>](../../../docs/framework/performance/security-etw-events.md)  
 <span data-ttu-id="8565c-133">厳密な名前と Authenticode の検証に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="8565c-134">スタック イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-134">Stack Event</span></span>](../../../docs/framework/performance/stack-etw-event.md)  
 <span data-ttu-id="8565c-135">イベントが発生した後に、他のイベントでスタック トレースの生成に使用された情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8565c-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8565c-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="8565c-136">See also</span></span>
- [<span data-ttu-id="8565c-137">デバッグの向上およびパフォーマンス調整 ETW を</span><span class="sxs-lookup"><span data-stu-id="8565c-137">Improve Debugging And Performance Tuning With ETW</span></span>](https://go.microsoft.com/fwlink/?LinkId=179696)
- [<span data-ttu-id="8565c-138">Windows のパフォーマンスに関するブログ</span><span class="sxs-lookup"><span data-stu-id="8565c-138">Windows Performance Blog</span></span>](https://go.microsoft.com/fwlink/?LinkId=179509)
- [<span data-ttu-id="8565c-139">.NET Framework のログ記録の制御</span><span class="sxs-lookup"><span data-stu-id="8565c-139">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)
- [<span data-ttu-id="8565c-140">CLR ETW プロバイダー</span><span class="sxs-lookup"><span data-stu-id="8565c-140">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)
- [<span data-ttu-id="8565c-141">CLR ETW キーワードおよびレベル</span><span class="sxs-lookup"><span data-stu-id="8565c-141">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="8565c-142">共通言語ランタイムの ETW イベント</span><span class="sxs-lookup"><span data-stu-id="8565c-142">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
