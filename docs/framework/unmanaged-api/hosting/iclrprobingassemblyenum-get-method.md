---
title: ICLRProbingAssemblyEnum::Get メソッド
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 909e18fe9086fa954ffc389ffe1c6fe49217d2f5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492453"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="42556-102">ICLRProbingAssemblyEnum::Get メソッド</span><span class="sxs-lookup"><span data-stu-id="42556-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="42556-103">指定したインデックス位置には、アセンブリの id を取得します。</span><span class="sxs-lookup"><span data-stu-id="42556-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42556-104">構文</span><span class="sxs-lookup"><span data-stu-id="42556-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42556-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42556-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="42556-106">[in]アセンブリ id を返すの 0 から始まるインデックス。</span><span class="sxs-lookup"><span data-stu-id="42556-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="42556-107">[out]アセンブリの id データを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="42556-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="42556-108">[入力、出力]サイズ、`pwzBuffer`バッファー。</span><span class="sxs-lookup"><span data-stu-id="42556-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42556-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="42556-109">Return Value</span></span>  
  
|<span data-ttu-id="42556-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42556-110">HRESULT</span></span>|<span data-ttu-id="42556-111">説明</span><span class="sxs-lookup"><span data-stu-id="42556-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42556-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="42556-112">S_OK</span></span>|<span data-ttu-id="42556-113">`Get` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="42556-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="42556-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="42556-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="42556-115">`pwzBuffer` が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="42556-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="42556-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="42556-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="42556-117">列挙には、これ以上項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="42556-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="42556-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42556-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42556-119">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="42556-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42556-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42556-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42556-121">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="42556-121">The call timed out.</span></span>|  
|<span data-ttu-id="42556-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42556-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42556-123">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="42556-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42556-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42556-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42556-125">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="42556-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42556-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42556-126">E_FAIL</span></span>|<span data-ttu-id="42556-127">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="42556-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42556-128">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="42556-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42556-129">ホスト メソッドが存在する後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="42556-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42556-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="42556-130">Remarks</span></span>  
 <span data-ttu-id="42556-131">インデックス 0 の id は、プロセッサ アーキテクチャに固有の id です。</span><span class="sxs-lookup"><span data-stu-id="42556-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="42556-132">インデックス 1 の id は、Microsoft intermediate language (MSIL) のアーキテクチャに依存しないアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="42556-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="42556-133">インデックス 2 の id には、アーキテクチャ情報が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="42556-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="42556-134">`Get` 通常は 2 回呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="42556-134">`Get` is typically called twice.</span></span> <span data-ttu-id="42556-135">最初の呼び出しには、null 値が指定されています`pwzBuffer`、設定と`pcchBufferSize`の適切なサイズに`pwzBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="42556-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="42556-136">2 つ目の呼び出しが適切なサイズ指定されています`pwzBuffer`、完了すると標準アセンブリの id データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="42556-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42556-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="42556-137">Requirements</span></span>  
 <span data-ttu-id="42556-138">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42556-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42556-139">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42556-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42556-140">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="42556-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42556-141">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42556-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42556-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="42556-142">See also</span></span>
- [<span data-ttu-id="42556-143">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42556-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="42556-144">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42556-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
