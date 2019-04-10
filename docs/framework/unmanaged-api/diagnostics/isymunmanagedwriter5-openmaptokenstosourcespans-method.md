---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans メソッド
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dc2ced988f7277c994eb9449e7c26efa5450b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222680"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="2bc0b-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="2bc0b-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="2bc0b-103">マップする span ソースへのトークン情報を出力するカスタム データの特別なセクションを開きます。</span><span class="sxs-lookup"><span data-stu-id="2bc0b-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="2bc0b-104">メソッドがまだ開いてまたはその逆の場合、エラーには、このセクションを開くことです。</span><span class="sxs-lookup"><span data-stu-id="2bc0b-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc0b-105">構文</span><span class="sxs-lookup"><span data-stu-id="2bc0b-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2bc0b-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="2bc0b-106">Return Value</span></span>  
 <span data-ttu-id="2bc0b-107">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="2bc0b-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc0b-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bc0b-108">Requirements</span></span>  
 <span data-ttu-id="2bc0b-109">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2bc0b-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc0b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bc0b-110">See also</span></span>

- [<span data-ttu-id="2bc0b-111">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bc0b-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
