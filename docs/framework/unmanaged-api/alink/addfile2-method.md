---
title: AddFile2 メソッド
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 078820649543479e65ec35daa6e1cc2876581ddc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693202"
---
# <a name="addfile2-method"></a><span data-ttu-id="a48f5-102">AddFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="a48f5-102">AddFile2 Method</span></span>
<span data-ttu-id="a48f5-103">アセンブリには、ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="a48f5-103">Adds files to the assembly.</span></span> <span data-ttu-id="a48f5-104">非バインド モジュールの作成にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a48f5-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a48f5-105">構文</span><span class="sxs-lookup"><span data-stu-id="a48f5-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a48f5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a48f5-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a48f5-107">ファイルを追加するアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="a48f5-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="a48f5-108">追加するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="a48f5-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a48f5-109">COM +`FileDef`などフラグ`ffContainsNoMetaData`と`ffWriteable`します。</span><span class="sxs-lookup"><span data-stu-id="a48f5-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="a48f5-110">`dwFlags` 渡される[DefineFile メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="a48f5-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="a48f5-111">インターフェイスを[IMetaDataEmit2 インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a48f5-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="a48f5-112">追加するファイルの ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a48f5-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a48f5-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="a48f5-113">Return Value</span></span>  
 <span data-ttu-id="a48f5-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="a48f5-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a48f5-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="a48f5-115">Requirements</span></span>  
 <span data-ttu-id="a48f5-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="a48f5-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48f5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a48f5-117">See also</span></span>
- [<span data-ttu-id="a48f5-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a48f5-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a48f5-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a48f5-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a48f5-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="a48f5-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
