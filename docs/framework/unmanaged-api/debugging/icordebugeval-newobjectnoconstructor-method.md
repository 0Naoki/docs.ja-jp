---
title: ICorDebugEval::NewObjectNoConstructor メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6846b866fd47674ca6b5fd187b580fd28e080fd0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162307"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="e3e43-102">ICorDebugEval::NewObjectNoConstructor メソッド</span><span class="sxs-lookup"><span data-stu-id="e3e43-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="e3e43-103">コンス トラクター メソッドを呼び出そうとすると、指定した型の新しいオブジェクト インスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e3e43-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="e3e43-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="e3e43-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e3e43-105">使用[icordebugeval 2::newparameterizedobjectnoconstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="e3e43-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3e43-106">構文</span><span class="sxs-lookup"><span data-stu-id="e3e43-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3e43-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3e43-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="e3e43-108">[in]ICorDebugClass を表すオブジェクトをインスタンス化されるオブジェクトの型へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e3e43-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3e43-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e3e43-109">Requirements</span></span>  
 <span data-ttu-id="e3e43-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e43-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3e43-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3e43-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3e43-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3e43-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3e43-113">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="e3e43-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3e43-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3e43-114">See also</span></span>

- [<span data-ttu-id="e3e43-115">NewParameterizedObjectNoConstructor メソッド</span><span class="sxs-lookup"><span data-stu-id="e3e43-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
