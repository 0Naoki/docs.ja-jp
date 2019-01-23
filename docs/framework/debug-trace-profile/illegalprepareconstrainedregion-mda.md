---
title: illegalPrepareConstrainedRegion MDA
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b3e962bd68d78d9a61e41b1e6049dc35acc50c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623080"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="067fe-102">illegalPrepareConstrainedRegion MDA</span><span class="sxs-lookup"><span data-stu-id="067fe-102">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="067fe-103">`illegalPrepareConstrainedRegion` マネージド デバッグ アシスタント (MDA) は、<xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> メソッドの呼び出しが、例外ハンドラーの `try` ステートメントの直前にない場合にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="067fe-103">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="067fe-104">この制限は、MSIL レベルであり、呼び出しと `try` の間でコメントなどのコードを生成しないソースの使用が許可されます。</span><span class="sxs-lookup"><span data-stu-id="067fe-104">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="067fe-105">現象</span><span class="sxs-lookup"><span data-stu-id="067fe-105">Symptoms</span></span>  
 <span data-ttu-id="067fe-106">そのように扱われず、単純な例外処理ブロック (`finally` または `catch`) として扱われる制約された実行領域 (CER)。</span><span class="sxs-lookup"><span data-stu-id="067fe-106">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="067fe-107">その結果、メモリ不足の状態やスレッドの中止のときには領域は実行されません。</span><span class="sxs-lookup"><span data-stu-id="067fe-107">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="067fe-108">原因</span><span class="sxs-lookup"><span data-stu-id="067fe-108">Cause</span></span>  
 <span data-ttu-id="067fe-109">CER の準備パターンが正しく実行されません。</span><span class="sxs-lookup"><span data-stu-id="067fe-109">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="067fe-110">エラー イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="067fe-110">This is an error event.</span></span> <span data-ttu-id="067fe-111"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>で CER の導入として例外ハンドラーをマークするために使用するメソッドの呼び出し、 `catch` / `finally` / `fault` / `filter`ブロックにする直前に使用する必要があります、`try`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="067fe-111">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="067fe-112">解像度</span><span class="sxs-lookup"><span data-stu-id="067fe-112">Resolution</span></span>  
 <span data-ttu-id="067fe-113">`try`ステートメントの直前に <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> の呼び出しがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="067fe-113">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="067fe-114">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="067fe-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="067fe-115">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="067fe-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="067fe-116">出力</span><span class="sxs-lookup"><span data-stu-id="067fe-116">Output</span></span>  
 <span data-ttu-id="067fe-117">MDA は、<xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> メソッドの呼び出し元の名前、MSIL のオフセット、および呼び出しが try ブロックの先頭の直前にないことを示すメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="067fe-117">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="067fe-118">構成</span><span class="sxs-lookup"><span data-stu-id="067fe-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="067fe-119">例</span><span class="sxs-lookup"><span data-stu-id="067fe-119">Example</span></span>  
 <span data-ttu-id="067fe-120">次のコード例では、この MDA のアクティブ化の原因となるパターンを示します。</span><span class="sxs-lookup"><span data-stu-id="067fe-120">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="067fe-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="067fe-121">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="067fe-122">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="067fe-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="067fe-123">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="067fe-123">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
