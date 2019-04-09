---
title: ISymUnmanagedENCUpdate インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 378322c28d59b2a6e7c09f2f2c4bf55bb019d01d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171841"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="03aa2-102">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="03aa2-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="03aa2-103">関数は、エディット コンティニュの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="03aa2-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03aa2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="03aa2-104">Methods</span></span>  
  
|<span data-ttu-id="03aa2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="03aa2-105">Method</span></span>|<span data-ttu-id="03aa2-106">説明</span><span class="sxs-lookup"><span data-stu-id="03aa2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03aa2-107">GetLocalVariableCount メソッド</span><span class="sxs-lookup"><span data-stu-id="03aa2-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="03aa2-108">ローカル変数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="03aa2-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="03aa2-109">GetLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="03aa2-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="03aa2-110">ローカル変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="03aa2-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="03aa2-111">InitializeForEnc メソッド</span><span class="sxs-lookup"><span data-stu-id="03aa2-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="03aa2-112">により、最初の呼び出しの前に計算するメソッドの境界、 [isymunmanagedencupdate::updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="03aa2-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="03aa2-113">UpdateMethodLines メソッド</span><span class="sxs-lookup"><span data-stu-id="03aa2-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="03aa2-114">再コンパイルされていない、その行が個別に移動されたメソッドの行情報の更新を許可します。</span><span class="sxs-lookup"><span data-stu-id="03aa2-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="03aa2-115">各ステートメントのデルタが許可されます。</span><span class="sxs-lookup"><span data-stu-id="03aa2-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="03aa2-116">UpdateSymbolStore2 メソッド</span><span class="sxs-lookup"><span data-stu-id="03aa2-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="03aa2-117">コンパイラが行情報が要件を満たしていることが、プログラム データベース (PDB) のストリームから変更されていない関数を省略できるようにします。</span><span class="sxs-lookup"><span data-stu-id="03aa2-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="03aa2-118">PDB の行の古い情報と、関数のすべての行の 1 つのデルタは正しい行情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="03aa2-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03aa2-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="03aa2-119">Requirements</span></span>  
 <span data-ttu-id="03aa2-120">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="03aa2-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03aa2-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="03aa2-121">See also</span></span>

- [<span data-ttu-id="03aa2-122">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="03aa2-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
