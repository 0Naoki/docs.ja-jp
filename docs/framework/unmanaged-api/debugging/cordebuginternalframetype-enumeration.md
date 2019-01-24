---
title: CorDebugInternalFrameType 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cf4c0eb3f9bb36cb45aa93c576b4efddaa93482
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736534"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="a6e13-102">CorDebugInternalFrameType 列挙型</span><span class="sxs-lookup"><span data-stu-id="a6e13-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="a6e13-103">スタック フレームの型を示します。</span><span class="sxs-lookup"><span data-stu-id="a6e13-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="a6e13-104">この列挙体を使って、 [icordebuginternalframe::getframetype](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a6e13-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e13-105">構文</span><span class="sxs-lookup"><span data-stu-id="a6e13-105">Syntax</span></span>  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a><span data-ttu-id="a6e13-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a6e13-106">Members</span></span>  
  
|<span data-ttu-id="a6e13-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="a6e13-107">Member</span></span>|<span data-ttu-id="a6e13-108">説明</span><span class="sxs-lookup"><span data-stu-id="a6e13-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="a6e13-109">null 値。</span><span class="sxs-lookup"><span data-stu-id="a6e13-109">A null value.</span></span> <span data-ttu-id="a6e13-110">`ICorDebugInternalFrame::GetFrameType`メソッドがこの値を返すことはありません。</span><span class="sxs-lookup"><span data-stu-id="a6e13-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="a6e13-111">マネージとアンマネージのスタブ フレーム。</span><span class="sxs-lookup"><span data-stu-id="a6e13-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="a6e13-112">スタブのアンマネージからマネージ フレームでは。</span><span class="sxs-lookup"><span data-stu-id="a6e13-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="a6e13-113">アプリケーション ドメイン間で遷移します。</span><span class="sxs-lookup"><span data-stu-id="a6e13-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="a6e13-114">軽量なメソッド呼び出し。</span><span class="sxs-lookup"><span data-stu-id="a6e13-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="a6e13-115">関数の評価の開始。</span><span class="sxs-lookup"><span data-stu-id="a6e13-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="a6e13-116">共通言語ランタイムの内部呼び出し。</span><span class="sxs-lookup"><span data-stu-id="a6e13-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="a6e13-117">クラスの初期化の開始。</span><span class="sxs-lookup"><span data-stu-id="a6e13-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="a6e13-118">スローされる例外。</span><span class="sxs-lookup"><span data-stu-id="a6e13-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="a6e13-119">コード アクセス セキュリティのために使用するフレーム。</span><span class="sxs-lookup"><span data-stu-id="a6e13-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="a6e13-120">ランタイムは、メソッドを JIT コンパイルです。</span><span class="sxs-lookup"><span data-stu-id="a6e13-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6e13-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6e13-121">Requirements</span></span>  
 <span data-ttu-id="a6e13-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e13-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e13-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6e13-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6e13-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6e13-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6e13-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e13-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e13-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6e13-126">See also</span></span>
- [<span data-ttu-id="a6e13-127">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="a6e13-127">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
