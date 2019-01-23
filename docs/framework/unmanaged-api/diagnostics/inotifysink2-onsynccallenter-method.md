---
title: INotifySink2::OnSyncCallEnter メソッド
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c44a150fa85ff0cbda4ff2b39acefb46045adad1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500290"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="2bcb6-102">INotifySink2::OnSyncCallEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="2bcb6-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="2bcb6-103">呼び出しを入力するときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2bcb6-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bcb6-104">構文</span><span class="sxs-lookup"><span data-stu-id="2bcb6-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2bcb6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bcb6-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="2bcb6-106">[in]入力されている呼び出しの ID。</span><span class="sxs-lookup"><span data-stu-id="2bcb6-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="2bcb6-107">参照してください[CALL_ID 構造体](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)します。</span><span class="sxs-lookup"><span data-stu-id="2bcb6-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="2bcb6-108">[in]バッファーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2bcb6-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="2bcb6-109">[in]呼び出しバッファーのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="2bcb6-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bcb6-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="2bcb6-110">Return Value</span></span>  
 <span data-ttu-id="2bcb6-111">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="2bcb6-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bcb6-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bcb6-112">Requirements</span></span>  
 <span data-ttu-id="2bcb6-113">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="2bcb6-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bcb6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bcb6-114">See also</span></span>
- [<span data-ttu-id="2bcb6-115">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bcb6-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="2bcb6-116">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bcb6-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="2bcb6-117">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bcb6-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
