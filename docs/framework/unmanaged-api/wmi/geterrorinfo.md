---
title: GetErrorInfo 関数 (アンマネージ API リファレンス)
description: GetErrorInfo 関数は、前の関数呼び出しからエラー情報を取得します。
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f25777402fa31e72cbbf36f58a6c4cc65542979
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44277274"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="27dfe-103">GetErrorInfo 関数</span><span class="sxs-lookup"><span data-stu-id="27dfe-103">GetErrorInfo function</span></span>
<span data-ttu-id="27dfe-104">前の関数呼び出しからエラー情報が取得されます。</span><span class="sxs-lookup"><span data-stu-id="27dfe-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="27dfe-105">構文</span><span class="sxs-lookup"><span data-stu-id="27dfe-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="27dfe-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="27dfe-106">Return value</span></span>

<span data-ttu-id="27dfe-107">ポインターを[IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)関数呼び出しが成功すると、オブジェクトまたは`null`失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="27dfe-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="27dfe-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="27dfe-108">Remarks</span></span>

<span data-ttu-id="27dfe-109">この関数の呼び出しをラップする、 [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)メソッド。</span><span class="sxs-lookup"><span data-stu-id="27dfe-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="27dfe-110">要件</span><span class="sxs-lookup"><span data-stu-id="27dfe-110">Requirements</span></span>  
 <span data-ttu-id="27dfe-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27dfe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27dfe-112">**ヘッダー:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="27dfe-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="27dfe-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="27dfe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27dfe-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="27dfe-114">See also</span></span>  
[<span data-ttu-id="27dfe-115">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="27dfe-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
