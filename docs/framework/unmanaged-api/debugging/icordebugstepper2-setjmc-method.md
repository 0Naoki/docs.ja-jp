---
title: ICorDebugStepper2::SetJMC メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 129bf04a097b2019b080f813bf049d41b501f8fd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474216"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="a1d49-102">ICorDebugStepper2::SetJMC メソッド</span><span class="sxs-lookup"><span data-stu-id="a1d49-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="a1d49-103">この ICorDebugStepper のステップは、アプリケーションの開発者が作成したコードからのみかどうかを指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a1d49-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="a1d49-104">このプロセスは、マイ コード (のみ JMC) のデバッグとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a1d49-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d49-105">構文</span><span class="sxs-lookup"><span data-stu-id="a1d49-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1d49-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1d49-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="a1d49-107">[in]設定`true`だけは、アプリケーションの開発者が作成した。 それ以外の場合、に設定するコードをステップ実行する`false`します。</span><span class="sxs-lookup"><span data-stu-id="a1d49-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1d49-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1d49-108">Requirements</span></span>  
 <span data-ttu-id="a1d49-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1d49-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1d49-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1d49-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1d49-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1d49-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1d49-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1d49-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
