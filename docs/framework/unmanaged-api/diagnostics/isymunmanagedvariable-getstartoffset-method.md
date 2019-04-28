---
title: ISymUnmanagedVariable::GetStartOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6a30dff869075a201a669d1e703bc003b011fc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797520"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="a649a-102">ISymUnmanagedVariable::GetStartOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="a649a-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="a649a-103">この変数の親内の開始オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="a649a-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="a649a-104">スコープ内のローカル変数の場合は、開始オフセットは、スコープに対して定義されたオフセット内で分類されます。</span><span class="sxs-lookup"><span data-stu-id="a649a-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a649a-105">構文</span><span class="sxs-lookup"><span data-stu-id="a649a-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a649a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a649a-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a649a-107">[out]ポインターを`ULONG32`開始オフセットを受け取る。</span><span class="sxs-lookup"><span data-stu-id="a649a-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a649a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a649a-108">Return Value</span></span>  
 <span data-ttu-id="a649a-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="a649a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a649a-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a649a-110">Requirements</span></span>  
 <span data-ttu-id="a649a-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a649a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a649a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a649a-112">See also</span></span>

- [<span data-ttu-id="a649a-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a649a-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="a649a-114">GetEndOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="a649a-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
