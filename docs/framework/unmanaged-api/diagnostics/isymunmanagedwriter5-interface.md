---
title: ISymUnmanagedWriter5 インターフェイス
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88a9fa2f720db403c45d4254b17dfaf4689cd0f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706905"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="4d8ae-102">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d8ae-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="4d8ae-103">ISymUnmanagedWriter5 インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4d8ae-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d8ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d8ae-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="4d8ae-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4d8ae-105">Methods</span></span>  
 <span data-ttu-id="4d8ae-106">このインターフェイスには、次のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d8ae-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="4d8ae-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="4d8ae-107">Method</span></span>|<span data-ttu-id="4d8ae-108">説明</span><span class="sxs-lookup"><span data-stu-id="4d8ae-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d8ae-109">CloseMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="4d8ae-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="4d8ae-110">マッピングの情報ソースへのトークンの範囲は、特別なカスタム データのセクションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4d8ae-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="4d8ae-111">閉じられた後は、以上のマッピング情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4d8ae-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="4d8ae-112">MapTokenToSourceSpan メソッド</span><span class="sxs-lookup"><span data-stu-id="4d8ae-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="4d8ae-113">指定したソース ファイルで指定されたソース行に指定したメタデータ トークン span をマップします。</span><span class="sxs-lookup"><span data-stu-id="4d8ae-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="4d8ae-114">呼び出しの間で呼び出す必要がある[OpenMapTokensToSourceSpans メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)と[CloseMapTokensToSourceSpans メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d8ae-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="4d8ae-115">OpenMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="4d8ae-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="4d8ae-116">マップする span ソースへのトークン情報を出力するカスタム データの特別なセクションを開きます。</span><span class="sxs-lookup"><span data-stu-id="4d8ae-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="4d8ae-117">メソッドがまだ開いてまたはその逆の場合、エラーには、このセクションを開くことです。</span><span class="sxs-lookup"><span data-stu-id="4d8ae-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4d8ae-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="4d8ae-118">Requirements</span></span>  
 <span data-ttu-id="4d8ae-119">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4d8ae-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d8ae-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d8ae-120">See also</span></span>
- [<span data-ttu-id="4d8ae-121">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d8ae-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="4d8ae-122">ISymUnmanagedWriter4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d8ae-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
