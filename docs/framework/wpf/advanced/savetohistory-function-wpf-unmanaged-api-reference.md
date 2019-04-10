---
title: SaveToHistory 関数 (WPF のアンマネージ API リファレンス)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: 3f6413558ff1f259e497c6a1c31eb2664f70cc48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213717"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="5db4c-102">SaveToHistory 関数 (WPF のアンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5db4c-102">SaveToHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="5db4c-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしているし、コードから直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="5db4c-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="5db4c-104">Windows Presentation Foundation (WPF) インフラストラクチャによって windows の管理に使用します。</span><span class="sxs-lookup"><span data-stu-id="5db4c-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db4c-105">構文</span><span class="sxs-lookup"><span data-stu-id="5db4c-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="5db4c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5db4c-106">Parameters</span></span>  
 <span data-ttu-id="5db4c-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="5db4c-107">pHistoryStream</span></span>  
 <span data-ttu-id="5db4c-108">履歴のストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5db4c-108">A pointer to the history stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5db4c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5db4c-109">Requirements</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5db4c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5db4c-110">Requirements</span></span>  
 <span data-ttu-id="5db4c-111">**プラットフォーム:** 参照してください[.NET Framework システム要件](../../get-started/system-requirements.md)します。</span><span class="sxs-lookup"><span data-stu-id="5db4c-111">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="5db4c-112">DLL:</span><span class="sxs-lookup"><span data-stu-id="5db4c-112">DLL:</span></span>**  
  
 <span data-ttu-id="5db4c-113">.NET framework 3.0 および 3.5。PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="5db4c-113">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="5db4c-114">.NET framework 4 以降では。PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="5db4c-114">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="5db4c-115">.NET framework のバージョン:</span><span class="sxs-lookup"><span data-stu-id="5db4c-115">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5db4c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5db4c-116">See also</span></span>

- [<span data-ttu-id="5db4c-117">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="5db4c-117">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
