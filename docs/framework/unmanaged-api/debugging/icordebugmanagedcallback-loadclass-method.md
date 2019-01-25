---
title: ICorDebugManagedCallback::LoadClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3c430e18864c0352b43641bce9a7d52af69cc80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718222"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="bbdbf-102">ICorDebugManagedCallback::LoadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="bbdbf-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="bbdbf-103">クラスが読み込まれたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="bbdbf-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbdbf-104">構文</span><span class="sxs-lookup"><span data-stu-id="bbdbf-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbdbf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bbdbf-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="bbdbf-106">[in]クラスのロード先のアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bbdbf-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="bbdbf-107">[in]クラスを表す ICorDebugClass オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bbdbf-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbdbf-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="bbdbf-108">Remarks</span></span>  
 <span data-ttu-id="bbdbf-109">このコールバックは、クラスを含むモジュールのクラスの読み込みが有効になっている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="bbdbf-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="bbdbf-110">クラスの読み込みは常に動的モジュールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bbdbf-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="bbdbf-111">`LoadClass`コールバックは動的モジュールの新しく生成されたクラスにブレークポイントをバインドする適切な時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="bbdbf-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbdbf-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="bbdbf-112">Requirements</span></span>  
 <span data-ttu-id="bbdbf-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbdbf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbdbf-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbdbf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbdbf-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbdbf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbdbf-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbdbf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbdbf-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbdbf-117">See also</span></span>
- [<span data-ttu-id="bbdbf-118">UnloadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="bbdbf-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="bbdbf-119">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bbdbf-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
