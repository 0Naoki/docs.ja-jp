---
title: ICorDebugCode::GetCode メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d057032f2a46ef29a903ae21ab13af02f9d657f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728766"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="ed867-102">ICorDebugCode::GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="ed867-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="ed867-103">指定した関数のすべてのコードを取得し、逆アセンブリ用に書式設定します。</span><span class="sxs-lookup"><span data-stu-id="ed867-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="ed867-104">このメソッドは、.NET Framework version 2.0 で廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ed867-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ed867-105">使用[icordebugcode 2::getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="ed867-105">Use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed867-106">構文</span><span class="sxs-lookup"><span data-stu-id="ed867-106">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed867-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ed867-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="ed867-108">[in]関数の最初のオフセット。</span><span class="sxs-lookup"><span data-stu-id="ed867-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="ed867-109">[in]関数の最後のオフセット。</span><span class="sxs-lookup"><span data-stu-id="ed867-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="ed867-110">[in]サイズ、`buffer`にコードを返される配列。</span><span class="sxs-lookup"><span data-stu-id="ed867-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="ed867-111">[out]コードが返される先の配列。</span><span class="sxs-lookup"><span data-stu-id="ed867-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="ed867-112">[out]返されるバイト数。</span><span class="sxs-lookup"><span data-stu-id="ed867-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed867-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="ed867-113">Remarks</span></span>  
 <span data-ttu-id="ed867-114">関数のコードは、複数のチャンクに分割されていますが場合、は、ネイティブのオフセットの昇順で連結されます。</span><span class="sxs-lookup"><span data-stu-id="ed867-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="ed867-115">命令の境界はチェックされません。</span><span class="sxs-lookup"><span data-stu-id="ed867-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed867-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="ed867-116">Requirements</span></span>  
 <span data-ttu-id="ed867-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed867-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed867-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed867-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed867-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed867-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed867-120">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ed867-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed867-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed867-121">See also</span></span>
- [<span data-ttu-id="ed867-122">GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="ed867-122">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)

