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
ms.openlocfilehash: 20e718d425d0300aed8cc7ccf064126ee8384704
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608298"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="57792-102">ICorDebugCode::CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="57792-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="57792-103">指定したオフセットには、このコード セグメントでは、ブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="57792-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57792-104">構文</span><span class="sxs-lookup"><span data-stu-id="57792-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57792-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="57792-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="57792-106">[in]ブレークポイントを作成するオフセットです。</span><span class="sxs-lookup"><span data-stu-id="57792-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="57792-107">[out]ブレークポイントを表す"ICorDebugFunctionBreakpoint"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="57792-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57792-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="57792-108">Remarks</span></span>  
 <span data-ttu-id="57792-109">前に、ブレークポイントがアクティブでは、プロセス オブジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57792-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="57792-110">このコードは、Microsoft intermediate language (MSIL) コードでは、およびの just-in-time (JIT) があるかどうか、コードの JIT コンパイルにも、ブレークポイント、コードのコンパイル済みのネイティブのバージョンが適用されます。</span><span class="sxs-lookup"><span data-stu-id="57792-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="57792-111">(同じは、コードが JIT コンパイルされた後では、true を返します。)</span><span class="sxs-lookup"><span data-stu-id="57792-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57792-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="57792-112">Requirements</span></span>  
 <span data-ttu-id="57792-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="57792-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57792-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57792-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57792-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57792-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57792-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57792-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57792-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="57792-117">See also</span></span>

