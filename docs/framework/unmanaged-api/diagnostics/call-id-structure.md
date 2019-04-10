---
title: CALL_ID 構造体
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6fa729b131d12b2825a2def700fd918ce8acc40
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220176"
---
# <a name="callid-structure"></a><span data-ttu-id="45e7e-102">CALL_ID 構造体</span><span class="sxs-lookup"><span data-stu-id="45e7e-102">CALL_ID Structure</span></span>
<span data-ttu-id="45e7e-103">デバッガーが呼び出される関数に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="45e7e-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="45e7e-104">参照してください、 [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)インターフェイスの詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="45e7e-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e7e-105">構文</span><span class="sxs-lookup"><span data-stu-id="45e7e-105">Syntax</span></span>  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="45e7e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="45e7e-106">Members</span></span>  
  
|<span data-ttu-id="45e7e-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="45e7e-107">Member</span></span>|<span data-ttu-id="45e7e-108">説明</span><span class="sxs-lookup"><span data-stu-id="45e7e-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="45e7e-109">呼び出しを行っているコンピューターを識別します。</span><span class="sxs-lookup"><span data-stu-id="45e7e-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="45e7e-110">コンピューターのプロセッサを識別します。</span><span class="sxs-lookup"><span data-stu-id="45e7e-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="45e7e-111">呼び出しを実行しているスレッドを識別します。</span><span class="sxs-lookup"><span data-stu-id="45e7e-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="45e7e-112">呼び出し履歴のアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="45e7e-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="45e7e-113">呼び出しのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="45e7e-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="45e7e-114">呼び出しを実行するマシンを識別します。</span><span class="sxs-lookup"><span data-stu-id="45e7e-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45e7e-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="45e7e-115">Requirements</span></span>  
 <span data-ttu-id="45e7e-116">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="45e7e-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e7e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="45e7e-117">See also</span></span>

- [<span data-ttu-id="45e7e-118">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45e7e-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="45e7e-119">シンボル ストア診断構造体</span><span class="sxs-lookup"><span data-stu-id="45e7e-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
