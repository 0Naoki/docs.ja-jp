---
title: ICorDebugCode::CreateBreakpoint メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d193f9aa4d051baa73944545d28a455495aeda40
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185771"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="6f79e-102">ICorDebugCode::CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="6f79e-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="6f79e-103">指定したオフセットには、このコード セグメントでは、ブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f79e-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f79e-104">構文</span><span class="sxs-lookup"><span data-stu-id="6f79e-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f79e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f79e-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="6f79e-106">[in]ブレークポイントを作成するオフセットです。</span><span class="sxs-lookup"><span data-stu-id="6f79e-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="6f79e-107">[out]ブレークポイントを表す"ICorDebugFunctionBreakpoint"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6f79e-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f79e-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f79e-108">Remarks</span></span>  
 <span data-ttu-id="6f79e-109">前に、ブレークポイントがアクティブでは、プロセス オブジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f79e-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="6f79e-110">このコードは、Microsoft intermediate language (MSIL) コードでは、およびの just-in-time (JIT) があるかどうか、コードの JIT コンパイルにも、ブレークポイント、コードのコンパイル済みのネイティブのバージョンが適用されます。</span><span class="sxs-lookup"><span data-stu-id="6f79e-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="6f79e-111">(同じは、コードが JIT コンパイルされた後では、true を返します。)</span><span class="sxs-lookup"><span data-stu-id="6f79e-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f79e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="6f79e-112">Requirements</span></span>  
 <span data-ttu-id="6f79e-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f79e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f79e-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f79e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f79e-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f79e-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6f79e-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="6f79e-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f79e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f79e-117">See also</span></span>
