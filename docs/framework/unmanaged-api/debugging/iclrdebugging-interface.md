---
title: ICLRDebugging インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6edee34c8560c989040475fee4a35c6bd2ddb3e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155715"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="18a24-102">ICLRDebugging インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18a24-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="18a24-103">デバッグ用にモジュールの読み込みとアンロードを処理するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="18a24-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18a24-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="18a24-104">Methods</span></span>  
  
|<span data-ttu-id="18a24-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="18a24-105">Method</span></span>|<span data-ttu-id="18a24-106">説明</span><span class="sxs-lookup"><span data-stu-id="18a24-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18a24-107">OpenVirtualProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="18a24-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="18a24-108">プロセスに読み込まれている共通言語ランタイム (CLR) モジュールに対応する"ICorDebugProcess"インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="18a24-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="18a24-109">CanUnloadNow メソッド</span><span class="sxs-lookup"><span data-stu-id="18a24-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="18a24-110">ライブラリで提供されているかどうかを決定する、 [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)インターフェイスが使用されている、またはアンロードできます。</span><span class="sxs-lookup"><span data-stu-id="18a24-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18a24-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="18a24-111">Remarks</span></span>  
 <span data-ttu-id="18a24-112">インスタンスを取得することができます、`ICLRDebugging`インターフェイスを使用して、 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="18a24-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18a24-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="18a24-113">Requirements</span></span>  
 <span data-ttu-id="18a24-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="18a24-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18a24-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18a24-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18a24-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18a24-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18a24-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18a24-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a24-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="18a24-118">See also</span></span>

- [<span data-ttu-id="18a24-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18a24-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="18a24-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="18a24-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
