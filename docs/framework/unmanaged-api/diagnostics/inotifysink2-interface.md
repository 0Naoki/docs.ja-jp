---
title: INotifySink2 インターフェイス
ms.date: 03/30/2017
api_name:
- INotifySink2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2
helpviewer_keywords:
- INotifySink2 interface [.NET Framework debugging]
ms.assetid: c1018789-4206-455d-aacc-2d876fc0d0bb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc5d09ac12919b8c68b9fe4bf9f7dc0009b2d4b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705470"
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="d5fb2-102">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5fb2-102">INotifySink2 Interface</span></span>
<span data-ttu-id="d5fb2-103">シンク通知メソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-103">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5fb2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d5fb2-104">Methods</span></span>  
  
|<span data-ttu-id="d5fb2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d5fb2-105">Method</span></span>|<span data-ttu-id="d5fb2-106">説明</span><span class="sxs-lookup"><span data-stu-id="d5fb2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5fb2-107">OnSyncCallEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="d5fb2-107">OnSyncCallEnter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="d5fb2-108">呼び出しを入力するときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-108">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="d5fb2-109">OnSyncCallExit メソッド</span><span class="sxs-lookup"><span data-stu-id="d5fb2-109">OnSyncCallExit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="d5fb2-110">呼び出しが終了するときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-110">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="d5fb2-111">OnSyncCallOut メソッド</span><span class="sxs-lookup"><span data-stu-id="d5fb2-111">OnSyncCallOut Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)|<span data-ttu-id="d5fb2-112">呼び出しがないときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-112">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="d5fb2-113">OnSyncCallReturn メソッド</span><span class="sxs-lookup"><span data-stu-id="d5fb2-113">OnSyncCallReturn Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="d5fb2-114">呼び出しが戻るときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d5fb2-114">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5fb2-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5fb2-115">Requirements</span></span>  
 <span data-ttu-id="d5fb2-116">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="d5fb2-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5fb2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5fb2-117">See also</span></span>
- [<span data-ttu-id="d5fb2-118">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5fb2-118">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="d5fb2-119">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5fb2-119">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="d5fb2-120">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5fb2-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
