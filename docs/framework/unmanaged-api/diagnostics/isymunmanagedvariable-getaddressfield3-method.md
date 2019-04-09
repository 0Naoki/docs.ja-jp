---
title: ISymUnmanagedVariable::GetAddressField3 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8b03b96c8cab43046d109d0dd11ae135cb70c9f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163609"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="4e9a2-102">ISymUnmanagedVariable::GetAddressField3 メソッド</span><span class="sxs-lookup"><span data-stu-id="4e9a2-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="4e9a2-103">この変数の 3 番目のアドレス フィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e9a2-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="4e9a2-104">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4e9a2-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e9a2-105">構文</span><span class="sxs-lookup"><span data-stu-id="4e9a2-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e9a2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e9a2-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4e9a2-107">[out]ポインターを`ULONG32`を受け取る 3 番目のアドレス フィールド。</span><span class="sxs-lookup"><span data-stu-id="4e9a2-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e9a2-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="4e9a2-108">Return Value</span></span>  
 <span data-ttu-id="4e9a2-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="4e9a2-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e9a2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4e9a2-110">Requirements</span></span>  
 <span data-ttu-id="4e9a2-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4e9a2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e9a2-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e9a2-112">See also</span></span>

- [<span data-ttu-id="4e9a2-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4e9a2-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="4e9a2-114">GetAddressField1 メソッド</span><span class="sxs-lookup"><span data-stu-id="4e9a2-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="4e9a2-115">GetAddressField2 メソッド</span><span class="sxs-lookup"><span data-stu-id="4e9a2-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="4e9a2-116">GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="4e9a2-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
