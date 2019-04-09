---
title: IAssemblyName::GetName メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88a46ecadaf2b191e8321c5629bc77b0c67dfd3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079527"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="79f27-102">IAssemblyName::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="79f27-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="79f27-103">これによって参照されるアセンブリの単純な暗号化されていない名前を取得[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="79f27-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79f27-104">構文</span><span class="sxs-lookup"><span data-stu-id="79f27-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79f27-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="79f27-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="79f27-106">[入力、出力]サイズ`pwzName`ワイド文字、終端の null 文字を含むです。</span><span class="sxs-lookup"><span data-stu-id="79f27-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="79f27-107">[out]参照アセンブリの名前を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="79f27-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79f27-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="79f27-108">Requirements</span></span>  
 <span data-ttu-id="79f27-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79f27-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79f27-110">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="79f27-110">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="79f27-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="79f27-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="79f27-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="79f27-112">See also</span></span>

- [<span data-ttu-id="79f27-113">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79f27-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
