---
title: ICorRuntimeHost::CreateEvidence メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca54f779d257314b843838d90ca9996f1eb3237b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081831"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="486e5-102">ICorRuntimeHost::CreateEvidence メソッド</span><span class="sxs-lookup"><span data-stu-id="486e5-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="486e5-103">型のインターフェイス ポインターを取得<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>、ホストに渡すセキュリティ証拠を作成することができます、 [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)または[CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="486e5-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="486e5-104">構文</span><span class="sxs-lookup"><span data-stu-id="486e5-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="486e5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="486e5-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="486e5-106">[out]インターフェイス ポインターを<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>インスタンスのセキュリティ証拠を作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="486e5-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="486e5-107">このポインターは型指定`IUnknown`呼び出し元が呼び出す通常必要がありますので、`QueryInterface`へのポインターを取得するには、このインターフェイスで、<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="486e5-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="486e5-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="486e5-108">Return Value</span></span>  
  
|<span data-ttu-id="486e5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="486e5-109">HRESULT</span></span>|<span data-ttu-id="486e5-110">説明</span><span class="sxs-lookup"><span data-stu-id="486e5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="486e5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="486e5-111">S_OK</span></span>|<span data-ttu-id="486e5-112">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="486e5-112">The operation was successful.</span></span>|  
|<span data-ttu-id="486e5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="486e5-113">S_FALSE</span></span>|<span data-ttu-id="486e5-114">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="486e5-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="486e5-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="486e5-115">E_FAIL</span></span>|<span data-ttu-id="486e5-116">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="486e5-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="486e5-117">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="486e5-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="486e5-118">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="486e5-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="486e5-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="486e5-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="486e5-120">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="486e5-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="486e5-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="486e5-121">Remarks</span></span>  
 <span data-ttu-id="486e5-122">このメソッドは、ネイティブ コードから設定することはできません、空のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="486e5-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="486e5-123">使用する必要があります、<xref:System.Security.Policy.Evidence>メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="486e5-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="486e5-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="486e5-124">Requirements</span></span>  
 <span data-ttu-id="486e5-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="486e5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="486e5-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="486e5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="486e5-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="486e5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="486e5-128">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="486e5-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486e5-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="486e5-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="486e5-130">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="486e5-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
