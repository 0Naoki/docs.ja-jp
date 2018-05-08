---
title: ICorProfilerCallback4::MovedReferences2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.MovedReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb5145db6f081661996766aab0683dc5d8a97e61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback4movedreferences2-method"></a>ICorProfilerCallback4::MovedReferences2 メソッド
圧縮ガベージ コレクションを実行した後の、ヒープ内のオブジェクトの新しいレイアウトを報告するために呼び出されます。 このメソッドは、プロファイラーが実装されている場合、 [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)インターフェイスです。 このコールバックが置き換えられます、 [icorprofilercallback::movedreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)メソッド、ULONG で表現できる内容を超える長さのオブジェクトの大きい範囲を報告できるためです。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cMovedObjectIDRanges`  
 [in] 圧縮ガベージ コレクションを実行した後に移動される、隣接したオブジェクトのブロック数。 つまり、`cMovedObjectIDRanges` の値は `oldObjectIDRangeStart`、`newObjectIDRangeStart`、および `cObjectIDRangeLength` 配列の合計サイズです。  
  
 `MovedReferences2` の次の 3 つの引数は並列配列です。 つまり、`oldObjectIDRangeStart[i]`、`newObjectIDRangeStart[i]`、`cObjectIDRangeLength[i]` はすべて、隣接するオブジェクトの同じブロックを対象としています。  
  
 `oldObjectIDRangeStart`  
 [in] それぞれがメモリ内の有効な隣接オブジェクト ブロックの古い (ガベージ コレクション実行前の) 開始アドレスを表す、`ObjectID` 値の配列。  
  
 `newObjectIDRangeStart`  
 [in] それぞれがメモリ内の有効な隣接オブジェクト ブロックの新しい (ガベージ コレクション実行後の) 開始アドレスを表す、`ObjectID` 値の配列。  
  
 `cObjectIDRangeLength`  
 [in] それぞれがメモリ内の隣接オブジェクト ブロックのサイズを表す、整数の配列。  
  
 サイズは、`oldObjectIDRangeStart` および `newObjectIDRangeStart` 配列内の参照される各ブロックに対して指定します。  
  
## <a name="remarks"></a>コメント  
 圧縮ガベージ コレクターは、無効なオブジェクトによって占有されているメモリを解放し、解放された領域を圧縮します。 その結果、ヒープ内で有効なオブジェクトが移動され、以前の通知で配布された `ObjectID` の値が変更されることがあります。  
  
 既存の `ObjectID` の値 (`oldObjectID`) が次の範囲内にあるとします。  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 この場合、範囲の開始からオブジェクトの開始までのオフセットは次のとおりです。  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 `i` の値が次の範囲内にあるとします。  
  
 0 <= `i` < `cMovedObjectIDRanges`  
  
 この場合、新しい `ObjectID` は次のように計算できます。  
  
 `newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)  
  
 ガーベッジ コレクションでオブジェクトが古い場所から新しい場所へ移動中の可能性があるため、コールバックの間は `MovedReferences2` によって渡される `ObjectID` 値はすべて無効です。 このため、`MovedReferences2` 呼び出しの間、プロファイラーはオブジェクトを検査するべきではありません。 A [icorprofilercallback 2::garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)コールバックすべてのオブジェクトが新しい場所に移動され、検査を実行できることを示します。  
  
 プロファイラーでは、両方を実装する場合、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)と[ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) 、インターフェイス、`MovedReferences2`メソッドは、前に呼び出されます、 [ICorProfilerCallback:。MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)場合に限り、メソッド、`MovedReferences2`メソッドが正常に返されます。 プロファイラーは HRESULT を返すことがあり、これは `MovedReferences2` メソッドの失敗を示し、2 番目のメソッドが呼び出されません。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:** を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー** : CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [ICorProfilerCallback インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [MovedReferences メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)  
 [ICorProfilerCallback4 インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [プロファイリングのインターフェイス](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [プロファイル](../../../../docs/framework/unmanaged-api/profiling/index.md)
