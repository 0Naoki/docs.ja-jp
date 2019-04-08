---
title: ICorDebugNativeFrame::GetIP メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f913b742f7ece2f136454f801ae780124aed87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073534"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="067b0-102">ICorDebugNativeFrame::GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="067b0-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="067b0-103">ネイティブ コードのオフセット命令ポインターが現在設定されている場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="067b0-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="067b0-104">構文</span><span class="sxs-lookup"><span data-stu-id="067b0-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="067b0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="067b0-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="067b0-106">[out]ネイティブ コード内のオフセット位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="067b0-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="067b0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="067b0-107">Remarks</span></span>  
 <span data-ttu-id="067b0-108">この"ICorDebugNativeFrame"で表されるスタック フレームがアクティブな場合は、オフセットは、実行する次の命令のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="067b0-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="067b0-109">このスタック フレームがアクティブでない場合、オフセットは、次のスタック フレームが再アクティブ化時に実行される命令のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="067b0-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="067b0-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="067b0-110">Requirements</span></span>  
 <span data-ttu-id="067b0-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="067b0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="067b0-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="067b0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="067b0-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="067b0-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="067b0-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="067b0-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="067b0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="067b0-115">See also</span></span>
