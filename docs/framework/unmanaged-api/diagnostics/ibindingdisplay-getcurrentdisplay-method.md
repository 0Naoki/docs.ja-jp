---
title: IBindingDisplay::GetCurrentDisplay メソッド
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f9cc44db9c93a8b018d0586bc1faeda7cfbc9bc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498433"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="0dc81-102">IBindingDisplay::GetCurrentDisplay メソッド</span><span class="sxs-lookup"><span data-stu-id="0dc81-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="0dc81-103">現在のバインディングの表示情報を返します。</span><span class="sxs-lookup"><span data-stu-id="0dc81-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc81-104">構文</span><span class="sxs-lookup"><span data-stu-id="0dc81-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dc81-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0dc81-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="0dc81-106">[out, retval]バインドの表示情報を含む safearray へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0dc81-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dc81-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0dc81-107">Remarks</span></span>  
 <span data-ttu-id="0dc81-108">[Ibindingdisplay::initializeforprocess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)メソッドが以前に成功しましたが、デバッガーでプログラムを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc81-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="0dc81-109">呼び出し元の返される割り当てを解除する必要があります`SAFEARRAY`を使用してメモリ[SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)します。</span><span class="sxs-lookup"><span data-stu-id="0dc81-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dc81-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="0dc81-110">Requirements</span></span>  
 <span data-ttu-id="0dc81-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dc81-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dc81-112">**ヘッダー:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="0dc81-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="0dc81-113">**ライブラリ:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="0dc81-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="0dc81-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dc81-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc81-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dc81-115">See also</span></span>
- [<span data-ttu-id="0dc81-116">IBindingDisplay インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0dc81-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="0dc81-117">InitializeForProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="0dc81-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
