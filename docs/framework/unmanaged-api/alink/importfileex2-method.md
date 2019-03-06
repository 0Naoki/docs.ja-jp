---
title: ImportFileEx2 メソッド
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d09877d9ca8dde601d2b515bce63bfdca53b6ab0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498134"
---
# <a name="importfileex2-method"></a><span data-ttu-id="c6a15-102">ImportFileEx2 メソッド</span><span class="sxs-lookup"><span data-stu-id="c6a15-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="c6a15-103">アセンブリとバインドされていないモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c6a15-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="c6a15-104">このメソッドはのように、 [ImportFile メソッド](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)がインポートされるファイルがディスクに存在しない場合でも機能します。</span><span class="sxs-lookup"><span data-stu-id="c6a15-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6a15-105">構文</span><span class="sxs-lookup"><span data-stu-id="c6a15-105">Syntax</span></span>  
  
```  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6a15-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6a15-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="c6a15-107">インポートするファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c6a15-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="c6a15-108">ターゲット ファイルの名前を省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c6a15-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="c6a15-109">省略可能なインポート スコープ[IMetaDataAssemblyImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c6a15-109">Optional import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="c6a15-110">TRUE の場合は、ImportTypes が使用されますが、それ以外の場合にインポートし、手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6a15-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="c6a15-111">渡すフラグ[OpenScope メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6a15-111">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="c6a15-112">アセンブリまたはファイルの一意の ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c6a15-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="c6a15-113">アセンブリ インポート スコープを受け取る[IMetaDataAssemblyImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c6a15-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="c6a15-114">ファイルはアセンブリでない場合、NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6a15-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="c6a15-115">ファイルやインポートされたスコープの数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c6a15-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6a15-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="c6a15-116">Return Value</span></span>  
 <span data-ttu-id="c6a15-117">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="c6a15-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6a15-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="c6a15-118">Requirements</span></span>  
 <span data-ttu-id="c6a15-119">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6a15-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a15-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6a15-120">See also</span></span>
- [<span data-ttu-id="c6a15-121">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6a15-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c6a15-122">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6a15-122">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c6a15-123">ALink API</span><span class="sxs-lookup"><span data-stu-id="c6a15-123">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
