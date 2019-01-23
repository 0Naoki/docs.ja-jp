---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f87107be14554d8d826c58108446ecd245549b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603691"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="5a57d-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion メソッド</span><span class="sxs-lookup"><span data-stu-id="5a57d-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="5a57d-103">によって呼び出される[iclrdataenummemoryregions::enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)メモリの指定した領域の列挙の試行の結果をデバッガーに報告します。</span><span class="sxs-lookup"><span data-stu-id="5a57d-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a57d-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a57d-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a57d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a57d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5a57d-106">[in]列挙されるメモリ領域の開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="5a57d-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="5a57d-107">[in] \(バイト単位\) のメモリ領域のサイズ。</span><span class="sxs-lookup"><span data-stu-id="5a57d-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a57d-108">コメント</span><span class="sxs-lookup"><span data-stu-id="5a57d-108">Remarks</span></span>  
 <span data-ttu-id="5a57d-109">`ICLRDataEnumMemoryRegions::EnumMemoryRegions`メソッドは、メモリ領域を列挙するために試行するたびにこのコールバック メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5a57d-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="5a57d-110">このメソッドは、エラーを示す HRESULT を返した場合であっても、列挙は継続されます。</span><span class="sxs-lookup"><span data-stu-id="5a57d-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="5a57d-111">このコールバックによって報告されたリージョンには、重複またはオーバー ラップがあります。</span><span class="sxs-lookup"><span data-stu-id="5a57d-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a57d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a57d-112">Requirements</span></span>  
 <span data-ttu-id="5a57d-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a57d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a57d-114">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="5a57d-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5a57d-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a57d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a57d-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a57d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a57d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a57d-117">See also</span></span>
- [<span data-ttu-id="5a57d-118">ICLRDataEnumMemoryRegionsCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a57d-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
