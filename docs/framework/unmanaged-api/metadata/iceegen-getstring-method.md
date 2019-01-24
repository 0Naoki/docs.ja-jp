---
title: ICeeGen::GetString メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d8d6a0ebecb4fbb9ba277844710c775d80648e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716818"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="a910f-102">ICeeGen::GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="a910f-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="a910f-103">指定された相対仮想アドレスに格納されている文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="a910f-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="a910f-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a910f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a910f-105">構文</span><span class="sxs-lookup"><span data-stu-id="a910f-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a910f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a910f-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="a910f-107">[in]返される文字列の相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="a910f-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="a910f-108">[out]返される文字列。</span><span class="sxs-lookup"><span data-stu-id="a910f-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a910f-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="a910f-109">Requirements</span></span>  
 <span data-ttu-id="a910f-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a910f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a910f-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a910f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a910f-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a910f-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a910f-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a910f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a910f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a910f-114">See also</span></span>
- [<span data-ttu-id="a910f-115">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a910f-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
