---
title: ImportFileEx メソッド
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b3cf91ad4e048ddfccb4086f36923f33d754ac0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131041"
---
# <a name="importfileex-method"></a><span data-ttu-id="21522-102">ImportFileEx メソッド</span><span class="sxs-lookup"><span data-stu-id="21522-102">ImportFileEx Method</span></span>
<span data-ttu-id="21522-103">インポートには、アセンブリまたはバインドされていないモジュールが示されます。</span><span class="sxs-lookup"><span data-stu-id="21522-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21522-104">構文</span><span class="sxs-lookup"><span data-stu-id="21522-104">Syntax</span></span>  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="21522-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="21522-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="21522-106">インポート元のファイルの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="21522-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="21522-107">ターゲット ファイルの名前を省略可能です。</span><span class="sxs-lookup"><span data-stu-id="21522-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="21522-108">TRUE の場合は、ImportTypes が使用されますが、それ以外の場合にインポートし、手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21522-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="21522-109">渡すフラグ[OpenScope メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="21522-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="21522-110">インポートされるファイルの ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="21522-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="21522-111">アセンブリ インポート スコープを受け取る[IMetaDataAssemblyImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="21522-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="21522-112">ファイルはアセンブリでない場合、NULL に設定されます。</span><span class="sxs-lookup"><span data-stu-id="21522-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="21522-113">インポートされたファイルやスコープの数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="21522-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21522-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="21522-114">Return Value</span></span>  
 <span data-ttu-id="21522-115">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="21522-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21522-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="21522-116">Requirements</span></span>  
 <span data-ttu-id="21522-117">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="21522-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21522-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="21522-118">See also</span></span>

- [<span data-ttu-id="21522-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21522-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="21522-120">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21522-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="21522-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="21522-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
