---
title: IDefinitionIdentity インターフェイス
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb97c545d2d57ef589b5a7a5b3618eaa2b6f364f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686999"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="17d39-102">IDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="17d39-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="17d39-103">現在のスコープ内でアプリケーションを定義するコードの一意のシグネチャを表します。</span><span class="sxs-lookup"><span data-stu-id="17d39-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17d39-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="17d39-104">Methods</span></span>  
  
|<span data-ttu-id="17d39-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="17d39-105">Method</span></span>|<span data-ttu-id="17d39-106">説明</span><span class="sxs-lookup"><span data-stu-id="17d39-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="17d39-107">新しいインターフェイス ポインターを取得`IDefinitionIdentity`これと同じであるオブジェクト`IDefinitionIdentity`、指定した属性の変更を除く。</span><span class="sxs-lookup"><span data-stu-id="17d39-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="17d39-108">インターフェイス ポインターを取得、 [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)オブジェクトに関連付けられた属性を含む`IDefinitionIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="17d39-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="17d39-109">指定した名前空間には、指定した名前の属性の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="17d39-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="17d39-110">指定した値を指定した名前空間で指定した名前を持つ属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="17d39-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17d39-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="17d39-111">Requirements</span></span>  
 <span data-ttu-id="17d39-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="17d39-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17d39-113">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="17d39-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="17d39-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17d39-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d39-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="17d39-115">See also</span></span>
- [<span data-ttu-id="17d39-116">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="17d39-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
