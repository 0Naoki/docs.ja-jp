---
title: ICorPublishAppDomain::GetName メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4afbc41e680d8a20166095aeb1afbc0de9bbacbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631749"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="e142e-102">ICorPublishAppDomain::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="e142e-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="e142e-103">これで表されるアプリケーション ドメインの名前を取得[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="e142e-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e142e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e142e-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e142e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e142e-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e142e-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="e142e-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e142e-107">[out]返される、null 文字を含む、ワイド文字数へのポインター、`szName`配列。</span><span class="sxs-lookup"><span data-stu-id="e142e-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="e142e-108">[out]名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="e142e-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e142e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e142e-109">Remarks</span></span>  
 <span data-ttu-id="e142e-110">場合`szName`null 以外の場合は、`GetName`メソッドは、最大コピー`cchName`に文字 (null 終端文字を含む)`szName`します。</span><span class="sxs-lookup"><span data-stu-id="e142e-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="e142e-111">非 null が返される場合`pcchName`に実際の名前 (null 終端文字を含む) の文字数が格納されている、`szName`配列。</span><span class="sxs-lookup"><span data-stu-id="e142e-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="e142e-112">`GetName`メソッドは、コピーされた文字数に関係なく S_OK HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="e142e-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e142e-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="e142e-113">Requirements</span></span>  
 <span data-ttu-id="e142e-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e142e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e142e-115">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="e142e-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e142e-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e142e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e142e-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e142e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e142e-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e142e-118">See also</span></span>
- [<span data-ttu-id="e142e-119">ICorPublishAppDomain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e142e-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
