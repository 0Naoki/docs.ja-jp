---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset メソッド
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d000e61736f3250c677014cce50a2b7dcdecf1b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491688"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="a5ee8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="a5ee8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="a5ee8-103">IL オフセットの非同期メソッドをラップする catch のコンパイラによって生成されたハンドラーを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5ee8-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="a5ee8-104">生成された catch の IL オフセットは、場合と非ユーザー コードがユーザー コード メソッドで発生した場合でも、catch を処理するために、デバッガーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5ee8-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="a5ee8-105">具体的への応答で使用される、 **CatchHandlerFound**例外イベント。</span><span class="sxs-lookup"><span data-stu-id="a5ee8-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ee8-106">構文</span><span class="sxs-lookup"><span data-stu-id="a5ee8-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5ee8-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5ee8-107">Parameters</span></span>  
  
|<span data-ttu-id="a5ee8-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5ee8-108">Parameter</span></span>|<span data-ttu-id="a5ee8-109">説明</span><span class="sxs-lookup"><span data-stu-id="a5ee8-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="a5ee8-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5ee8-110">Return Value</span></span>  
 <span data-ttu-id="a5ee8-111">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="a5ee8-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5ee8-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a5ee8-112">Requirements</span></span>  
 <span data-ttu-id="a5ee8-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a5ee8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ee8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5ee8-114">See also</span></span>
- [<span data-ttu-id="a5ee8-115">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5ee8-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
