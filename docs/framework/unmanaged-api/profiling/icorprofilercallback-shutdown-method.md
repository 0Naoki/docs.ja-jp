---
title: ICorProfilerCallback::Shutdown メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1696cb49170ba245a657e5efb6c8ba4b694af32f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192642"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="883a4-102">ICorProfilerCallback::Shutdown メソッド</span><span class="sxs-lookup"><span data-stu-id="883a4-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="883a4-103">アプリケーションのシャット ダウンをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="883a4-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="883a4-104">構文</span><span class="sxs-lookup"><span data-stu-id="883a4-104">Syntax</span></span>  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="883a4-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="883a4-105">Remarks</span></span>  
 <span data-ttu-id="883a4-106">プロファイラー コードがのメソッドを安全に呼び出すことはできません、 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)インターフェイスの後に、`Shutdown`メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="883a4-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="883a4-107">呼び出し`ICorProfilerInfo`メソッドの後に未定義の動作が発生する、`Shutdown`メソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="883a4-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="883a4-108">シャット ダウン後に特定の変更できないイベントが発生します。プロファイラーは、これが発生したときにすぐに返される注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="883a4-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="883a4-109">`Shutdown`プロファイリングされているマネージ アプリケーションがマネージ コードとして起動する場合にのみ、メソッドが呼び出されます (つまり、プロセスのスタックの最初のフレームが管理対象)。</span><span class="sxs-lookup"><span data-stu-id="883a4-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="883a4-110">アプリケーションがアンマネージ コードとして開始された後でマネージ コードにジャンプする場合は、それによってインスタンスを作成する共通言語ランタイム (CLR) の`Shutdown`は呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="883a4-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="883a4-111">ような場合、プロファイラーは、ライブラリに含める必要があります、 `DllMain` DLL_PROCESS_DETACH を使用するルーチンの値をすべてのリソースを解放し、これにディスクにトレースのフラッシュなどのデータのクリーンアップ処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="883a4-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="883a4-112">一般に、プロファイラーは、予期しないシャット ダウンに対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="883a4-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="883a4-113">たとえば、win32 のプロセスを中止する可能性があります`TerminateProcess`メソッド (Winbase.h で宣言)。</span><span class="sxs-lookup"><span data-stu-id="883a4-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="883a4-114">それ以外の場合、CLR は、それらの計画的な破棄のメッセージを配信することがなく、特定のマネージ スレッド (バック グラウンド スレッド) を停止します。</span><span class="sxs-lookup"><span data-stu-id="883a4-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="883a4-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="883a4-115">Requirements</span></span>  
 <span data-ttu-id="883a4-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="883a4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="883a4-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="883a4-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="883a4-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="883a4-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="883a4-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="883a4-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="883a4-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="883a4-120">See also</span></span>

- [<span data-ttu-id="883a4-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="883a4-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="883a4-122">Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="883a4-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
