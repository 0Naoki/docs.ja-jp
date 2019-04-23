---
title: ISymUnmanagedVariable::GetAddressField2 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2030a0da7a84695750d1dd9781adca9cd66f22ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137697"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="97346-102">ISymUnmanagedVariable::GetAddressField2 メソッド</span><span class="sxs-lookup"><span data-stu-id="97346-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="97346-103">この変数の 2 番目のアドレス フィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="97346-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="97346-104">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="97346-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97346-105">構文</span><span class="sxs-lookup"><span data-stu-id="97346-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97346-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="97346-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="97346-107">[out]ポインターを`ULONG32`を受け取る 2 番目のアドレス フィールド。</span><span class="sxs-lookup"><span data-stu-id="97346-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97346-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="97346-108">Return Value</span></span>  
 <span data-ttu-id="97346-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="97346-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97346-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="97346-110">Requirements</span></span>  
 <span data-ttu-id="97346-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="97346-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97346-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="97346-112">See also</span></span>

- [<span data-ttu-id="97346-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97346-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="97346-114">GetAddressField1 メソッド</span><span class="sxs-lookup"><span data-stu-id="97346-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="97346-115">GetAddressField3 メソッド</span><span class="sxs-lookup"><span data-stu-id="97346-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="97346-116">GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="97346-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
