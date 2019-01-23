---
title: ICorDebugDataTarget::ReadVirtual メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bc807906af67350f309a4fc9439899cea328be8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575490"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="de6ad-102">ICorDebugDataTarget::ReadVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="de6ad-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="de6ad-103">指定したアドレスから始まる連続したメモリのブロックを取得し、指定されたバッファーで返します。</span><span class="sxs-lookup"><span data-stu-id="de6ad-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de6ad-104">構文</span><span class="sxs-lookup"><span data-stu-id="de6ad-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de6ad-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de6ad-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="de6ad-106">[in]要求されたメモリの開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="de6ad-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="de6ad-107">[out]メモリを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="de6ad-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="de6ad-108">[in]ターゲット アドレスから取得するバイト数。</span><span class="sxs-lookup"><span data-stu-id="de6ad-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="de6ad-109">[out]ターゲット アドレスから実際に読み取られたバイト数。</span><span class="sxs-lookup"><span data-stu-id="de6ad-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="de6ad-110">これより少ない`bytesRequested`します。</span><span class="sxs-lookup"><span data-stu-id="de6ad-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de6ad-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="de6ad-111">Remarks</span></span>  
 <span data-ttu-id="de6ad-112">(指定した開始アドレス) にある最初のバイトを読み取るには、呼び出しは成功した場合 (長さ、null で終わる文字列のような自己記述型のデータ構造体の効率的な読み取りをサポート) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ad-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de6ad-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="de6ad-113">Requirements</span></span>  
 <span data-ttu-id="de6ad-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6ad-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de6ad-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de6ad-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de6ad-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de6ad-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de6ad-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de6ad-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de6ad-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="de6ad-118">See also</span></span>
- [<span data-ttu-id="de6ad-119">ICorDebugDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de6ad-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="de6ad-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de6ad-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="de6ad-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="de6ad-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
