---
title: GetScope メソッド
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8de6c745b1d32c3d98f1b54e822ab084f0574b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486200"
---
# <a name="getscope-method"></a><span data-ttu-id="cc314-102">GetScope メソッド</span><span class="sxs-lookup"><span data-stu-id="cc314-102">GetScope Method</span></span>
<span data-ttu-id="cc314-103">インポート スコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="cc314-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc314-104">構文</span><span class="sxs-lookup"><span data-stu-id="cc314-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc314-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cc314-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cc314-106">インポート先のアセンブリの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="cc314-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="cc314-107">インポートするファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="cc314-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="cc314-108">インポートする 0 から始まるスコープです。</span><span class="sxs-lookup"><span data-stu-id="cc314-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="cc314-109">受信[IMetaDataImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)スコープのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="cc314-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc314-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="cc314-110">Return Value</span></span>  
 <span data-ttu-id="cc314-111">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="cc314-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc314-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="cc314-112">Requirements</span></span>  
 <span data-ttu-id="cc314-113">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="cc314-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc314-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc314-114">See also</span></span>
- [<span data-ttu-id="cc314-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc314-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="cc314-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc314-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="cc314-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="cc314-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
