---
title: CloseEnum メソッド
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd7d63596690e2a5d0bc26448884ec09ecd63231
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129520"
---
# <a name="closeenum-method"></a><span data-ttu-id="2dcad-102">CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="2dcad-102">CloseEnum Method</span></span>
<span data-ttu-id="2dcad-103">指定の列挙体を終了し、関連付けられているリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="2dcad-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dcad-104">構文</span><span class="sxs-lookup"><span data-stu-id="2dcad-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dcad-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2dcad-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="2dcad-106">終了する列挙体のハンドル。</span><span class="sxs-lookup"><span data-stu-id="2dcad-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2dcad-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2dcad-107">Return Value</span></span>  
 <span data-ttu-id="2dcad-108">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="2dcad-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dcad-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2dcad-109">Requirements</span></span>  
 <span data-ttu-id="2dcad-110">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="2dcad-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dcad-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dcad-111">See also</span></span>

- [<span data-ttu-id="2dcad-112">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2dcad-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2dcad-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2dcad-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2dcad-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="2dcad-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
