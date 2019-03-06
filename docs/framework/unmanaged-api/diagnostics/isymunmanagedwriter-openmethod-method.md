---
title: ISymUnmanagedWriter::OpenMethod メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e6ee68fe3ffed0ae19c2f528a49a863b99fa7f7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499551"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="b78de-102">ISymUnmanagedWriter::OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="b78de-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="b78de-103">シンボル情報の生成のメソッドを開きます。</span><span class="sxs-lookup"><span data-stu-id="b78de-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="b78de-104">特定のメソッドでは、シーケンス ポイント、パラメーター、および構文のスコープを定義する呼び出しの現在のメソッドになります。</span><span class="sxs-lookup"><span data-stu-id="b78de-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="b78de-105">メソッド全体を囲む暗黙的な構文のスコープがあります。</span><span class="sxs-lookup"><span data-stu-id="b78de-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="b78de-106">以前に閉じられたメソッドを再び開くには、そのメソッドの以前に定義されたシンボルが消去されます。</span><span class="sxs-lookup"><span data-stu-id="b78de-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="b78de-107">一度に 1 つだけの open メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="b78de-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b78de-108">構文</span><span class="sxs-lookup"><span data-stu-id="b78de-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b78de-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b78de-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="b78de-110">[in]開かれているメソッドのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="b78de-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b78de-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="b78de-111">Return Value</span></span>  
 <span data-ttu-id="b78de-112">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="b78de-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b78de-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="b78de-113">Requirements</span></span>  
 <span data-ttu-id="b78de-114">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b78de-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b78de-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b78de-115">See also</span></span>
- [<span data-ttu-id="b78de-116">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b78de-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="b78de-117">CloseMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="b78de-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="b78de-118">OpenMethod2 メソッド</span><span class="sxs-lookup"><span data-stu-id="b78de-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
