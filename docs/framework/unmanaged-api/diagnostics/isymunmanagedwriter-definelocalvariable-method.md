---
title: ISymUnmanagedWriter::DefineLocalVariable メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1361d6e93fcf39a86951a78f1245e9158d6ed314
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483616"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="32dc1-102">ISymUnmanagedWriter::DefineLocalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="32dc1-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="32dc1-103">現在の構文のスコープの変数を 1 つ定義します。</span><span class="sxs-lookup"><span data-stu-id="32dc1-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="32dc1-104">このメソッドをスコープ全体で複数のホームのある同じ名前の変数を複数回呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="32dc1-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="32dc1-105">この場合、ただしの値、`startOffset`と`endOffset`パラメーターが重複しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="32dc1-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32dc1-106">構文</span><span class="sxs-lookup"><span data-stu-id="32dc1-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32dc1-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="32dc1-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="32dc1-108">[in]ポインター、`WCHAR`ローカル変数の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="32dc1-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="32dc1-109">[in]ローカル変数の属性。</span><span class="sxs-lookup"><span data-stu-id="32dc1-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="32dc1-110">[in]A`ULONG32`のサイズ (バイト単位) を示す、`signature`バッファー。</span><span class="sxs-lookup"><span data-stu-id="32dc1-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="32dc1-111">[in]ローカル変数シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="32dc1-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="32dc1-112">[in]アドレスの種類。</span><span class="sxs-lookup"><span data-stu-id="32dc1-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="32dc1-113">[in]パラメーター指定の最初のアドレス。</span><span class="sxs-lookup"><span data-stu-id="32dc1-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="32dc1-114">[in]パラメーター指定の 2 番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="32dc1-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="32dc1-115">[in]パラメーター指定の 3 番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="32dc1-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="32dc1-116">[in]変数の開始オフセット。</span><span class="sxs-lookup"><span data-stu-id="32dc1-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="32dc1-117">このパラメーターは省略できます。</span><span class="sxs-lookup"><span data-stu-id="32dc1-117">This parameter is optional.</span></span> <span data-ttu-id="32dc1-118">0 の場合は、このパラメーターは無視され、スコープ全体で変数が定義されています。</span><span class="sxs-lookup"><span data-stu-id="32dc1-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="32dc1-119">0 以外の値の場合は、現在のスコープのオフセット内、変数となります。</span><span class="sxs-lookup"><span data-stu-id="32dc1-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="32dc1-120">[in]変数の終了オフセット。</span><span class="sxs-lookup"><span data-stu-id="32dc1-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="32dc1-121">このパラメーターは省略できます。</span><span class="sxs-lookup"><span data-stu-id="32dc1-121">This parameter is optional.</span></span> <span data-ttu-id="32dc1-122">0 の場合は、このパラメーターは無視され、スコープ全体で変数が定義されています。</span><span class="sxs-lookup"><span data-stu-id="32dc1-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="32dc1-123">0 以外の値の場合は、現在のスコープのオフセット内、変数となります。</span><span class="sxs-lookup"><span data-stu-id="32dc1-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32dc1-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="32dc1-124">Return Value</span></span>  
 <span data-ttu-id="32dc1-125">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="32dc1-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32dc1-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="32dc1-126">Requirements</span></span>  
 <span data-ttu-id="32dc1-127">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="32dc1-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32dc1-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="32dc1-128">See also</span></span>
- [<span data-ttu-id="32dc1-129">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32dc1-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="32dc1-130">DefineGlobalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="32dc1-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="32dc1-131">DefineLocalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="32dc1-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
