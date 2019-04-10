---
title: notMarshalable MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 30db07ddf935b5ce13b1fe4212f7f6a40270ae93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226106"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="0b810-102">notMarshalable MDA</span><span class="sxs-lookup"><span data-stu-id="0b810-102">notMarshalable MDA</span></span>
<span data-ttu-id="0b810-103">共通言語ランタイム (CLR: Common Language Runtime) がコンテキスト間でインターフェイスをマーシャリングするときに、有効な登録済みのプロキシやスタブのない COM インターフェイス ポインター、または不正な `IMarshal` インターフェイスの実装を検出すると、`notMarshalable` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) がアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="0b810-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0b810-104">症状</span><span class="sxs-lookup"><span data-stu-id="0b810-104">Symptoms</span></span>  
 <span data-ttu-id="0b810-105">呼び出しが処理されないか、COM インターフェイス ポインターの不正なコンテキストで発生します。</span><span class="sxs-lookup"><span data-stu-id="0b810-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0b810-106">原因</span><span class="sxs-lookup"><span data-stu-id="0b810-106">Cause</span></span>  
 <span data-ttu-id="0b810-107">コンテキスト間でインターフェイスのマーシャリングを試みたときに、有効な登録済みのプロキシやスタブがないか、`IMarshal` が不正です。</span><span class="sxs-lookup"><span data-stu-id="0b810-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0b810-108">解像度</span><span class="sxs-lookup"><span data-stu-id="0b810-108">Resolution</span></span>  
 <span data-ttu-id="0b810-109">プロキシ スタブを登録済みであることと、`IMarshal` の実装が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b810-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0b810-110">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="0b810-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="0b810-111">この MDA は、ランタイムに影響しません。</span><span class="sxs-lookup"><span data-stu-id="0b810-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0b810-112">出力</span><span class="sxs-lookup"><span data-stu-id="0b810-112">Output</span></span>  
 <span data-ttu-id="0b810-113">問題を説明するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0b810-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0b810-114">構成</span><span class="sxs-lookup"><span data-stu-id="0b810-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b810-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b810-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="0b810-116">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="0b810-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="0b810-117">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="0b810-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
