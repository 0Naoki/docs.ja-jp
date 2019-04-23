---
title: ICLRDataTarget::GetImageBase メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e823911280f52e16c745c9c77fe17b49bd35dc0b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129832"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="6a598-102">ICLRDataTarget::GetImageBase メソッド</span><span class="sxs-lookup"><span data-stu-id="6a598-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="6a598-103">指定したイメージのメモリのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a598-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a598-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a598-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a598-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a598-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="6a598-106">[in]そのパスを含む、イメージのファイル名。</span><span class="sxs-lookup"><span data-stu-id="6a598-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="6a598-107">[out]イメージのベース アドレスを格納する CLRDATA_ADDRESS へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6a598-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a598-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a598-108">Remarks</span></span>  
 <span data-ttu-id="6a598-109">イメージのファイル名では、可能性がありますか、パスがない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a598-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="6a598-110">照合はパス全体で行われますパスが指定されている場合それ以外の場合、照合はファイル名でのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="6a598-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a598-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6a598-111">Requirements</span></span>  
 <span data-ttu-id="6a598-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a598-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a598-113">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="6a598-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6a598-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a598-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a598-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a598-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a598-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a598-116">See also</span></span>

- [<span data-ttu-id="6a598-117">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a598-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
