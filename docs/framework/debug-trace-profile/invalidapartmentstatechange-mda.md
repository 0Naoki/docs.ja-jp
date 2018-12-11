---
title: invalidApartmentStateChange MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73f96ea8cf215c1392857635e85556f530784397
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147659"
---
# <a name="invalidapartmentstatechange-mda"></a><span data-ttu-id="a238b-102">invalidApartmentStateChange MDA</span><span class="sxs-lookup"><span data-stu-id="a238b-102">invalidApartmentStateChange MDA</span></span>
<span data-ttu-id="a238b-103">`invalidApartmentStateChange` マネージド デバッグ アシスタント (MDS) は、次の 2 つのどちらかの問題によってアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="a238b-103">The `invalidApartmentStateChange` managed debugging assistant (MDS) is activated by either of two problems:</span></span>  
  
-   <span data-ttu-id="a238b-104">COM によって既に初期化されているスレッドの COM アパートメント状態を異なるアパートメント状態に変更しようとした。</span><span class="sxs-lookup"><span data-stu-id="a238b-104">An attempt is made to change the COM apartment state of a thread that has already been initialized by COM to a different apartment state.</span></span>  
  
-   <span data-ttu-id="a238b-105">スレッドの COM アパートメント状態が予期せず変更された。</span><span class="sxs-lookup"><span data-stu-id="a238b-105">The COM apartment state of a thread changes unexpectedly.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a238b-106">現象</span><span class="sxs-lookup"><span data-stu-id="a238b-106">Symptoms</span></span>  
  
-   <span data-ttu-id="a238b-107">スレッドの COM アパートメント状態が要求されたものと異なります。</span><span class="sxs-lookup"><span data-stu-id="a238b-107">A thread's COM apartment state is not what was requested.</span></span> <span data-ttu-id="a238b-108">これが原因で、現在のモデルと異なるスレッド処理モデルの COM コンポーネントがプロキシで使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a238b-108">This may cause proxies to be used for COM components that have a threading model different from the current one.</span></span> <span data-ttu-id="a238b-109">これにより、アパートメント間のマーシャリング用に設定されていないインターフェイスを介して COM オブジェクトが呼び出されるときに <xref:System.InvalidCastException> がスローされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a238b-109">This in turn may cause an <xref:System.InvalidCastException> to be thrown when calling the COM object through interfaces that are not set up for cross-apartment marshaling.</span></span>  
  
-   <span data-ttu-id="a238b-110">スレッドの COM アパートメント状態が予想と異なります。</span><span class="sxs-lookup"><span data-stu-id="a238b-110">The COM apartment state of the thread is different than expected.</span></span> <span data-ttu-id="a238b-111">これが原因で、[ランタイム呼び出し可能ラッパー](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) で呼び出しを行うときに、HRESULT が RPC_E_WRONG_THREAD の <xref:System.Runtime.InteropServices.COMException>、および <xref:System.InvalidCastException> が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a238b-111">This can cause a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD as well as a <xref:System.InvalidCastException> when making calls on a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="a238b-112">これにより、一部のシングル スレッド COM が同時に複数のスレッドによってアクセスされ、そのために破損またはデータの損失につながることがあります。</span><span class="sxs-lookup"><span data-stu-id="a238b-112">This can also cause some single-threaded COM components to be accessed by multiple threads at the same time, which can lead to corruption or data loss.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a238b-113">原因</span><span class="sxs-lookup"><span data-stu-id="a238b-113">Cause</span></span>  
  
