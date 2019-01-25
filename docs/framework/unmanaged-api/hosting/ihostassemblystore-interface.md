---
title: IHostAssemblyStore インターフェイス
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3714f31d0ab58584a8671055cf4c607f04a832c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611060"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="73c57-102">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73c57-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="73c57-103">アセンブリおよび共通言語ランタイム (CLR) とは無関係にモジュールの読み込みにホストできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="73c57-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73c57-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="73c57-104">Methods</span></span>  
  
|<span data-ttu-id="73c57-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="73c57-105">Method</span></span>|<span data-ttu-id="73c57-106">説明</span><span class="sxs-lookup"><span data-stu-id="73c57-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73c57-107">ProvideAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="73c57-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="73c57-108">によって参照されているアセンブリへの参照を取得、 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)への呼び出しから返された[ihostassemblymanager::getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="73c57-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="73c57-109">ProvideModule メソッド</span><span class="sxs-lookup"><span data-stu-id="73c57-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="73c57-110">アセンブリまたはリンク (組み込まれていない) リソース ファイル内のモジュールを解決します。</span><span class="sxs-lookup"><span data-stu-id="73c57-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73c57-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="73c57-111">Remarks</span></span>  
 <span data-ttu-id="73c57-112">`IHostAssemblyStore` ホストがアセンブリ id に基づいた効率的にアセンブリを読み込む方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="73c57-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="73c57-113">ホストでは、アセンブリを読み込んで返すことによって`IStream`バイトを直接ポイントするインスタンス。</span><span class="sxs-lookup"><span data-stu-id="73c57-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="73c57-114">CLR は、ホストが実装されているかどうかを決定します。`IHostAssemblyStore`呼び出して`IHostAssemblyManager::GetNonHostAssemblyStores`の初期化時にします。</span><span class="sxs-lookup"><span data-stu-id="73c57-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="73c57-115">これにより、ホスト、たとえば、.NET Framework アセンブリへのバインドをランタイムに依存するが、ユーザーのアセンブリへのバインディングを制御します。</span><span class="sxs-lookup"><span data-stu-id="73c57-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73c57-116">実装を提供するために`IHostAssemblyStore`、ホストによって参照されていないすべてのアセンブリを解決するのにはその目的を指定します、`ICLRAssemblyReferenceList`から返された`IHostAssemblyManager::GetNonHostStoreAssemblies`します。</span><span class="sxs-lookup"><span data-stu-id="73c57-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73c57-117">によって提供される、.NET Framework version 2.0 が、ホスト、アセンブリのネイティブ イメージを読み込むための手段を提供しない、[ネイティブ イメージ ジェネレーター (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)ユーティリティ。</span><span class="sxs-lookup"><span data-stu-id="73c57-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73c57-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="73c57-118">Requirements</span></span>  
 <span data-ttu-id="73c57-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73c57-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73c57-120">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="73c57-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73c57-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="73c57-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73c57-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73c57-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c57-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="73c57-123">See also</span></span>
- [<span data-ttu-id="73c57-124">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73c57-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="73c57-125">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73c57-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="73c57-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73c57-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
