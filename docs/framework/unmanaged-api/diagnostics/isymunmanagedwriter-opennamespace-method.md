---
title: ISymUnmanagedWriter::OpenNamespace メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a108ec27cc4f8ed9d9d3c9227bf6ab0815fa933
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739694"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="bdd4c-102">ISymUnmanagedWriter::OpenNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="bdd4c-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="bdd4c-103">新しい名前空間を開きます。</span><span class="sxs-lookup"><span data-stu-id="bdd4c-103">Opens a new namespace.</span></span> <span data-ttu-id="bdd4c-104">名前空間を使用するメソッドまたは変数を定義する前に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bdd4c-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="bdd4c-105">名前空間を入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bdd4c-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdd4c-106">構文</span><span class="sxs-lookup"><span data-stu-id="bdd4c-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bdd4c-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bdd4c-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="bdd4c-108">[in]新しい名前空間の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bdd4c-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdd4c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bdd4c-109">Return Value</span></span>  
 <span data-ttu-id="bdd4c-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="bdd4c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdd4c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="bdd4c-111">Requirements</span></span>  
 <span data-ttu-id="bdd4c-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bdd4c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd4c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdd4c-113">See also</span></span>
- [<span data-ttu-id="bdd4c-114">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bdd4c-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="bdd4c-115">CloseNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="bdd4c-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
