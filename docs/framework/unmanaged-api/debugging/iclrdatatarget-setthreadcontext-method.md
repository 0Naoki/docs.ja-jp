---
title: ICLRDataTarget::SetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3f98ab65512a380ebd4dc0ecd50e36f94a6d6b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104157"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="d0659-102">ICLRDataTarget::SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="d0659-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="d0659-103">ターゲット プロセスでは、指定したスレッドの現在のコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="d0659-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="d0659-104">このメソッドは、共通言語ランタイム (CLR) データ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d0659-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0659-105">構文</span><span class="sxs-lookup"><span data-stu-id="d0659-105">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0659-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0659-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d0659-107">[in]ターゲット プロセス内のスレッドのオペレーティング システムの識別子です。</span><span class="sxs-lookup"><span data-stu-id="d0659-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="d0659-108">[in]コンテキストのサイズ。</span><span class="sxs-lookup"><span data-stu-id="d0659-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="d0659-109">[in]コンテキストを格納するバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d0659-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="d0659-110">内のデータ、`context`バッファーは、Win32 の形式になります`CONTEXT`構造体。</span><span class="sxs-lookup"><span data-stu-id="d0659-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="d0659-111">コンテキストはプロセッサ固有の登録データを指定するので、Win32 の定義`CONTEXT`構造は、プロセッサのアーキテクチャによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d0659-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="d0659-112">Win32 の定義については、WinNT.h ヘッダー ファイルを参照してください`CONTEXT`構造体。</span><span class="sxs-lookup"><span data-stu-id="d0659-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0659-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0659-113">Remarks</span></span>  
 <span data-ttu-id="d0659-114">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="d0659-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0659-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0659-115">Requirements</span></span>  
 <span data-ttu-id="d0659-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0659-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0659-117">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d0659-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d0659-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0659-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d0659-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d0659-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d0659-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0659-120">See also</span></span>

- [<span data-ttu-id="d0659-121">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0659-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
