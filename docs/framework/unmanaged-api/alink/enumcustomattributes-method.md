---
title: EnumCustomAttributes メソッド
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b419962982fc80591ed565cceb28afb88a39495e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199142"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="6e0cc-102">EnumCustomAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="6e0cc-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="6e0cc-103">アセンブリ レベルのカスタム属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e0cc-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e0cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e0cc-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e0cc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e0cc-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6e0cc-106">列挙子のハンドル。</span><span class="sxs-lookup"><span data-stu-id="6e0cc-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="6e0cc-107">列挙する属性の型。</span><span class="sxs-lookup"><span data-stu-id="6e0cc-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="6e0cc-108">使用`mdTokenNill`すべての属性。</span><span class="sxs-lookup"><span data-stu-id="6e0cc-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="6e0cc-109">カスタム属性のトークンを受信します。</span><span class="sxs-lookup"><span data-stu-id="6e0cc-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6e0cc-110">サイズを指定`rCustomValues`配列。</span><span class="sxs-lookup"><span data-stu-id="6e0cc-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="6e0cc-111">必要に応じてトークンの値の数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6e0cc-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e0cc-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="6e0cc-112">Return Value</span></span>  
 <span data-ttu-id="6e0cc-113">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="6e0cc-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e0cc-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="6e0cc-114">Requirements</span></span>  
 <span data-ttu-id="6e0cc-115">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="6e0cc-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e0cc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e0cc-116">See also</span></span>

- [<span data-ttu-id="6e0cc-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e0cc-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6e0cc-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e0cc-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6e0cc-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="6e0cc-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
