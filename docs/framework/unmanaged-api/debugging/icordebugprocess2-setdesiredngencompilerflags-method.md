---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc0dde4f2455ed45ddf8ca1efefa7ab67ba04f6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660776"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="11998-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="11998-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="11998-103">ランタイムにそのイメージを現在のプロセスに読み込むためにプリコンパイル済みのイメージに埋め込む必要があるフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="11998-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11998-104">構文</span><span class="sxs-lookup"><span data-stu-id="11998-104">Syntax</span></span>  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11998-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="11998-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="11998-106">[in]値、 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)コンパイラ フラグを指定する列挙体に適切なコンパイル済みのイメージを選択するために使用します。</span><span class="sxs-lookup"><span data-stu-id="11998-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11998-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="11998-107">Remarks</span></span>  
 <span data-ttu-id="11998-108">`SetDesiredNGENCompilerFlags`メソッドは、ランタイムはこのプロセスにそのイメージを読み込むようにプリコンパイル済みのイメージに埋め込む必要があるフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="11998-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="11998-109">このメソッドによって設定されたフラグは、適切なプリコンパイル済みのイメージの選択にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="11998-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="11998-110">このようなイメージが存在しない場合、ランタイムは読み込む Microsoft intermediate language (MSIL) のイメージと、ジャストイン タイム (JIT) コンパイラ代わりにします。</span><span class="sxs-lookup"><span data-stu-id="11998-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="11998-111">その場合は、デバッガーを使用する必要がありますが、 [icordebugmodule 2::setjitcompilerflags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)メソッドを JIT コンパイルの必要に応じて、フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="11998-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="11998-112">イメージが読み込まれると、JIT コンパイルはいくつか行う必要があります (これは、イメージには、ジェネリックが含まれている場合、ケースになります) そのイメージの場合で指定されたコンパイラ フラグ、`SetDesiredNGENCompilerFlags`メソッドは、追加の JIT コンパイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="11998-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="11998-113">`SetDesiredNGENCompilerFlags`メソッドを呼び出す必要があります、 [icordebugmanagedcallback::createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="11998-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="11998-114">呼び出そうとすると、`SetDesiredNGENCompilerFlags`メソッドが後では失敗します。</span><span class="sxs-lookup"><span data-stu-id="11998-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="11998-115">もないか、フラグを設定しようとが定義されている、`CorDebugJITCompilerFlags`列挙型または指定されたプロセスの有効ではないが失敗します。</span><span class="sxs-lookup"><span data-stu-id="11998-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11998-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="11998-116">Requirements</span></span>  
 <span data-ttu-id="11998-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="11998-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11998-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11998-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11998-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11998-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11998-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11998-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11998-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="11998-121">See also</span></span>
- [<span data-ttu-id="11998-122">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11998-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="11998-123">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11998-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
