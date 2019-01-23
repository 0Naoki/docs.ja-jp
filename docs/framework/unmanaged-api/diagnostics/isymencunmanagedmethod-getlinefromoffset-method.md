---
title: ISymENCUnmanagedMethod::GetLineFromOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98015af4a79a9fca4945708e6d0baeb61e46876f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531227"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="41a70-102">ISymENCUnmanagedMethod::GetLineFromOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="41a70-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="41a70-103">オフセットに関連付けられている行の情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="41a70-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="41a70-104">場合オフセット パラメーター (`dwOffset`) がシーケンス ポイントでは、このメソッドは、前のオフセットに関連付けられている行の情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="41a70-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a70-105">構文</span><span class="sxs-lookup"><span data-stu-id="41a70-105">Syntax</span></span>  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41a70-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41a70-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="41a70-107">[in]A`ULONG32`オフセットを格納しています。</span><span class="sxs-lookup"><span data-stu-id="41a70-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="41a70-108">[out]ポインターを`ULONG32`行を受け取る。</span><span class="sxs-lookup"><span data-stu-id="41a70-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="41a70-109">[out]ポインター、`ULONG32`列を受け取る。</span><span class="sxs-lookup"><span data-stu-id="41a70-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="41a70-110">[out]ポインター、`ULONG32`最終行を受け取る。</span><span class="sxs-lookup"><span data-stu-id="41a70-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="41a70-111">[out]ポインター、`ULONG32`終了列を受け取る。</span><span class="sxs-lookup"><span data-stu-id="41a70-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="41a70-112">[out]ポインター、`ULONG32`関連付けられているシーケンス ポイントを受け取る。</span><span class="sxs-lookup"><span data-stu-id="41a70-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41a70-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="41a70-113">Return Value</span></span>  
 <span data-ttu-id="41a70-114">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="41a70-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41a70-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="41a70-115">Requirements</span></span>  
 <span data-ttu-id="41a70-116">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="41a70-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a70-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="41a70-117">See also</span></span>
- [<span data-ttu-id="41a70-118">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41a70-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
