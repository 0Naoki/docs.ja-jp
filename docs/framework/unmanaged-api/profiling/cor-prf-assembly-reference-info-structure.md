---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO 構造体
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 380dbe43c09e0be48410431b87d796f502a7012b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634962"
---
# <a name="corprfassemblyreferenceinfo-structure"></a><span data-ttu-id="3cb75-102">COR_PRF_ASSEMBLY_REFERENCE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="3cb75-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="3cb75-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="3cb75-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3cb75-104">アセンブリ参照クロージャのウォークを実行するときに考慮する必要があるアセンブリ参照の情報を、共通言語ランタイムに提供します。</span><span class="sxs-lookup"><span data-stu-id="3cb75-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cb75-105">構文</span><span class="sxs-lookup"><span data-stu-id="3cb75-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="3cb75-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3cb75-106">Members</span></span>  
  
|<span data-ttu-id="3cb75-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="3cb75-107">Member</span></span>|<span data-ttu-id="3cb75-108">説明</span><span class="sxs-lookup"><span data-stu-id="3cb75-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="3cb75-109">公開キー、またはアセンブリのトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3cb75-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="3cb75-110">公開キーまたはトークンのバイト数。</span><span class="sxs-lookup"><span data-stu-id="3cb75-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="3cb75-111">参照されるアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="3cb75-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="3cb75-112">アセンブリのメタデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3cb75-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="3cb75-113">ハッシュ バイナリ ラージ オブジェクト (BLOB) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3cb75-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="3cb75-114">ハッシュ BLOB のバイト数。</span><span class="sxs-lookup"><span data-stu-id="3cb75-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="3cb75-115">アセンブリのフラグ。</span><span class="sxs-lookup"><span data-stu-id="3cb75-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cb75-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cb75-116">Remarks</span></span>  
 <span data-ttu-id="3cb75-117">`COR_PRF_EX_CLAUSE_INFO` 構造は、追加のアセンブリ参照を宣言するときに、プロファイラーによって値が設定されます。ここでの追加のアセンブリ参照は、アセンブリ参照クロージャのウォークを実行するときに共通言語ランタイムが考慮するものです。</span><span class="sxs-lookup"><span data-stu-id="3cb75-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="3cb75-118">用のプロファイラーを登録する場合、 [icorprofilercallback 6::getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)コールバック メソッド、ランタイムへのポインターと共に読み込まれるアセンブリの名前とパスを渡します、 [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)メソッドへのインターフェイスのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3cb75-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="3cb75-119">プロファイラーを呼び出すことが、 [icorprofilerassemblyreferenceprovider::addassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)メソッドを`COR_PRF_ASSEMBLY_REFERENCE_INFO`で指定されたアセンブリから参照することを計画、各ターゲット アセンブリのオブジェクト、 [Icorprofilercallback 6::getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="3cb75-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cb75-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="3cb75-120">Requirements</span></span>  
 <span data-ttu-id="3cb75-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb75-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cb75-122">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3cb75-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3cb75-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cb75-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cb75-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cb75-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb75-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cb75-125">See also</span></span>
- [<span data-ttu-id="3cb75-126">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="3cb75-126">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
- [<span data-ttu-id="3cb75-127">GetAssemblyReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="3cb75-127">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="3cb75-128">AddAssemblyReference メソッド</span><span class="sxs-lookup"><span data-stu-id="3cb75-128">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
