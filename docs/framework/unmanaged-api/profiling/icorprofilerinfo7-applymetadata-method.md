---
title: ICorProfilerInfo7::ApplyMetaData メソッド
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5caf7b5e24ac5e583420b45c563f53b8988f1e00
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332664"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="cd89c-102">ICorProfilerInfo7::ApplyMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="cd89c-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="cd89c-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="cd89c-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="cd89c-104">新しく定義されたメタデータを適用、`IMetadataEmit::Define*`メソッドが指定されたモジュールにします。</span><span class="sxs-lookup"><span data-stu-id="cd89c-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd89c-105">構文</span><span class="sxs-lookup"><span data-stu-id="cd89c-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd89c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd89c-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="cd89c-107">[in]変更されたメタデータを持つモジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="cd89c-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd89c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="cd89c-108">Remarks</span></span>  
 <span data-ttu-id="cd89c-109">後のメタデータの変更が加えられた場合、 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバック、新しいメタデータを使用する前にこのメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd89c-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="cd89c-110">`ApplyMetaData` 次の種類のメタデータを追加するにのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cd89c-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="cd89c-111">`AssemblyRef` レコードは、呼び出すことによって作成する、 [imetadataassemblyemit::defineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="cd89c-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="cd89c-112">メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="cd89c-112">method.</span></span>  
  
-   <span data-ttu-id="cd89c-113">`TypeRef` レコードは、呼び出すことによって作成する、 [imetadataemit::definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd89c-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="cd89c-114">`TypeSpec` レコードは、呼び出すことによって作成する、 [imetadataemit::gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd89c-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="cd89c-115">`MemberRef` レコードは、呼び出すことによって作成する、 [imetadataemit::definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd89c-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="cd89c-116">`MemberSpec` レコードは、呼び出すことによって作成する、 [imetadataemit 2::definemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd89c-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="cd89c-117">`UserString` レコードは、呼び出すことによって作成する、 [imetadataemit::defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd89c-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="cd89c-118">.NET Core の 3.0 以降`ApplyMetaData`も次の種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="cd89c-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="cd89c-119">`TypeDef` レコードは、呼び出すことによって作成する、 [imetadataemit::definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd89c-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="cd89c-120">`MethodDef` レコードは、呼び出すことによって作成する、 [imetadataemit::definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd89c-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="cd89c-121">ただし、既存の型に仮想メソッドを追加することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cd89c-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="cd89c-122">前に仮想メソッドを追加する必要があります、 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="cd89c-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd89c-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="cd89c-123">Requirements</span></span>  
 <span data-ttu-id="cd89c-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd89c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd89c-125">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cd89c-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cd89c-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd89c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd89c-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd89c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd89c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd89c-128">See also</span></span>
- [<span data-ttu-id="cd89c-129">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd89c-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
