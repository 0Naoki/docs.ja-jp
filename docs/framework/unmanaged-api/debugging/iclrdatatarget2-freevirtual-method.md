---
title: ICLRDataTarget2::FreeVirtual メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b30bd3e97af8d222f629c5b4f9f318a9b6379e78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181403"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="65b11-102">ICLRDataTarget2::FreeVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="65b11-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="65b11-103">ターゲット プロセスのアドレス空間に割り当てられていたメモリを解放共通言語ランタイム (CLR) データ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="65b11-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65b11-104">構文</span><span class="sxs-lookup"><span data-stu-id="65b11-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65b11-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65b11-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="65b11-106">[in]A`CLRDATA_ADDRESS`が解放されるメモリの開始アドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="65b11-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="65b11-107">[in]解放するメモリのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="65b11-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="65b11-108">[in]メモリの解放を制御するフラグ。</span><span class="sxs-lookup"><span data-stu-id="65b11-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="65b11-109">Win32 を参照してください。`VirtualFree`関数。</span><span class="sxs-lookup"><span data-stu-id="65b11-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65b11-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="65b11-110">Remarks</span></span>  
 <span data-ttu-id="65b11-111">`FreeVirtual`メソッドは、Win32 の論理ラッパーとして機能`VirtualFree`関数。</span><span class="sxs-lookup"><span data-stu-id="65b11-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="65b11-112">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="65b11-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65b11-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="65b11-113">Requirements</span></span>  
 <span data-ttu-id="65b11-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65b11-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65b11-115">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="65b11-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="65b11-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65b11-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="65b11-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="65b11-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="65b11-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="65b11-118">See also</span></span>

- [<span data-ttu-id="65b11-119">ICLRDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65b11-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="65b11-120">AllocVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="65b11-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
