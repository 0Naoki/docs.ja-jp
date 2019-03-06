---
title: ICLRDataTarget::Request メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bafc8be92da72cbb98f7cd47ec6632a3fbb76656
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487216"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="8c817-102">ICLRDataTarget::Request メソッド</span><span class="sxs-lookup"><span data-stu-id="8c817-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="8c817-103">実装によって定義されているように、操作を要求する共通言語ランタイム (CLR) データ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8c817-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c817-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c817-104">Syntax</span></span>  
  
```  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c817-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c817-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="8c817-106">[in]ユーザー定義です。</span><span class="sxs-lookup"><span data-stu-id="8c817-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="8c817-107">[in]受信要求に使用される入力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="8c817-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="8c817-108">[in]要求を含むバッファー。</span><span class="sxs-lookup"><span data-stu-id="8c817-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="8c817-109">[in]応答に使用される出力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="8c817-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="8c817-110">[out]応答を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="8c817-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c817-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c817-111">Remarks</span></span>  
 <span data-ttu-id="8c817-112">`Request`メソッドが指定されていないカスタム操作の追加を容易になります。</span><span class="sxs-lookup"><span data-stu-id="8c817-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="8c817-113">つまり、このメソッドは、インターフェイス定義のリビジョンを必要とせずに機能拡張を提供します。</span><span class="sxs-lookup"><span data-stu-id="8c817-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="8c817-114">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="8c817-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c817-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c817-115">Requirements</span></span>  
 <span data-ttu-id="8c817-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c817-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c817-117">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8c817-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8c817-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c817-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c817-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c817-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c817-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c817-120">See also</span></span>
- [<span data-ttu-id="8c817-121">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c817-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
