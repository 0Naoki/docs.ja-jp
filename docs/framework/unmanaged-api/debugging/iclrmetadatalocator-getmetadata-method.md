---
title: ICLRMetadataLocator::GetMetadata メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e677aefd5420f71867c1f11a2c9408c77d305c45
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161383"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="63934-102">ICLRMetadataLocator::GetMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="63934-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="63934-103">イメージのメタデータを取得する共通言語ランタイム (CLR) データ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="63934-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63934-104">構文</span><span class="sxs-lookup"><span data-stu-id="63934-104">Syntax</span></span>  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63934-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63934-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="63934-106">[in]イメージ ファイルのパスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="63934-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="63934-107">[in]イメージ ファイルのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="63934-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="63934-108">[in]イメージ ファイルのサイズ。</span><span class="sxs-lookup"><span data-stu-id="63934-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="63934-109">[in]イメージのグローバルに一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="63934-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="63934-110">[in]メタデータの相対仮想アドレス (RVA)。</span><span class="sxs-lookup"><span data-stu-id="63934-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="63934-111">アドレスは、イメージのベース アドレスに対して相対的です。</span><span class="sxs-lookup"><span data-stu-id="63934-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="63934-112">[in]将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="63934-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="63934-113">[in]メタデータの配置先となるバッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="63934-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="63934-114">[out]メタデータの配置先となるバッファー。</span><span class="sxs-lookup"><span data-stu-id="63934-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="63934-115">[out]返されるメタデータのサイズ。</span><span class="sxs-lookup"><span data-stu-id="63934-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63934-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="63934-116">Remarks</span></span>  
 <span data-ttu-id="63934-117">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="63934-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63934-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="63934-118">Requirements</span></span>  
 <span data-ttu-id="63934-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63934-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63934-120">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="63934-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="63934-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63934-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="63934-122">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="63934-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63934-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="63934-123">See also</span></span>

- [<span data-ttu-id="63934-124">ICLRMetadataLocator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63934-124">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
