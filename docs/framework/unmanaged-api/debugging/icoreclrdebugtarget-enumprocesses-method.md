---
title: ICoreClrDebugTarget::EnumProcesses メソッド
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a35f5ff62ca37337b7becb023f2328cbe05aea6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216042"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="b24f1-102">ICoreClrDebugTarget::EnumProcesses メソッド</span><span class="sxs-lookup"><span data-stu-id="b24f1-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="b24f1-103">リモート コンピューターで実行されているプロセスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="b24f1-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b24f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="b24f1-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b24f1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b24f1-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="b24f1-106">[out] `ppProcs` に返されるプロセス数。</span><span class="sxs-lookup"><span data-stu-id="b24f1-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="b24f1-107">この値は 0 (ゼロ) になる可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="b24f1-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="b24f1-108">[out]配列の[CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)リモート コンピューターで実行中のプロセスを表す構造体。</span><span class="sxs-lookup"><span data-stu-id="b24f1-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b24f1-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b24f1-109">Return Value</span></span>  
 <span data-ttu-id="b24f1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b24f1-110">S_OK</span></span>  
 <span data-ttu-id="b24f1-111">成功。</span><span class="sxs-lookup"><span data-stu-id="b24f1-111">Success.</span></span>  
  
 <span data-ttu-id="b24f1-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b24f1-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="b24f1-113">`ppProcs`  用に十分なメモリを割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="b24f1-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="b24f1-114">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="b24f1-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="b24f1-115">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b24f1-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b24f1-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="b24f1-116">Remarks</span></span>  
 <span data-ttu-id="b24f1-117">このメソッドによって割り当てられたメモリを解放する呼び出し、 [icoreclrdebugtarget::freememory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="b24f1-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b24f1-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="b24f1-118">Requirements</span></span>  
 <span data-ttu-id="b24f1-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b24f1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b24f1-120">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="b24f1-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="b24f1-121">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="b24f1-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="b24f1-122">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b24f1-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b24f1-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b24f1-123">See also</span></span>

- [<span data-ttu-id="b24f1-124">ICoreClrDebugTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b24f1-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
