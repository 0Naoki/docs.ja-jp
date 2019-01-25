---
title: ICLRDebuggingLibraryProvider インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9d851a31cbbf429f49b9f369ce9bc03fa110b5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731986"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="12acd-102">ICLRDebuggingLibraryProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12acd-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="12acd-103">含まれています、 [ProvideLibrary メソッド](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)メソッドで、ライブラリ プロバイダーの共通言語ランタイム バージョン固有デバッグ ライブラリを検索しに読み込む要求を許可するコールバック インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="12acd-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12acd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="12acd-104">Methods</span></span>  
  
|<span data-ttu-id="12acd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="12acd-105">Method</span></span>|<span data-ttu-id="12acd-106">説明</span><span class="sxs-lookup"><span data-stu-id="12acd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12acd-107">ProvideLibrary メソッド</span><span class="sxs-lookup"><span data-stu-id="12acd-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="12acd-108">デバッグ ライブラリの読み込みに使用できるモジュールを識別するハンドルを提供するデバッガーを使用します。</span><span class="sxs-lookup"><span data-stu-id="12acd-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12acd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="12acd-109">Requirements</span></span>  
 <span data-ttu-id="12acd-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12acd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12acd-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12acd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12acd-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12acd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12acd-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12acd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12acd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="12acd-114">See also</span></span>
- [<span data-ttu-id="12acd-115">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12acd-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="12acd-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="12acd-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
