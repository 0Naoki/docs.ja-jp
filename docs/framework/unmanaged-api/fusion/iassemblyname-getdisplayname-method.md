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
ms.openlocfilehash: 2d8cbc540377c8f2a26b8fafef35c19e94a59c51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536010"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="3fb6d-102">IAssemblyName::GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="3fb6d-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="3fb6d-103">これによって参照されるアセンブリの人間が判読できる名前を取得[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3fb6d-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb6d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3fb6d-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fb6d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3fb6d-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="3fb6d-106">[out]参照先アセンブリの名前を格納している文字列バッファー。</span><span class="sxs-lookup"><span data-stu-id="3fb6d-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="3fb6d-107">[入力、出力]サイズ`szDisplayName`ワイド文字、終端の null 文字を含むです。</span><span class="sxs-lookup"><span data-stu-id="3fb6d-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="3fb6d-108">[in]ビットごとの組み合わせ[ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md)の機能に影響を与える値`szDisplayName`します。</span><span class="sxs-lookup"><span data-stu-id="3fb6d-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fb6d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="3fb6d-109">Requirements</span></span>  
 <span data-ttu-id="3fb6d-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fb6d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fb6d-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3fb6d-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3fb6d-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fb6d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb6d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3fb6d-113">See also</span></span>
- [<span data-ttu-id="3fb6d-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3fb6d-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="3fb6d-115">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="3fb6d-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
