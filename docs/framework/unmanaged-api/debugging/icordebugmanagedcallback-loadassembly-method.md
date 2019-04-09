---
title: ICorDebugManagedCallback::LoadAssembly メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5760287e01257e3f0fc99a18ba20f2f2a1b2b3af
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083362"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="c7d16-102">ICorDebugManagedCallback::LoadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="c7d16-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="c7d16-103">共通言語ランタイム (CLR) アセンブリが正常にアンロードされたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c7d16-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d16-104">構文</span><span class="sxs-lookup"><span data-stu-id="c7d16-104">Syntax</span></span>  
  
```  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7d16-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7d16-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c7d16-106">[in]先のアセンブリが読み込まれたアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c7d16-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="c7d16-107">[in]アセンブリを表す ICorDebugAssembly オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c7d16-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7d16-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="c7d16-108">Requirements</span></span>  
 <span data-ttu-id="c7d16-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7d16-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7d16-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7d16-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7d16-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7d16-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c7d16-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c7d16-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c7d16-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7d16-113">See also</span></span>

- [<span data-ttu-id="c7d16-114">UnloadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="c7d16-114">UnloadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="c7d16-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7d16-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
