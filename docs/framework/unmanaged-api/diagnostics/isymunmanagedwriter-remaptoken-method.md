---
title: ISymUnmanagedWriter::RemapToken メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0ec3f94d290423130e3718b32cd8058f59d797d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694517"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="e0830-102">ISymUnmanagedWriter::RemapToken メソッド</span><span class="sxs-lookup"><span data-stu-id="e0830-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="e0830-103">メタデータ トークンが再マップされたメタデータの生成とするシンボルのライターに通知します。</span><span class="sxs-lookup"><span data-stu-id="e0830-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="e0830-104">シンボルのライターがシンボル ストア内の古いトークンを格納してある場合、読み込みフェーズ中に再マップする対応するシンボル リーダーのマップを保存して格納したトークンを新しい値、またはそのどちらかの更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0830-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0830-105">構文</span><span class="sxs-lookup"><span data-stu-id="e0830-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0830-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0830-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="e0830-107">[in]再マップされたメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="e0830-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="e0830-108">[in]新しいメタデータ トークンを`oldToken`が再マップします。</span><span class="sxs-lookup"><span data-stu-id="e0830-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0830-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="e0830-109">Return Value</span></span>  
 <span data-ttu-id="e0830-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="e0830-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0830-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="e0830-111">Requirements</span></span>  
 <span data-ttu-id="e0830-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e0830-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0830-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0830-113">See also</span></span>
- [<span data-ttu-id="e0830-114">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0830-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
