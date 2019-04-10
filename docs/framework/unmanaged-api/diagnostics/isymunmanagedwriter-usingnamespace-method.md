---
title: ISymUnmanagedWriter::UsingNamespace メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0739cc38d1f12967f0daef2d6828e04a256ade6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201846"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="7eb47-102">ISymUnmanagedWriter::UsingNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="7eb47-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="7eb47-103">指定した名前空間の完全修飾名が現在開いている構文のスコープ内で使用されているを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eb47-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="7eb47-104">名前空間は、現在開いているスコープから継承するすべてのスコープ内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="7eb47-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="7eb47-105">現在のスコープを閉じると、名前空間の使用も停止されます。</span><span class="sxs-lookup"><span data-stu-id="7eb47-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eb47-106">構文</span><span class="sxs-lookup"><span data-stu-id="7eb47-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eb47-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7eb47-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="7eb47-108">[in]名前空間の完全修飾名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7eb47-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7eb47-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7eb47-109">Return Value</span></span>  
 <span data-ttu-id="7eb47-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="7eb47-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eb47-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7eb47-111">Requirements</span></span>  
 <span data-ttu-id="7eb47-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7eb47-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb47-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eb47-113">See also</span></span>

- [<span data-ttu-id="7eb47-114">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7eb47-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
