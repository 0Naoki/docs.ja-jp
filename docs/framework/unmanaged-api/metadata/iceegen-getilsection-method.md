---
title: ICeeGen::GetIlSection メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e9d71edc580591b698ad039f8ee73e49c4e1d6a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489047"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="6fa07-102">ICeeGen::GetIlSection メソッド</span><span class="sxs-lookup"><span data-stu-id="6fa07-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="6fa07-103">指定したハンドルによって参照される基本の中間言語コードのセクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="6fa07-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="6fa07-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa07-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa07-105">構文</span><span class="sxs-lookup"><span data-stu-id="6fa07-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fa07-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fa07-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="6fa07-107">[in]取得するセクションへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="6fa07-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fa07-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="6fa07-108">Requirements</span></span>  
 <span data-ttu-id="6fa07-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa07-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa07-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6fa07-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fa07-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6fa07-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6fa07-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa07-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa07-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fa07-113">See also</span></span>
- [<span data-ttu-id="6fa07-114">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fa07-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
