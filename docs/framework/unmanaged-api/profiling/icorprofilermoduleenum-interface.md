---
title: "ICorProfilerModuleEnum インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum
api_location: mscorwks.cll
api_type: COM
f1_keywords: ICorProfilerModuleEnum
helpviewer_keywords: ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 43cc6afc42fc1a02fd7d7b3df2973cc9b3e31251
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenum-interface"></a>ICorProfilerModuleEnum インターフェイス
アプリケーションまたはプロファイラーによってロードされたモジュールのコレクションを順番に反復処理するためのメソッドを提供します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[Clone メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|この `ICorProfilerModuleEnum` インターフェイスのコピーに対するインターフェイス ポインターを取得します。|  
|[GetCount メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|アプリケーションによって読み込まれたマネージ モジュールの数を取得します。|  
|[Next メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|オブジェクトのシーケンシャル コレクションから、列挙子の現在の位置以降にある指定した数の隣接するモジュールを取得します。|  
|[Reset メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|列挙子のカーソルをシーケンスの開始位置に移動します。|  
|[Skip メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|指定した数の要素がスキップされるように、この列挙子のカーソルの位置を進めます。|  
  
## <a name="remarks"></a>コメント  
 `ICorProfilerModuleEnum` インターフェイスは列挙子です。 このインターフェイスにより、配列の受信側は、受信側に適した速度で送信側から要素をプルできます。 つまり、受信側は配列要素のフローを明示的に制御できるため、大きな配列をメソッド パラメーターとして渡す場合に関連する問題を回避できます。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー** : CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [ICorProfilerInfo インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [プロファイリングのインターフェイス](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [EnumModules メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
