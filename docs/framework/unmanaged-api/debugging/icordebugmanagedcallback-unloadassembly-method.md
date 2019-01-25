---
title: ICorDebugManagedCallback::UnloadAssembly メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93d44006dd6652a8d34c23209eb957b23064f976
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704005"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="6b392-102">ICorDebugManagedCallback::UnloadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="6b392-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="6b392-103">共通言語ランタイム アセンブリがアンロードされたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="6b392-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b392-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b392-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b392-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b392-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6b392-106">[in]アセンブリに含まれるアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6b392-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="6b392-107">[in]アセンブリを表す ICorDebugAssembly オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6b392-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b392-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="6b392-108">Remarks</span></span>  
 <span data-ttu-id="6b392-109">このコールバックの後、アセンブリを使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b392-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b392-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b392-110">Requirements</span></span>  
 <span data-ttu-id="6b392-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b392-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b392-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b392-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b392-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b392-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b392-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b392-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b392-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b392-115">See also</span></span>
- [<span data-ttu-id="6b392-116">LoadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="6b392-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="6b392-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b392-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
