---
title: ICorDebug::DebugActiveProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b3869c9f96eee6f0e3066a99a58a154a2f5f2ee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480092"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="7e12f-102">ICorDebug::DebugActiveProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="7e12f-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="7e12f-103">既存のプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="7e12f-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e12f-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e12f-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e12f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e12f-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="7e12f-106">[in]デバッガーのアタッチ先のプロセスの ID。</span><span class="sxs-lookup"><span data-stu-id="7e12f-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="7e12f-107">[in]ブール値に設定されている`true`デバッガーで、Win32 のデバッガー プロセスとして動作する必要があります、アンマネージのコールバックのディスパッチ場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="7e12f-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="7e12f-108">[out]デバッガーのアタッチするプロセスを表す"ICorDebugProcess"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7e12f-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e12f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e12f-109">Remarks</span></span>  
 <span data-ttu-id="7e12f-110">IA 64 ベースおよび AMD64 ベースのプラットフォームなど、Win9x と x86 以外のプラットフォームでは、相互運用機能デバッグはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7e12f-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e12f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7e12f-111">Requirements</span></span>  
 <span data-ttu-id="7e12f-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e12f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e12f-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e12f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e12f-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e12f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e12f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e12f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e12f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e12f-116">See also</span></span>
- [<span data-ttu-id="7e12f-117">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e12f-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
