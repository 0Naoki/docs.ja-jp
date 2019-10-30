---
title: ICorPublishProcess インターフェイス
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 04f6a088c5bbe96e3909ba600aa8ffab937abe2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140404"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="8b2fb-102">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b2fb-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="8b2fb-103">プロセスについて表示される情報にアクセスするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b2fb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b2fb-104">Methods</span></span>  
  
|<span data-ttu-id="8b2fb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b2fb-105">Method</span></span>|<span data-ttu-id="8b2fb-106">説明</span><span class="sxs-lookup"><span data-stu-id="8b2fb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b2fb-107">EnumAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="8b2fb-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="8b2fb-108">この `ICorPublishProcess`によって参照されるプロセス内のアプリケーションドメインを含む[ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="8b2fb-109">GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="8b2fb-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="8b2fb-110">この `ICorPublishProcess`によって参照されるプロセスの実行可能ファイルの完全パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="8b2fb-111">GetProcessID メソッド</span><span class="sxs-lookup"><span data-stu-id="8b2fb-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="8b2fb-112">この `ICorPublishProcess`によって参照されるプロセスのオペレーティングシステム識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="8b2fb-113">IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="8b2fb-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="8b2fb-114">この `ICorPublishProcess` によって参照されるプロセスがマネージコードを実行していることがわかっているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b2fb-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="8b2fb-115">Requirements</span></span>  
 <span data-ttu-id="8b2fb-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b2fb-117">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="8b2fb-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8b2fb-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b2fb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b2fb-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b2fb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2fb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b2fb-120">See also</span></span>

- [<span data-ttu-id="8b2fb-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b2fb-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="8b2fb-122">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="8b2fb-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
