---
title: ICLRAssemblyReferenceList::IsAssemblyReferenceInList メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 557b15fe2bd04a3362532f190a88ee2ad52ed366
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499833"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="5c039-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="5c039-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="5c039-103">一覧でアセンブリを参照して、指定されたポインターかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c039-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c039-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c039-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c039-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c039-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="5c039-106">[in]検索対象のアセンブリへのインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="5c039-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="5c039-107">有効な値の種類は`IAssemblyName`または`IReferenceIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="5c039-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c039-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5c039-108">Return Value</span></span>  
  
|<span data-ttu-id="5c039-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c039-109">HRESULT</span></span>|<span data-ttu-id="5c039-110">説明</span><span class="sxs-lookup"><span data-stu-id="5c039-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c039-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c039-111">S_OK</span></span>|<span data-ttu-id="5c039-112">文字列は、一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c039-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="5c039-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5c039-113">S_FALSE</span></span>|<span data-ttu-id="5c039-114">文字列は、一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="5c039-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="5c039-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c039-115">E_FAIL</span></span>|<span data-ttu-id="5c039-116">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5c039-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5c039-117">メソッドには、E_FAIL が返された、後に、共通言語ランタイムは、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5c039-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="5c039-118">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5c039-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c039-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="5c039-119">Requirements</span></span>  
 <span data-ttu-id="5c039-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c039-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c039-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5c039-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c039-122">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5c039-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c039-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c039-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c039-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c039-124">See also</span></span>
- [<span data-ttu-id="5c039-125">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c039-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="5c039-126">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c039-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="5c039-127">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c039-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="5c039-128">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c039-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
