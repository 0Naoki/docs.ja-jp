---
title: ICLRDataTarget::SetTLSValue メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 421fb371094c21948486e56d0881163e7a6961a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465284"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="54b7f-102">ICLRDataTarget::SetTLSValue メソッド</span><span class="sxs-lookup"><span data-stu-id="54b7f-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="54b7f-103">ターゲット プロセス内の指定したスレッドのスレッド ローカル ストレージ (TLS) の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="54b7f-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="54b7f-104">このメソッドは、共通言語ランタイム (CLR) データ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54b7f-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b7f-105">構文</span><span class="sxs-lookup"><span data-stu-id="54b7f-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54b7f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54b7f-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="54b7f-107">[in]ターゲット プロセス内のスレッドのオペレーティング システムの識別子です。</span><span class="sxs-lookup"><span data-stu-id="54b7f-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="54b7f-108">[in]位置のインデックス。</span><span class="sxs-lookup"><span data-stu-id="54b7f-108">[in] The index of the location.</span></span> <span data-ttu-id="54b7f-109">この値は、指定したスレッドのローカル ストアに有効なインデックスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54b7f-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="54b7f-110">[in]A `CLRDATA_ADDRESS` TLS の指定した場所に配置する値を指定する値。</span><span class="sxs-lookup"><span data-stu-id="54b7f-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54b7f-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="54b7f-111">Remarks</span></span>  
 <span data-ttu-id="54b7f-112">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="54b7f-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54b7f-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="54b7f-113">Requirements</span></span>  
 <span data-ttu-id="54b7f-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b7f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54b7f-115">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="54b7f-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="54b7f-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54b7f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54b7f-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54b7f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b7f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="54b7f-118">See also</span></span>
- [<span data-ttu-id="54b7f-119">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54b7f-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
