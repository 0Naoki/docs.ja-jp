---
title: ISymUnmanagedScope2 インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: beb48835039f142ea1d9e18871f77ada1b6f4f3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706314"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="87c3e-102">ISymUnmanagedScope2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87c3e-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="87c3e-103">メソッド内での構文のスコープを表します。</span><span class="sxs-lookup"><span data-stu-id="87c3e-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="87c3e-104">このインターフェイスは、拡張、 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)スコープ内で定義されている定数に関する情報を取得するメソッドを持つインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="87c3e-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87c3e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="87c3e-105">Methods</span></span>  
  
|<span data-ttu-id="87c3e-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="87c3e-106">Method</span></span>|<span data-ttu-id="87c3e-107">説明</span><span class="sxs-lookup"><span data-stu-id="87c3e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87c3e-108">GetConstantCount メソッド</span><span class="sxs-lookup"><span data-stu-id="87c3e-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="87c3e-109">このスコープ内で定義されている定数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="87c3e-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="87c3e-110">GetConstants メソッド</span><span class="sxs-lookup"><span data-stu-id="87c3e-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="87c3e-111">このスコープ内で定義されているローカル定数を取得します。</span><span class="sxs-lookup"><span data-stu-id="87c3e-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87c3e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="87c3e-112">Requirements</span></span>  
 <span data-ttu-id="87c3e-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="87c3e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c3e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="87c3e-114">See also</span></span>
- [<span data-ttu-id="87c3e-115">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87c3e-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="87c3e-116">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87c3e-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
