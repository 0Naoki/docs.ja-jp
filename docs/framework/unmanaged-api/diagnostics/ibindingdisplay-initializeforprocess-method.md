---
title: IBindingDisplay::InitializeForProcess メソッド
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aabad159b521207fed976636ae8b9e338f09ac42
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466181"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="e8280-102">IBindingDisplay::InitializeForProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="e8280-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="e8280-103">初期化します、 [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e8280-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8280-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8280-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8280-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8280-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="e8280-106">[in]プロセス識別子。</span><span class="sxs-lookup"><span data-stu-id="e8280-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8280-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e8280-107">Remarks</span></span>  
 <span data-ttu-id="e8280-108">デバッガーの呼び出し、`InitializeForProcess`バインディングの表示を初期化するためには、作成時のメソッド。</span><span class="sxs-lookup"><span data-stu-id="e8280-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="e8280-109">`InitializeForProcess` その他のメソッドの前に、作成時に呼び出す必要があります`IBindingDisplay`が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e8280-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8280-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e8280-110">Requirements</span></span>  
 <span data-ttu-id="e8280-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8280-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8280-112">**ヘッダー:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="e8280-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="e8280-113">**ライブラリ:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="e8280-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="e8280-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8280-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8280-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8280-115">See also</span></span>
- [<span data-ttu-id="e8280-116">IBindingDisplay インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e8280-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
