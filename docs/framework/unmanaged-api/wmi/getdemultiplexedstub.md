---
title: GetDemultiplexedStub 関数 (アンマネージ API リファレンス)
description: GetDemultiplexedStub 関数は、クライアントを Windows の管理から非同期呼び出しの受信を支援するために、オブジェクト転送シンクを作成します。
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4311a77c9159428bf7beacc99d4479acb28b91b6
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44135810"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="fddbb-103">GetDemultiplexedStub 関数</span><span class="sxs-lookup"><span data-stu-id="fddbb-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="fddbb-104">Windows 管理から非同期呼び出しを受信する際にクライアントを支援するオブジェクト転送シンクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fddbb-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fddbb-105">構文</span><span class="sxs-lookup"><span data-stu-id="fddbb-105">Syntax</span></span>  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="fddbb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fddbb-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="fddbb-107">[in]クライアントのインプロセス実装へのポインター [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)します。</span><span class="sxs-lookup"><span data-stu-id="fddbb-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="fddbb-108">[in]イベントがローカルかどうかを示すフラグ (`true`)、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="fddbb-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="fddbb-109">[out]Windows の管理から非同期呼び出しの受信をクライアントを支援するためにオブジェクトのフォワーダー シンク。</span><span class="sxs-lookup"><span data-stu-id="fddbb-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="fddbb-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="fddbb-110">Return value</span></span>

<span data-ttu-id="fddbb-111">関数が成功した場合、戻り値は`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="fddbb-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="fddbb-112">関数が失敗した場合、戻り値が 0 以外のエラー コードにします。</span><span class="sxs-lookup"><span data-stu-id="fddbb-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="fddbb-113">拡張エラー情報を取得する、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="fddbb-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="fddbb-114">要件</span><span class="sxs-lookup"><span data-stu-id="fddbb-114">Requirements</span></span>  
 <span data-ttu-id="fddbb-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fddbb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fddbb-116">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fddbb-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fddbb-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fddbb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fddbb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="fddbb-118">See also</span></span>  
[<span data-ttu-id="fddbb-119">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="fddbb-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
