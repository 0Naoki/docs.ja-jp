---
title: disconnectedContext MDA
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d97ee808ef7d2a14902259c47227b787f0830fb
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629381"
---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="252d2-102">disconnectedContext MDA</span><span class="sxs-lookup"><span data-stu-id="252d2-102">disconnectedContext MDA</span></span>
<span data-ttu-id="252d2-103">CLR が COM オブジェクトに関する要求を処理中に、切断しているアパートメントまたはコンテキストに遷移しようとすると、`disconnectedContext` マネージド デバッグ アシスタント (MDA) がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="252d2-103">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="252d2-104">症状</span><span class="sxs-lookup"><span data-stu-id="252d2-104">Symptoms</span></span>  
 <span data-ttu-id="252d2-105">[ランタイム呼び出し可能ラッパー](../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) に対する呼び出しは、その呼び出しが存在する COM コンポーネントではなく、現在のアパートメントまたはコンテキスト内の基になる COM コンポーネントへ送られます。</span><span class="sxs-lookup"><span data-stu-id="252d2-105">Calls made on a [Runtime Callable Wrapper](../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="252d2-106">シングル スレッド アパートメント (STA) コンポーネントのように、COM コンポーネントがマルチスレッド化されていない場合、これが原因で破損やデータ損失が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="252d2-106">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="252d2-107">あるいは RCW 自体がプロキシである場合、呼び出しの結果として <xref:System.Runtime.InteropServices.COMException> がスローされ、HRESULT が RPC_E_WRONG_THREAD になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="252d2-107">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="252d2-108">原因</span><span class="sxs-lookup"><span data-stu-id="252d2-108">Cause</span></span>  
 <span data-ttu-id="252d2-109">OLE アパートメントまたはコンテキストは、CLR が遷移を試行しようとしたときに、既にシャットダウンしています。</span><span class="sxs-lookup"><span data-stu-id="252d2-109">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="252d2-110">ほとんどの場合これは、STA アパートメントが所有するすべての COM コンポーネントが完全に解放される前に、それらの STA アパートメントがシャットダウンしたことが原因で発生します。また、RCW でユーザー コードからの明示的な呼び出しが実行された結果として発生することや、CLR 自体が COM コンポーネントを操作している場合 (たとえば関連する RCW がガーベージ コレクションされているのに CRL が COM コンポーネントを解放する場合など) にも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="252d2-110">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="252d2-111">解決方法</span><span class="sxs-lookup"><span data-stu-id="252d2-111">Resolution</span></span>  
 <span data-ttu-id="252d2-112">この問題を回避するには、アプリケーションがアパートメントに存在するすべてのオブジェクトの処理を完了する前に、STA を所有するスレッドが強制終了しないようにします。</span><span class="sxs-lookup"><span data-stu-id="252d2-112">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="252d2-113">コンテキストの場合も同様に、アプリケーションがコンテキスト内部に存在するすべての COM コンポーネントの処理を完了するまでは、コンテキストがシャットダウンしないようにします。</span><span class="sxs-lookup"><span data-stu-id="252d2-113">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="252d2-114">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="252d2-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="252d2-115">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="252d2-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="252d2-116">接続していないコンテキストに関するデータを報告するだけです。</span><span class="sxs-lookup"><span data-stu-id="252d2-116">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="252d2-117">Output</span><span class="sxs-lookup"><span data-stu-id="252d2-117">Output</span></span>  
 <span data-ttu-id="252d2-118">非接続アパートメントまたはコンテキストのコンテキスト Cookie を報告します。</span><span class="sxs-lookup"><span data-stu-id="252d2-118">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="252d2-119">構成</span><span class="sxs-lookup"><span data-stu-id="252d2-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="252d2-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="252d2-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="252d2-121">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="252d2-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="252d2-122">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="252d2-122">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
