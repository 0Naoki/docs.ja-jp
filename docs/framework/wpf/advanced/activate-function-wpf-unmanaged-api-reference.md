---
title: Activate 関数 (WPF のアンマネージ API リファレンス)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: ee231653815bd5ef75d58979034e3b3be9f5ba54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480781"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="c1cdf-102">Activate 関数 (WPF のアンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c1cdf-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="c1cdf-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしているし、コードから直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="c1cdf-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="c1cdf-104">Windows Presentation Foundation (WPF) インフラストラクチャによって windows の管理に使用します。</span><span class="sxs-lookup"><span data-stu-id="c1cdf-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1cdf-105">構文</span><span class="sxs-lookup"><span data-stu-id="c1cdf-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="c1cdf-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1cdf-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="c1cdf-107">ウィンドウのアクティブ化パラメーターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c1cdf-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="c1cdf-108">ポインターを格納している 1 つの要素のバッファーのアドレスへのポインター、<xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c1cdf-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="c1cdf-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1cdf-109">Requirements</span></span>

<span data-ttu-id="c1cdf-110">**プラットフォーム:** 参照してください[.NET Framework システム要件](../../get-started/system-requirements.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1cdf-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c1cdf-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="c1cdf-111">**DLL:**</span></span>

<span data-ttu-id="c1cdf-112">.NET framework 3.0 および 3.5。PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="c1cdf-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="c1cdf-113">.NET framework 4 以降では。PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="c1cdf-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="c1cdf-114">**.NET framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1cdf-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c1cdf-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1cdf-115">See also</span></span>

- [<span data-ttu-id="c1cdf-116">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="c1cdf-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
