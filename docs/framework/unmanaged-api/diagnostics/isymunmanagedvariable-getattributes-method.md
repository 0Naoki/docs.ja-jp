---
title: ISymUnmanagedVariable::GetAttributes メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7ba794060330de3934f8d4ca6434b09672d12bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090590"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="e7123-102">ISymUnmanagedVariable::GetAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="e7123-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="e7123-103">この変数の属性フラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="e7123-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7123-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7123-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7123-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7123-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e7123-106">[out]ポインターを`ULONG32`属性を受け取る。</span><span class="sxs-lookup"><span data-stu-id="e7123-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="e7123-107">返される値で定義されている値のいずれかになります、 [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="e7123-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7123-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e7123-108">Return Value</span></span>  
 <span data-ttu-id="e7123-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="e7123-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7123-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e7123-110">Requirements</span></span>  
 <span data-ttu-id="e7123-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e7123-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7123-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7123-112">See also</span></span>

- [<span data-ttu-id="e7123-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7123-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
