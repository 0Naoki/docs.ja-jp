---
title: ISymUnmanagedReader::GetGlobalVariables メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3de246c8b9c4387ea782b77f16edfbe792bb4427
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777012"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="95c88-102">ISymUnmanagedReader::GetGlobalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="95c88-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="95c88-103">すべてのグローバル変数を返します。</span><span class="sxs-lookup"><span data-stu-id="95c88-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95c88-104">構文</span><span class="sxs-lookup"><span data-stu-id="95c88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95c88-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="95c88-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="95c88-106">[in]バッファーの長さが指す`pcVars`します。</span><span class="sxs-lookup"><span data-stu-id="95c88-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="95c88-107">[out]ポインター、`ULONG32`変数の格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="95c88-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="95c88-108">[out]変数を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="95c88-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95c88-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="95c88-109">Return Value</span></span>  
 <span data-ttu-id="95c88-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="95c88-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c88-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="95c88-111">Requirements</span></span>  
 <span data-ttu-id="95c88-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="95c88-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c88-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="95c88-113">See also</span></span>

- [<span data-ttu-id="95c88-114">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95c88-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
