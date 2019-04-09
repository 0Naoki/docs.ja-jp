---
title: ICorDebugModule::GetToken メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c28182feff8e4b7d49b7d068da1496d44fa2f917
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150359"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="d0ded-102">ICorDebugModule::GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="d0ded-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="d0ded-103">このモジュールのテーブルのエントリのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d0ded-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0ded-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0ded-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0ded-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0ded-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="d0ded-106">[out]ポインター、`mdModule`モジュールのメタデータを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="d0ded-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0ded-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0ded-107">Remarks</span></span>  
 <span data-ttu-id="d0ded-108">トークンを渡すことができます、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)、 [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)、および[IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)メタデータ インポート インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d0ded-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0ded-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0ded-109">Requirements</span></span>  
 <span data-ttu-id="d0ded-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0ded-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0ded-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0ded-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0ded-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0ded-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d0ded-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d0ded-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d0ded-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0ded-114">See also</span></span>

- [<span data-ttu-id="d0ded-115">メタデータ</span><span class="sxs-lookup"><span data-stu-id="d0ded-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
