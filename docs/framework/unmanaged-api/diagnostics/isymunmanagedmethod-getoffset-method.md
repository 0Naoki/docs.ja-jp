---
title: ISymUnmanagedMethod::GetOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6485688c2964d477f0c5f68a3da714f084fa308f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515304"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="22017-102">ISymUnmanagedMethod::GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="22017-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="22017-103">ドキュメント内の位置を指定するには、対応するこのメソッド内のオフセットを返します。</span><span class="sxs-lookup"><span data-stu-id="22017-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22017-104">構文</span><span class="sxs-lookup"><span data-stu-id="22017-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22017-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22017-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="22017-106">[in]オフセットを要求する対象のドキュメントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="22017-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="22017-107">[in]オフセットを要求する対象のドキュメント行。</span><span class="sxs-lookup"><span data-stu-id="22017-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="22017-108">[in]オフセットが要求されるドキュメント列。</span><span class="sxs-lookup"><span data-stu-id="22017-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="22017-109">[out]ポインター、`ULONG32`オフセットを受け取る。</span><span class="sxs-lookup"><span data-stu-id="22017-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22017-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="22017-110">Return Value</span></span>  
 <span data-ttu-id="22017-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="22017-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22017-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="22017-112">Requirements</span></span>  
 <span data-ttu-id="22017-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="22017-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22017-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="22017-114">See also</span></span>
- [<span data-ttu-id="22017-115">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22017-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
