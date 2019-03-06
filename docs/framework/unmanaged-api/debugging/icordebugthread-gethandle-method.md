---
title: ICorDebugThread::GetHandle メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 900fece1dd29f73f77b85ff08e4deff1396f8aaf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484512"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="af8dc-102">ICorDebugThread::GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="af8dc-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="af8dc-103">この ICorDebugThread のアクティブな部分には、現在のハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="af8dc-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af8dc-104">構文</span><span class="sxs-lookup"><span data-stu-id="af8dc-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af8dc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af8dc-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="af8dc-106">[out]このスレッドのアクティブな部分のハンドルである、HTHREAD へのポインター。</span><span class="sxs-lookup"><span data-stu-id="af8dc-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af8dc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="af8dc-107">Remarks</span></span>  
 <span data-ttu-id="af8dc-108">ハンドルは、実行すると、プロセス、スレッドの種類ごとに異なる可能性がありますを変更できます。</span><span class="sxs-lookup"><span data-stu-id="af8dc-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="af8dc-109">このハンドルは、デバッグ API が所有します。</span><span class="sxs-lookup"><span data-stu-id="af8dc-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="af8dc-110">デバッガーを使用する前に複製する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af8dc-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af8dc-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="af8dc-111">Requirements</span></span>  
 <span data-ttu-id="af8dc-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af8dc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af8dc-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af8dc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af8dc-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af8dc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af8dc-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af8dc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
