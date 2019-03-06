---
title: IAssemblyName::GetDisplayName メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddcfe7a4066686da918cf5ed93aebec0d6f306f5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482042"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="e8622-102">IAssemblyName::GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="e8622-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="e8622-103">これによって参照されるアセンブリの人間が判読できる名前を取得[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e8622-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8622-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8622-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8622-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8622-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="e8622-106">[out]参照先アセンブリの名前を格納している文字列バッファー。</span><span class="sxs-lookup"><span data-stu-id="e8622-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="e8622-107">[入力、出力]サイズ`szDisplayName`ワイド文字、終端の null 文字を含むです。</span><span class="sxs-lookup"><span data-stu-id="e8622-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="e8622-108">[in]ビットごとの組み合わせ[ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md)の機能に影響を与える値`szDisplayName`します。</span><span class="sxs-lookup"><span data-stu-id="e8622-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8622-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e8622-109">Requirements</span></span>  
 <span data-ttu-id="e8622-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8622-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8622-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e8622-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e8622-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8622-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8622-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8622-113">See also</span></span>
- [<span data-ttu-id="e8622-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e8622-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="e8622-115">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="e8622-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
