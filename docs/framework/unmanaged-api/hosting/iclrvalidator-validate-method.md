---
title: ICLRValidator::Validate メソッド
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 559c265c70c199e64782ba185d4925d293d6a778
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158692"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="634f0-102">ICLRValidator::Validate メソッド</span><span class="sxs-lookup"><span data-stu-id="634f0-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="634f0-103">ポータブル実行可能 (PE) または Microsoft intermediate language (MSIL) で指定されたファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="634f0-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="634f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="634f0-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);      
```  
  
## <a name="parameters"></a><span data-ttu-id="634f0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="634f0-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="634f0-106">[in]ポインター、`IVEHandler`検証エラーを処理するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="634f0-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="634f0-107">[in]現在の識別子<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="634f0-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="634f0-108">[in]組み合わせた[ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)を実行する検証の種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="634f0-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="634f0-109">[in]検証を終了する前に許可されるエラーの最大数。</span><span class="sxs-lookup"><span data-stu-id="634f0-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="634f0-110">[in]使用されていません。</span><span class="sxs-lookup"><span data-stu-id="634f0-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="634f0-111">[in]検証するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="634f0-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="634f0-112">[in]ファイル バッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="634f0-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="634f0-113">[in]検証するファイルのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="634f0-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="634f0-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="634f0-114">Return Value</span></span>  
  
|<span data-ttu-id="634f0-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="634f0-115">HRESULT</span></span>|<span data-ttu-id="634f0-116">説明</span><span class="sxs-lookup"><span data-stu-id="634f0-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="634f0-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="634f0-117">S_OK</span></span>|<span data-ttu-id="634f0-118">`Validate` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="634f0-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="634f0-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="634f0-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="634f0-120">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="634f0-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="634f0-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="634f0-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="634f0-122">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="634f0-122">The call timed out.</span></span>|  
|<span data-ttu-id="634f0-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="634f0-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="634f0-124">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="634f0-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="634f0-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="634f0-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="634f0-126">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="634f0-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="634f0-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="634f0-127">E_FAIL</span></span>|<span data-ttu-id="634f0-128">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="634f0-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="634f0-129">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="634f0-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="634f0-130">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="634f0-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="634f0-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="634f0-131">Requirements</span></span>  
 <span data-ttu-id="634f0-132">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="634f0-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="634f0-133">**ヘッダー:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="634f0-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="634f0-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="634f0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="634f0-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="634f0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="634f0-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="634f0-136">See also</span></span>

- [<span data-ttu-id="634f0-137">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="634f0-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
