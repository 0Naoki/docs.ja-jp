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
ms.openlocfilehash: ec4a486b9dfb72c05a9e614fca22626dd84a83f7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468462"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="ecff8-102">ISymUnmanagedWriter::RemapToken メソッド</span><span class="sxs-lookup"><span data-stu-id="ecff8-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="ecff8-103">メタデータ トークンが再マップされたメタデータの生成とするシンボルのライターに通知します。</span><span class="sxs-lookup"><span data-stu-id="ecff8-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="ecff8-104">シンボルのライターがシンボル ストア内の古いトークンを格納してある場合、読み込みフェーズ中に再マップする対応するシンボル リーダーのマップを保存して格納したトークンを新しい値、またはそのどちらかの更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecff8-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecff8-105">構文</span><span class="sxs-lookup"><span data-stu-id="ecff8-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecff8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ecff8-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="ecff8-107">[in]再マップされたメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="ecff8-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="ecff8-108">[in]新しいメタデータ トークンを`oldToken`が再マップします。</span><span class="sxs-lookup"><span data-stu-id="ecff8-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecff8-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ecff8-109">Return Value</span></span>  
 <span data-ttu-id="ecff8-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ecff8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecff8-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="ecff8-111">Requirements</span></span>  
 <span data-ttu-id="ecff8-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ecff8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecff8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecff8-113">See also</span></span>
- [<span data-ttu-id="ecff8-114">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecff8-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
