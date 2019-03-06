---
title: ICorDebugNativeFrame::GetLocalRegisterMemoryValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3a174953877d70a295e659220e71c337e45f392
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495235"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="82b1d-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="82b1d-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="82b1d-103">引数またはうち下位ワードと上位ワード メモリ位置に格納され、このネイティブ フレームにそれぞれ、レジスタを指定のローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="82b1d-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82b1d-104">構文</span><span class="sxs-lookup"><span data-stu-id="82b1d-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82b1d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82b1d-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="82b1d-106">[in]値の上位ワードを含むレジスタを指定する"CorDebugRegister"列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="82b1d-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="82b1d-107">[in]A`CORDB_ADDRESS`値の下位ワードを格納しているメモリの場所を指定する値。</span><span class="sxs-lookup"><span data-stu-id="82b1d-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="82b1d-108">[in]によって参照されているバイナリ メタデータ シグネチャのサイズを指定する整数、`pvSigBlob`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="82b1d-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="82b1d-109">[in]A`PCCOR_SIGNATURE`値の型のバイナリ メタデータ シグネチャを示す値。</span><span class="sxs-lookup"><span data-stu-id="82b1d-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="82b1d-110">[out]指定した登録とメモリの場所に格納されている取得した値を表す"ICorDebugValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="82b1d-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82b1d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="82b1d-111">Requirements</span></span>  
 <span data-ttu-id="82b1d-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b1d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82b1d-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82b1d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82b1d-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82b1d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82b1d-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82b1d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b1d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="82b1d-116">See also</span></span>

