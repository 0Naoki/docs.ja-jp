---
title: IAssemblyEnum::GetNextAssembly メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 563784dd2fe3881cbf3278992ca2c75a94df1d3f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727561"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="62d8f-102">IAssemblyEnum::GetNextAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="62d8f-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="62d8f-103">次のポインターを取得[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)これに含まれる[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="62d8f-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62d8f-104">構文</span><span class="sxs-lookup"><span data-stu-id="62d8f-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62d8f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62d8f-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="62d8f-106">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="62d8f-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="62d8f-107">`pvReserved` null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62d8f-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="62d8f-108">[out]返された`IAssemblyName`ポインター。</span><span class="sxs-lookup"><span data-stu-id="62d8f-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="62d8f-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="62d8f-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="62d8f-110">`dwFlags` 0 (ゼロ) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62d8f-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62d8f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="62d8f-111">Requirements</span></span>  
 <span data-ttu-id="62d8f-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62d8f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d8f-113">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="62d8f-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="62d8f-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d8f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d8f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="62d8f-115">See also</span></span>
- [<span data-ttu-id="62d8f-116">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62d8f-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="62d8f-117">IAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62d8f-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
