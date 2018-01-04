---
title: "ICorProfilerInfo4::InitializeCurrentThread メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4::InitializeCurrentThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f3c261068b38861dca2633a490e46d9f44371d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread メソッド
後続のプロファイラー API は、デッドロックを回避するため、同じスレッドで呼び出しの前に、現在のスレッドを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>コメント  
 呼び出すことをお勧め`InitializeCurrentThread`API が存在するときは、プロファイラーを呼び出す任意のスレッドでスレッドを中断します。 このメソッドは、通常サンプリング プロファイラーを呼び出す独自のスレッドを作成して使用、 [icorprofilerinfo 2::dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)スタック行き場メソッドで対象のスレッドを中断している間はについて説明します。 呼び出して`InitializeCurrentThread`プロファイラーが CLR をそれ以外の場合、最初の呼び出し中に実行するスレッドあたりの遅延初期化を確認ときに、プロファイラーでは、まずサンプリング スレッドを作成した後`DoStackSnapshot`他のスレッドがない場合に安全に発生することができますようになりました中断されています。  
  
> [!NOTE]
>  `InitializeCurrentThread`ロックを実行し、デッドロックが発生するタスクを完了するには、事前に初期化します。 呼び出す`InitializeCurrentThread`中断されたスレッドが存在しない場合にのみです。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー** : CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [ICorProfilerInfo4 インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [プロファイリングのインターフェイス](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [プロファイル](../../../../docs/framework/unmanaged-api/profiling/index.md)
