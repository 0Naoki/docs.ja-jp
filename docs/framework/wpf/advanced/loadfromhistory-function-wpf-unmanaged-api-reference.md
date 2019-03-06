---
title: LoadFromHistory 関数 (WPF のアンマネージ API リファレンス)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 4fc083313c99b1b93db380bfbf6ddeacbc784dcb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487409"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d35cb-102">LoadFromHistory 関数 (WPF のアンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d35cb-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d35cb-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしているし、コードから直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="d35cb-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d35cb-104">Windows Presentation Foundation (WPF) インフラストラクチャによって windows の管理に使用します。</span><span class="sxs-lookup"><span data-stu-id="d35cb-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d35cb-105">構文</span><span class="sxs-lookup"><span data-stu-id="d35cb-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d35cb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d35cb-106">Parameters</span></span>  
 <span data-ttu-id="d35cb-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="d35cb-107">pHistoryStream</span></span>  
 <span data-ttu-id="d35cb-108">履歴情報のストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d35cb-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="d35cb-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="d35cb-109">pBindCtx</span></span>  
 <span data-ttu-id="d35cb-110">バインド コンテキストへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d35cb-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d35cb-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d35cb-111">Requirements</span></span>  
 <span data-ttu-id="d35cb-112">**プラットフォーム:** 参照してください[.NET Framework システム要件](../../get-started/system-requirements.md)します。</span><span class="sxs-lookup"><span data-stu-id="d35cb-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d35cb-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="d35cb-113">**DLL:**</span></span>  
  
 <span data-ttu-id="d35cb-114">.NET framework 3.0 および 3.5。PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="d35cb-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d35cb-115">.NET framework 4 以降では。PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="d35cb-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="d35cb-116">**.NET framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d35cb-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d35cb-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d35cb-117">See also</span></span>
- [<span data-ttu-id="d35cb-118">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="d35cb-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
