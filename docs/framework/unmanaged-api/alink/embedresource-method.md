---
title: EmbedResource メソッド
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51711162613db6c8045d9192e2ca9f1380509be2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556169"
---
# <a name="embedresource-method"></a><span data-ttu-id="67f66-102">EmbedResource メソッド</span><span class="sxs-lookup"><span data-stu-id="67f66-102">EmbedResource Method</span></span>
<span data-ttu-id="67f66-103">埋め込みリソースを宣言します。</span><span class="sxs-lookup"><span data-stu-id="67f66-103">Declares an embedded resource.</span></span> <span data-ttu-id="67f66-104">このメソッドは、リソースを実際には埋め込まれません。</span><span class="sxs-lookup"><span data-stu-id="67f66-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f66-105">構文</span><span class="sxs-lookup"><span data-stu-id="67f66-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67f66-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67f66-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="67f66-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="67f66-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="67f66-108">ファイル リソースを含むファイルのトークンまたはアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="67f66-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="67f66-109">リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="67f66-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="67f66-110">リソースの RVA からのオフセット。</span><span class="sxs-lookup"><span data-stu-id="67f66-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="67f66-111">ユーザー補助フラグなど`mrPublic`と`mrPrivate`します。</span><span class="sxs-lookup"><span data-stu-id="67f66-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="67f66-112">これらのフラグに渡される[DefineExportedType メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="67f66-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67f66-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="67f66-113">Return Value</span></span>  
 <span data-ttu-id="67f66-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="67f66-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67f66-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="67f66-115">Requirements</span></span>  
 <span data-ttu-id="67f66-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="67f66-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f66-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="67f66-117">See also</span></span>
- [<span data-ttu-id="67f66-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67f66-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="67f66-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67f66-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="67f66-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="67f66-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
