---
title: ISymUnmanagedWriter::DefineGlobalVariable メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bba8d887bc516149135aae61c4f9bdb9a9e0c9d9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470537"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="85c4e-102">ISymUnmanagedWriter::DefineGlobalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="85c4e-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="85c4e-103">1 つのグローバル変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="85c4e-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c4e-104">構文</span><span class="sxs-lookup"><span data-stu-id="85c4e-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85c4e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="85c4e-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="85c4e-106">[in]ポインター、`WCHAR`グローバル変数の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="85c4e-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="85c4e-107">[in]グローバル変数の属性。</span><span class="sxs-lookup"><span data-stu-id="85c4e-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="85c4e-108">[in]A`ULONG32`の文字数、サイズを示す、`signature`バッファー。</span><span class="sxs-lookup"><span data-stu-id="85c4e-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="85c4e-109">[in]グローバル変数シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="85c4e-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="85c4e-110">[in]アドレスの種類。</span><span class="sxs-lookup"><span data-stu-id="85c4e-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="85c4e-111">[in]パラメーター指定の最初のアドレス。</span><span class="sxs-lookup"><span data-stu-id="85c4e-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="85c4e-112">[in]パラメーター指定の 2 番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="85c4e-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="85c4e-113">[in]パラメーター指定の 3 番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="85c4e-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85c4e-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="85c4e-114">Return Value</span></span>  
 <span data-ttu-id="85c4e-115">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="85c4e-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c4e-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="85c4e-116">Requirements</span></span>  
 <span data-ttu-id="85c4e-117">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="85c4e-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c4e-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="85c4e-118">See also</span></span>
- [<span data-ttu-id="85c4e-119">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="85c4e-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="85c4e-120">DefineLocalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="85c4e-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="85c4e-121">DefineGlobalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="85c4e-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)
