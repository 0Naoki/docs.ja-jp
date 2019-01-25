---
title: ETW を使用した分析トレース
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 4651c515a938ed8f8736597808156080cfb0bbed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609084"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="c5f12-102">ETW を使用した分析トレース</span><span class="sxs-lookup"><span data-stu-id="c5f12-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="c5f12-103">Windows Communication Foundation (WCF) の分析トレースは、WCF サービスの実行中に診断情報をキャプチャする手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="c5f12-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="c5f12-104">WCF 分析トレース イベントは、運用環境で WCF サービスのトラブルシューティングが可能に WCF スタック内のキー_ポイントで出力されます。</span><span class="sxs-lookup"><span data-stu-id="c5f12-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="c5f12-105">WCF サービスの分析トレースが影響を最小限製品サーバーのパフォーマンスにホストする[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]WCF サービスのようにこれらのイベントは Event Tracing for Windows (ETW) セッションに非常に効率的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="c5f12-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5f12-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c5f12-106">In This Section</span></span>  
 [<span data-ttu-id="c5f12-107">分析トレースの概要</span><span class="sxs-lookup"><span data-stu-id="c5f12-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="c5f12-108">WCF 分析トレースがでどのように動作するかについて説明します。[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c5f12-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="c5f12-109">分析トレースの動的な有効化</span><span class="sxs-lookup"><span data-stu-id="c5f12-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="c5f12-110">ETW を使用してトレースを動的に有効化または無効化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5f12-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="c5f12-111">メッセージ フローのトレースの構成</span><span class="sxs-lookup"><span data-stu-id="c5f12-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="c5f12-112">メッセージ フローのトレースを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5f12-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="c5f12-113">分析トレース イベント リファレンス</span><span class="sxs-lookup"><span data-stu-id="c5f12-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="c5f12-114">イベント ID とそれらのイベント レベル、イベント メッセージ、およびキーワードを表で示します。</span><span class="sxs-lookup"><span data-stu-id="c5f12-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f12-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5f12-115">See also</span></span>
- [<span data-ttu-id="c5f12-116">WCF サービスと Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="c5f12-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="c5f12-117">Windows のイベント トレースへの追跡イベント</span><span class="sxs-lookup"><span data-stu-id="c5f12-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
