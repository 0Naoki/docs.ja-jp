---
title: ICorRuntimeHost::CloseEnum メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f150fe80302cd03e872ca8bdf5d172caae1ce599
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230773"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="2ac0b-102">ICorRuntimeHost::CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="2ac0b-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="2ac0b-103">ドメイン リストの先頭に戻るには、ドメインの列挙子をリセットします。</span><span class="sxs-lookup"><span data-stu-id="2ac0b-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ac0b-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ac0b-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ac0b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ac0b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="2ac0b-106">[in]リセットする列挙子。</span><span class="sxs-lookup"><span data-stu-id="2ac0b-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ac0b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2ac0b-107">Return Value</span></span>  
  
|<span data-ttu-id="2ac0b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ac0b-108">HRESULT</span></span>|<span data-ttu-id="2ac0b-109">説明</span><span class="sxs-lookup"><span data-stu-id="2ac0b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ac0b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ac0b-110">S_OK</span></span>|<span data-ttu-id="2ac0b-111">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="2ac0b-111">The operation was successful.</span></span>|  
|<span data-ttu-id="2ac0b-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2ac0b-112">S_FALSE</span></span>|<span data-ttu-id="2ac0b-113">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="2ac0b-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="2ac0b-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ac0b-114">E_FAIL</span></span>|<span data-ttu-id="2ac0b-115">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2ac0b-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2ac0b-116">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2ac0b-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="2ac0b-117">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2ac0b-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2ac0b-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ac0b-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ac0b-119">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="2ac0b-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ac0b-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="2ac0b-120">Requirements</span></span>  
 <span data-ttu-id="2ac0b-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ac0b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac0b-122">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ac0b-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ac0b-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2ac0b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ac0b-124">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2ac0b-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac0b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ac0b-125">See also</span></span>

- [<span data-ttu-id="2ac0b-126">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="2ac0b-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="2ac0b-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ac0b-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
