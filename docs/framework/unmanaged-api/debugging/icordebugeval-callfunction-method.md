---
title: ICorDebugEval::CallFunction メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66e51dc15f7d44ede26634571fa04c58e9735694
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364152"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="9c7f9-102">ICorDebugEval::CallFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="9c7f9-102">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="9c7f9-103">指定した関数の呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="9c7f9-103">Sets up a call to the specified function.</span></span>

<span data-ttu-id="9c7f9-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="9c7f9-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="9c7f9-105">使用[icordebugeval 2::callparameterizedfunction](icordebugeval2-callparameterizedfunction-method.md)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="9c7f9-105">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c7f9-106">構文</span><span class="sxs-lookup"><span data-stu-id="9c7f9-106">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="9c7f9-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9c7f9-107">Parameters</span></span>

`pFunction`\
<span data-ttu-id="9c7f9-108">[in]呼び出される関数を指定する ICorDebugFunction オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9c7f9-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="9c7f9-109">[in]関数の引数の数。</span><span class="sxs-lookup"><span data-stu-id="9c7f9-109">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="9c7f9-110">[in]関数に渡される引数を指定する ICorDebugValue オブジェクトを指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="9c7f9-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c7f9-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c7f9-111">Remarks</span></span>

<span data-ttu-id="9c7f9-112">関数が仮想場合、`CallFunction`仮想ディスパッチを実行します。</span><span class="sxs-lookup"><span data-stu-id="9c7f9-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="9c7f9-113">関数は、別のアプリケーション ドメインでは、すべての引数がそのアプリケーション ドメイン内にも限りの移行が発生します。</span><span class="sxs-lookup"><span data-stu-id="9c7f9-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c7f9-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="9c7f9-114">Requirements</span></span>

<span data-ttu-id="9c7f9-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c7f9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9c7f9-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c7f9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="9c7f9-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c7f9-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9c7f9-118">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="9c7f9-118">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="9c7f9-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c7f9-119">See also</span></span>

- [<span data-ttu-id="9c7f9-120">CallParameterizedFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="9c7f9-120">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)