-   <span data-ttu-id="a238b-114">スレッドは以前に異なる COM アパートメント状態に初期化されました。</span><span class="sxs-lookup"><span data-stu-id="a238b-114">The thread was previously initialized to a different COM apartment state.</span></span> <span data-ttu-id="a238b-115">スレッドのアパートメント状態を明示的または暗黙的に設定できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a238b-115">Note that the apartment state of a thread can be set either explicitly or implicitly.</span></span> <span data-ttu-id="a238b-116">明示的な操作には、<xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> プロパティ、<xref:System.Threading.Thread.SetApartmentState%2A> メソッド、<xref:System.Threading.Thread.TrySetApartmentState%2A> メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a238b-116">The explicit operations include the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property and the <xref:System.Threading.Thread.SetApartmentState%2A> and <xref:System.Threading.Thread.TrySetApartmentState%2A> methods.</span></span> <span data-ttu-id="a238b-117"><xref:System.Threading.Thread.Start%2A> メソッドを使用して作成されたスレッドは、スレッドが開始される前に <xref:System.Threading.Thread.SetApartmentState%2A> が呼び出されない限り、暗黙的に <xref:System.Threading.ApartmentState.MTA> に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a238b-117">A thread created using the <xref:System.Threading.Thread.Start%2A> method is implicitly set to <xref:System.Threading.ApartmentState.MTA> unless <xref:System.Threading.Thread.SetApartmentState%2A> is called before the thread is started.</span></span> <span data-ttu-id="a238b-118">アプリケーションのメイン スレッドも、メイン メソッドで <xref:System.STAThreadAttribute> 属性が指定されない限り、暗黙的に <xref:System.Threading.ApartmentState.MTA> に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="a238b-118">The main thread of the application is also implicitly initialized to <xref:System.Threading.ApartmentState.MTA> unless the <xref:System.STAThreadAttribute> attribute is specified on the main method.</span></span>  
  
-   <span data-ttu-id="a238b-119">異なるコンカレンシー モデルを持つ `CoUninitialize` メソッド (または `CoInitializeEx` メソッド) がスレッドで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a238b-119">The `CoUninitialize` method (or the `CoInitializeEx` method) with a different concurrency model is called on the thread.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a238b-120">解像度</span><span class="sxs-lookup"><span data-stu-id="a238b-120">Resolution</span></span>  
 <span data-ttu-id="a238b-121">スレッドの実行開始前に、スレッドのアパートメント状態を設定するか、<xref:System.STAThreadAttribute> 属性または <xref:System.MTAThreadAttribute> 属性をアプリケーションのメイン メソッドに適用します。</span><span class="sxs-lookup"><span data-stu-id="a238b-121">Set the apartment state of the thread before it begins executing, or apply either the <xref:System.STAThreadAttribute> attribute or the <xref:System.MTAThreadAttribute> attribute to the main method of the application.</span></span>  
  
 <span data-ttu-id="a238b-122">2 番目の原因の場合、理想的には、`CoUninitialize` メソッドを呼び出すコードを変更し、スレッドの終了間近になり、RCW がなく、基になる COM コンポーネントがまだスレッドによって使用されている状態まで、呼び出しを遅延する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a238b-122">For the second cause, ideally, the code that calls the `CoUninitialize` method should be modified to delay the call until the thread is about to terminate and there are no RCWs and their underlying COM components still in use by the thread.</span></span> <span data-ttu-id="a238b-123">ただし、`CoUninitialize` を呼び出すコードを変更できない場合は、この方法で初期化解除されるスレッドから RCW を使用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a238b-123">However, if it is not possible to modify the code that calls the `CoUninitialize` method, then no RCWs should be used from threads that are uninitialized in this way.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a238b-124">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="a238b-124">Effect on the Runtime</span></span>  
 <span data-ttu-id="a238b-125">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="a238b-125">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a238b-126">出力</span><span class="sxs-lookup"><span data-stu-id="a238b-126">Output</span></span>  
 <span data-ttu-id="a238b-127">現在のスレッドの COM アパートメント状態、およびコードが適用しようとした状態。</span><span class="sxs-lookup"><span data-stu-id="a238b-127">The COM apartment state of the current thread, and the state that the code was attempting to apply.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a238b-128">構成</span><span class="sxs-lookup"><span data-stu-id="a238b-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="a238b-129">例</span><span class="sxs-lookup"><span data-stu-id="a238b-129">Example</span></span>  
 <span data-ttu-id="a238b-130">次のコードの例は、この MDA がアクティブ化されることのある状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="a238b-130">The following code example demonstrates a situation that can activate this MDA.</span></span>  
  
```csharp
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a238b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="a238b-131">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="a238b-132">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="a238b-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="a238b-133">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="a238b-133">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
