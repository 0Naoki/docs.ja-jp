---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset メソッド
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55d35db387d6184f68ff31a74253d3d1610c806f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741252"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="62966-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="62966-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="62966-103">IL オフセットの非同期メソッドをラップする catch のコンパイラによって生成されたハンドラーを設定します。</span><span class="sxs-lookup"><span data-stu-id="62966-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="62966-104">生成された catch の IL オフセットは、場合と非ユーザー コードがユーザー コード メソッドで発生した場合でも、catch を処理するために、デバッガーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="62966-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="62966-105">具体的への応答で使用される、 **CatchHandlerFound**例外イベント。</span><span class="sxs-lookup"><span data-stu-id="62966-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62966-106">構文</span><span class="sxs-lookup"><span data-stu-id="62966-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62966-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62966-107">Parameters</span></span>  
  
|<span data-ttu-id="62966-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62966-108">Parameter</span></span>|<span data-ttu-id="62966-109">説明</span><span class="sxs-lookup"><span data-stu-id="62966-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="62966-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="62966-110">Return Value</span></span>  
 <span data-ttu-id="62966-111">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="62966-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62966-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="62966-112">Requirements</span></span>  
 <span data-ttu-id="62966-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="62966-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62966-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="62966-114">See also</span></span>
- [<span data-ttu-id="62966-115">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62966-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
