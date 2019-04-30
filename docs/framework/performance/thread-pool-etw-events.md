---
title: スレッド プール ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: caacee591c4df8389cea241916618f50da56b22b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949163"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="2d830-102">スレッド プール ETW イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-102">Thread Pool ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="2d830-103">これらのイベントは、ワーカー スレッドと I/O スレッドに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="2d830-103">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="2d830-104">スレッド プール イベントには 2 つのグループがあります。</span><span class="sxs-lookup"><span data-stu-id="2d830-104">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="2d830-105">[ワーカー スレッド プール イベント](#worker)は、アプリケーションがどのようにスレッド プールを使用するかに関する情報と、コンカレンシー制御におけるワークロードの効果に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2d830-105">[Worker thread pool events](#worker), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="2d830-106">[I/O スレッド プール イベント](#io)は、スレッド プールで作成、無効化、無効化解除、または終了した I/O スレッドに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2d830-106">[I/O thread pool events](#io), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  
  
<a name="worker"></a>   
## <a name="worker-thread-pool-events"></a><span data-ttu-id="2d830-107">ワーカー スレッド プール イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-107">Worker Thread Pool Events</span></span>  
 <span data-ttu-id="2d830-108">これらのイベントは、ランタイムのワーカー スレッドのプールに関連付けられており、スレッド イベントに関する通知 (スレッドが作成されたり停止されたりした場合など) を提供します。</span><span class="sxs-lookup"><span data-stu-id="2d830-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="2d830-109">ワーカー スレッド プールは、スレッドの数が計測されたスループットに基づいて計算されるアダプティブ アルゴリズムを使用して、コンカレンシー制御を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d830-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="2d830-110">ワーカー スレッド プール イベントを使用すると、アプリケーションで使用されるスレッド プールの様子や特定のワークロードがコンカレンシー制御に与える影響などを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="2d830-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="2d830-111">ThreadPoolWorkerThreadStart および ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="2d830-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="2d830-112">次の表に、これらのイベントのキーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="2d830-113">(詳細については、「 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="2d830-113">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="2d830-114">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="2d830-114">Keyword for raising the event</span></span>|<span data-ttu-id="2d830-115">レベル</span><span class="sxs-lookup"><span data-stu-id="2d830-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2d830-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2d830-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2d830-117">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="2d830-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="2d830-118">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2d830-119">イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-119">Event</span></span>|<span data-ttu-id="2d830-120">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d830-120">Event ID</span></span>|<span data-ttu-id="2d830-121">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="2d830-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="2d830-122">50</span><span class="sxs-lookup"><span data-stu-id="2d830-122">50</span></span>|<span data-ttu-id="2d830-123">ワーカー スレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="2d830-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="2d830-124">51</span><span class="sxs-lookup"><span data-stu-id="2d830-124">51</span></span>|<span data-ttu-id="2d830-125">ワーカー スレッドが停止された。</span><span class="sxs-lookup"><span data-stu-id="2d830-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="2d830-126">52</span><span class="sxs-lookup"><span data-stu-id="2d830-126">52</span></span>|<span data-ttu-id="2d830-127">ワーカー スレッドが無効にされた。</span><span class="sxs-lookup"><span data-stu-id="2d830-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="2d830-128">53</span><span class="sxs-lookup"><span data-stu-id="2d830-128">53</span></span>|<span data-ttu-id="2d830-129">提供終了になったワーカー スレッドが再びアクティブになった。</span><span class="sxs-lookup"><span data-stu-id="2d830-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="2d830-130">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2d830-131">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2d830-131">Field name</span></span>|<span data-ttu-id="2d830-132">データ型</span><span class="sxs-lookup"><span data-stu-id="2d830-132">Data type</span></span>|<span data-ttu-id="2d830-133">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2d830-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="2d830-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="2d830-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2d830-135">win:UInt32</span></span>|<span data-ttu-id="2d830-136">作業の処理に使用可能なワーカー スレッド (既に作業の処理中のもの含む) の数。</span><span class="sxs-lookup"><span data-stu-id="2d830-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="2d830-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="2d830-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="2d830-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2d830-138">win:UInt32</span></span>|<span data-ttu-id="2d830-139">作業の処理に使用できないものの、後にさらに多くのスレッドが必要になった場合に備えて予約されているワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="2d830-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="2d830-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2d830-140">ClrInstanceID</span></span>|<span data-ttu-id="2d830-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2d830-141">Win:UInt16</span></span>|<span data-ttu-id="2d830-142">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="2d830-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="2d830-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="2d830-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="2d830-144">これらのスレッド プール イベントは、スレッドの挿入 (コンカレンシー制御) アルゴリズムの動作を理解したりデバッグしたりするための情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2d830-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="2d830-145">この情報は、ワーカー スレッド プールによって内部で使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d830-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="2d830-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="2d830-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="2d830-147">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2d830-148">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="2d830-148">Keyword for raising the event</span></span>|<span data-ttu-id="2d830-149">レベル</span><span class="sxs-lookup"><span data-stu-id="2d830-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2d830-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2d830-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2d830-151">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="2d830-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="2d830-152">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2d830-153">イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-153">Event</span></span>|<span data-ttu-id="2d830-154">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d830-154">Event ID</span></span>|<span data-ttu-id="2d830-155">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="2d830-156">54</span><span class="sxs-lookup"><span data-stu-id="2d830-156">54</span></span>|<span data-ttu-id="2d830-157">1 つのサンプルの情報のコレクションを参照します。つまり、特定のコンカレンシー レベルの特定の時刻におけるスループットの測定値です。</span><span class="sxs-lookup"><span data-stu-id="2d830-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="2d830-158">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2d830-159">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2d830-159">Field name</span></span>|<span data-ttu-id="2d830-160">データ型</span><span class="sxs-lookup"><span data-stu-id="2d830-160">Data type</span></span>|<span data-ttu-id="2d830-161">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2d830-162">スループット</span><span class="sxs-lookup"><span data-stu-id="2d830-162">Throughput</span></span>|<span data-ttu-id="2d830-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-163">win:Double</span></span>|<span data-ttu-id="2d830-164">時間の単位あたりの入力候補の数です。</span><span class="sxs-lookup"><span data-stu-id="2d830-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="2d830-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2d830-165">ClrInstanceID</span></span>|<span data-ttu-id="2d830-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2d830-166">Win:UInt16</span></span>|<span data-ttu-id="2d830-167">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="2d830-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="2d830-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="2d830-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="2d830-169">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2d830-170">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="2d830-170">Keyword for raising the event</span></span>|<span data-ttu-id="2d830-171">レベル</span><span class="sxs-lookup"><span data-stu-id="2d830-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2d830-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2d830-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2d830-173">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="2d830-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="2d830-174">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2d830-175">イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-175">Event</span></span>|<span data-ttu-id="2d830-176">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d830-176">Event ID</span></span>|<span data-ttu-id="2d830-177">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="2d830-178">55</span><span class="sxs-lookup"><span data-stu-id="2d830-178">55</span></span>|<span data-ttu-id="2d830-179">スレッドの挿入 (山登り法) アルゴリズムが、コンカレンシー レベルに変更があったと判断した場合に、コントロールの変更を記録します。</span><span class="sxs-lookup"><span data-stu-id="2d830-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="2d830-180">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2d830-181">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2d830-181">Field name</span></span>|<span data-ttu-id="2d830-182">データ型</span><span class="sxs-lookup"><span data-stu-id="2d830-182">Data type</span></span>|<span data-ttu-id="2d830-183">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2d830-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="2d830-184">AverageThroughput</span></span>|<span data-ttu-id="2d830-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-185">win:Double</span></span>|<span data-ttu-id="2d830-186">計測のサンプルの平均のスループット。</span><span class="sxs-lookup"><span data-stu-id="2d830-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="2d830-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="2d830-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="2d830-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2d830-188">win:UInt32</span></span>|<span data-ttu-id="2d830-189">新しいアクティブなワーカー スレッド数。</span><span class="sxs-lookup"><span data-stu-id="2d830-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="2d830-190">理由</span><span class="sxs-lookup"><span data-stu-id="2d830-190">Reason</span></span>|<span data-ttu-id="2d830-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2d830-191">win:UInt32</span></span>|<span data-ttu-id="2d830-192">調整の理由。</span><span class="sxs-lookup"><span data-stu-id="2d830-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="2d830-193">0x00 - ウォーム アップ。</span><span class="sxs-lookup"><span data-stu-id="2d830-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="2d830-194">0x01 - 初期化。</span><span class="sxs-lookup"><span data-stu-id="2d830-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="2d830-195">0x02 - ランダムな移動。</span><span class="sxs-lookup"><span data-stu-id="2d830-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="2d830-196">0x03 - 上昇移動。</span><span class="sxs-lookup"><span data-stu-id="2d830-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="2d830-197">0x04 - 変更点。</span><span class="sxs-lookup"><span data-stu-id="2d830-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="2d830-198">0x05 - 安定化。</span><span class="sxs-lookup"><span data-stu-id="2d830-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="2d830-199">0x06 - 不足。</span><span class="sxs-lookup"><span data-stu-id="2d830-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="2d830-200">0x07 - スレッドのタイムアウト。</span><span class="sxs-lookup"><span data-stu-id="2d830-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="2d830-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2d830-201">ClrInstanceID</span></span>|<span data-ttu-id="2d830-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2d830-202">Win:UInt16</span></span>|<span data-ttu-id="2d830-203">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="2d830-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="2d830-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="2d830-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="2d830-205">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2d830-206">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="2d830-206">Keyword for raising the event</span></span>|<span data-ttu-id="2d830-207">レベル</span><span class="sxs-lookup"><span data-stu-id="2d830-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2d830-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2d830-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2d830-209">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="2d830-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="2d830-210">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2d830-211">イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-211">Event</span></span>|<span data-ttu-id="2d830-212">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d830-212">Event ID</span></span>|<span data-ttu-id="2d830-213">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="2d830-214">56</span><span class="sxs-lookup"><span data-stu-id="2d830-214">56</span></span>|<span data-ttu-id="2d830-215">スレッド プールに関するデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="2d830-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="2d830-216">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2d830-217">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2d830-217">Field name</span></span>|<span data-ttu-id="2d830-218">データ型</span><span class="sxs-lookup"><span data-stu-id="2d830-218">Data type</span></span>|<span data-ttu-id="2d830-219">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2d830-220">期間</span><span class="sxs-lookup"><span data-stu-id="2d830-220">Duration</span></span>|<span data-ttu-id="2d830-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-221">win:Double</span></span>|<span data-ttu-id="2d830-222">これらの統計情報が収集される時間数 (秒)。</span><span class="sxs-lookup"><span data-stu-id="2d830-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="2d830-223">スループット</span><span class="sxs-lookup"><span data-stu-id="2d830-223">Throughput</span></span>|<span data-ttu-id="2d830-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-224">win:Double</span></span>|<span data-ttu-id="2d830-225">この間隔中の 1 秒あたりの入力候補の平均数。</span><span class="sxs-lookup"><span data-stu-id="2d830-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="2d830-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="2d830-226">ThreadWave</span></span>|<span data-ttu-id="2d830-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-227">win:Double</span></span>|<span data-ttu-id="2d830-228">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="2d830-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="2d830-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="2d830-229">ThroughputWave</span></span>|<span data-ttu-id="2d830-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-230">win:Double</span></span>|<span data-ttu-id="2d830-231">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="2d830-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="2d830-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="2d830-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="2d830-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-233">win:Double</span></span>|<span data-ttu-id="2d830-234">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="2d830-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="2d830-235">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="2d830-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="2d830-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-236">win:Double</span></span>|<span data-ttu-id="2d830-237">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="2d830-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="2d830-238">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="2d830-238">ThroughputRatio</span></span>|<span data-ttu-id="2d830-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-239">win:Double</span></span>|<span data-ttu-id="2d830-240">この間隔中にアクティブなワーカー スレッドの数の変動によって引き起こされる、スループットの相対的な向上。</span><span class="sxs-lookup"><span data-stu-id="2d830-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="2d830-241">信頼度</span><span class="sxs-lookup"><span data-stu-id="2d830-241">Confidence</span></span>|<span data-ttu-id="2d830-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-242">win:Double</span></span>|<span data-ttu-id="2d830-243">ThroughputRatio フィールドの有効性の測定結果。</span><span class="sxs-lookup"><span data-stu-id="2d830-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="2d830-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="2d830-244">NewcontrolSetting</span></span>|<span data-ttu-id="2d830-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="2d830-245">win:Double</span></span>|<span data-ttu-id="2d830-246">アクティブなスレッド数の将来のバリエーションのベースラインとして使用するアクティブなワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="2d830-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="2d830-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="2d830-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="2d830-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2d830-248">Win:UInt16</span></span>|<span data-ttu-id="2d830-249">アクティブなスレッド数の、将来のバリエーションの大きさを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d830-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="2d830-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2d830-250">ClrInstanceID</span></span>|<span data-ttu-id="2d830-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2d830-251">Win:UInt16</span></span>|<span data-ttu-id="2d830-252">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="2d830-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2d830-253">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="2d830-253">Back to top</span></span>](#top)  
  
<a name="io"></a>   
## <a name="io-thread-events"></a><span data-ttu-id="2d830-254">I/O スレッド イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-254">I/O Thread Events</span></span>  
 <span data-ttu-id="2d830-255">これらのスレッド プール イベントは、I/O スレッド プール (完了ポート) にあるスレッドで発生します。これは非同期です。</span><span class="sxs-lookup"><span data-stu-id="2d830-255">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreatev1"></a><span data-ttu-id="2d830-256">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="2d830-256">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="2d830-257">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-257">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2d830-258">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="2d830-258">Keyword for raising the event</span></span>|<span data-ttu-id="2d830-259">レベル</span><span class="sxs-lookup"><span data-stu-id="2d830-259">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2d830-260">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2d830-260">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2d830-261">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="2d830-261">Informational (4)</span></span>|  
  
 <span data-ttu-id="2d830-262">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-262">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2d830-263">イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-263">Event</span></span>|<span data-ttu-id="2d830-264">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d830-264">Event ID</span></span>|<span data-ttu-id="2d830-265">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="2d830-265">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="2d830-266">44</span><span class="sxs-lookup"><span data-stu-id="2d830-266">44</span></span>|<span data-ttu-id="2d830-267">I/O スレッドがスレッド プールに作成された。</span><span class="sxs-lookup"><span data-stu-id="2d830-267">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="2d830-268">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-268">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2d830-269">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2d830-269">Field name</span></span>|<span data-ttu-id="2d830-270">データ型</span><span class="sxs-lookup"><span data-stu-id="2d830-270">Data type</span></span>|<span data-ttu-id="2d830-271">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-271">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2d830-272">カウント</span><span class="sxs-lookup"><span data-stu-id="2d830-272">Count</span></span>|<span data-ttu-id="2d830-273">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2d830-273">win:UInt64</span></span>|<span data-ttu-id="2d830-274">新しく作成されたスレッドを含む、I/O のスレッドの数です。</span><span class="sxs-lookup"><span data-stu-id="2d830-274">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="2d830-275">NumRetired</span><span class="sxs-lookup"><span data-stu-id="2d830-275">NumRetired</span></span>|<span data-ttu-id="2d830-276">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2d830-276">win:UInt64</span></span>|<span data-ttu-id="2d830-277">提供終了になったワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="2d830-277">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="2d830-278">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2d830-278">ClrInstanceID</span></span>|<span data-ttu-id="2d830-279">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2d830-279">Win:UInt16</span></span>|<span data-ttu-id="2d830-280">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="2d830-280">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretirev1"></a><span data-ttu-id="2d830-281">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="2d830-281">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="2d830-282">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-282">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2d830-283">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="2d830-283">Keyword for raising the event</span></span>|<span data-ttu-id="2d830-284">レベル</span><span class="sxs-lookup"><span data-stu-id="2d830-284">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2d830-285">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2d830-285">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2d830-286">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="2d830-286">Informational (4)</span></span>|  
  
 <span data-ttu-id="2d830-287">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-287">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2d830-288">イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-288">Event</span></span>|<span data-ttu-id="2d830-289">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d830-289">Event ID</span></span>|<span data-ttu-id="2d830-290">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="2d830-290">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="2d830-291">46</span><span class="sxs-lookup"><span data-stu-id="2d830-291">46</span></span>|<span data-ttu-id="2d830-292">I/O スレッドが、提供終了の候補になる。</span><span class="sxs-lookup"><span data-stu-id="2d830-292">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="2d830-293">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-293">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2d830-294">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2d830-294">Field name</span></span>|<span data-ttu-id="2d830-295">データ型</span><span class="sxs-lookup"><span data-stu-id="2d830-295">Data type</span></span>|<span data-ttu-id="2d830-296">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-296">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2d830-297">カウント</span><span class="sxs-lookup"><span data-stu-id="2d830-297">Count</span></span>|<span data-ttu-id="2d830-298">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2d830-298">win:UInt64</span></span>|<span data-ttu-id="2d830-299">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="2d830-299">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="2d830-300">NumRetired</span><span class="sxs-lookup"><span data-stu-id="2d830-300">NumRetired</span></span>|<span data-ttu-id="2d830-301">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2d830-301">win:UInt64</span></span>|<span data-ttu-id="2d830-302">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="2d830-302">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="2d830-303">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2d830-303">ClrInstanceID</span></span>|<span data-ttu-id="2d830-304">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2d830-304">Win:UInt16</span></span>|<span data-ttu-id="2d830-305">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="2d830-305">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretirev1"></a><span data-ttu-id="2d830-306">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="2d830-306">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="2d830-307">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-307">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2d830-308">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="2d830-308">Keyword for raising the event</span></span>|<span data-ttu-id="2d830-309">レベル</span><span class="sxs-lookup"><span data-stu-id="2d830-309">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2d830-310">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2d830-310">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2d830-311">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="2d830-311">Informational (4)</span></span>|  
  
 <span data-ttu-id="2d830-312">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-312">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2d830-313">イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-313">Event</span></span>|<span data-ttu-id="2d830-314">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d830-314">Event ID</span></span>|<span data-ttu-id="2d830-315">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="2d830-315">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="2d830-316">47</span><span class="sxs-lookup"><span data-stu-id="2d830-316">47</span></span>|<span data-ttu-id="2d830-317">スレッドが提供終了の候補になってから待機期間内に I/O が到着したため I/O スレッドが提供終了解除された。</span><span class="sxs-lookup"><span data-stu-id="2d830-317">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="2d830-318">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-318">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2d830-319">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2d830-319">Field name</span></span>|<span data-ttu-id="2d830-320">データ型</span><span class="sxs-lookup"><span data-stu-id="2d830-320">Data type</span></span>|<span data-ttu-id="2d830-321">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-321">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2d830-322">カウント</span><span class="sxs-lookup"><span data-stu-id="2d830-322">Count</span></span>|<span data-ttu-id="2d830-323">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2d830-323">win:UInt64</span></span>|<span data-ttu-id="2d830-324">これを含む、スレッド プール内の I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="2d830-324">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="2d830-325">NumRetired</span><span class="sxs-lookup"><span data-stu-id="2d830-325">NumRetired</span></span>|<span data-ttu-id="2d830-326">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2d830-326">win:UInt64</span></span>|<span data-ttu-id="2d830-327">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="2d830-327">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="2d830-328">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2d830-328">ClrInstanceID</span></span>|<span data-ttu-id="2d830-329">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2d830-329">Win:UInt16</span></span>|<span data-ttu-id="2d830-330">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="2d830-330">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="2d830-331">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="2d830-331">IOThreadTerminate</span></span>  
 <span data-ttu-id="2d830-332">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-332">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2d830-333">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="2d830-333">Keyword for raising the event</span></span>|<span data-ttu-id="2d830-334">レベル</span><span class="sxs-lookup"><span data-stu-id="2d830-334">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2d830-335">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2d830-335">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2d830-336">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="2d830-336">Informational (4)</span></span>|  
  
 <span data-ttu-id="2d830-337">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-337">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2d830-338">イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-338">Event</span></span>|<span data-ttu-id="2d830-339">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d830-339">Event ID</span></span>|<span data-ttu-id="2d830-340">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="2d830-340">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="2d830-341">45</span><span class="sxs-lookup"><span data-stu-id="2d830-341">45</span></span>|<span data-ttu-id="2d830-342">I/O スレッドがスレッド プールに作成された。</span><span class="sxs-lookup"><span data-stu-id="2d830-342">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="2d830-343">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="2d830-343">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2d830-344">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2d830-344">Field name</span></span>|<span data-ttu-id="2d830-345">データ型</span><span class="sxs-lookup"><span data-stu-id="2d830-345">Data type</span></span>|<span data-ttu-id="2d830-346">説明</span><span class="sxs-lookup"><span data-stu-id="2d830-346">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2d830-347">カウント</span><span class="sxs-lookup"><span data-stu-id="2d830-347">Count</span></span>|<span data-ttu-id="2d830-348">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2d830-348">win:UInt64</span></span>|<span data-ttu-id="2d830-349">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="2d830-349">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="2d830-350">NumRetired</span><span class="sxs-lookup"><span data-stu-id="2d830-350">NumRetired</span></span>|<span data-ttu-id="2d830-351">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2d830-351">win:UInt64</span></span>|<span data-ttu-id="2d830-352">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="2d830-352">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="2d830-353">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2d830-353">ClrInstanceID</span></span>|<span data-ttu-id="2d830-354">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2d830-354">Win:UInt16</span></span>|<span data-ttu-id="2d830-355">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="2d830-355">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d830-356">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d830-356">See also</span></span>

- [<span data-ttu-id="2d830-357">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="2d830-357">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
