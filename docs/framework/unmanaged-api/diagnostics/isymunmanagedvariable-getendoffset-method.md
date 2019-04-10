---
title: ISymUnmanagedVariable::GetEndOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 325db05cc322d85e836ca9ba62b6a169e8965241
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220956"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="50b41-102">ISymUnmanagedVariable::GetEndOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="50b41-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="50b41-103">親内でこの変数の終了オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="50b41-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="50b41-104">スコープ内でローカル変数の場合は、終了オフセットは、スコープに対して定義されたオフセット内で分類されます。</span><span class="sxs-lookup"><span data-stu-id="50b41-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50b41-105">構文</span><span class="sxs-lookup"><span data-stu-id="50b41-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50b41-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50b41-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="50b41-107">[out]ポインターを`ULONG32`を受け取る、終了オフセット。</span><span class="sxs-lookup"><span data-stu-id="50b41-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50b41-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="50b41-108">Return Value</span></span>  
 <span data-ttu-id="50b41-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="50b41-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50b41-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="50b41-110">Requirements</span></span>  
 <span data-ttu-id="50b41-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="50b41-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b41-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="50b41-112">See also</span></span>

- [<span data-ttu-id="50b41-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50b41-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="50b41-114">GetStartOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="50b41-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
