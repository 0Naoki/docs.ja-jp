---
title: "FunctionLeave3WithInfo 関数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave3WithInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave3WithInfo
helpviewer_keywords: FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f787b5bd78a575d862c198daeee99a0704734276
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="functionleave3withinfo-function"></a>FunctionLeave3WithInfo 関数
コントロールが、関数から返されていることをプロファイラーに通知しに渡すことができるハンドルを提供、 [icorprofilerinfo 3::getfunctionleave3info メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)スタック フレームおよび戻り値を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `functionIDOrClientID`  
 [in]制御が返される関数の識別子。  
  
 `eltInfo`  
 [in] 特定のスタック フレームに関する情報を表す不透明ハンドル。 このハンドルは、渡されるコールバック中にのみ有効です。  
  
## <a name="remarks"></a>コメント  
 `FunctionLeave3WithInfo`関数が呼び出され、により、プロファイラーを使用すると、プロファイラーに通知のコールバック メソッド、 [icorprofilerinfo 3::getfunctionleave3info メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)を戻り値を検査します。 戻り値の情報にアクセスする、`COR_PRF_ENABLE_FUNCTION_RETVAL`を設定するフラグを持っています。 プロファイラーは、使用、 [icorprofilerinfo::seteventmask メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)イベント フラグを設定し、使用して、 [icorprofilerinfo 3::setenterleavefunctionhooks3withinfo メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)を登録する、この関数の実装です。  
  
 `FunctionLeave3WithInfo`関数コールバックです。 これを実装する必要があります。 実装を使用する必要があります、`__declspec(naked)`ストレージ クラス属性。  
  
 実行エンジンは、この関数を呼び出す前に、レジスタを保存できません。  
  
-   エントリを上には、浮動小数点ユニット (FPU) にあるなど、使用するすべてのレジスタを保存する必要があります。  
  
-   終了時に、その呼び出し元がプッシュされたすべてのパラメーターをポップすることで、スタックを復元する必要があります。  
  
 実装`FunctionLeave3WithInfo`をブロックしないでください、ガベージ コレクションが延期されます。 実装しないでください、ガベージ コレクション スタックはガベージ コレクションに適した状態ではない可能性があります。 ガベージ コレクションが実行されると、ランタイムがまでブロックされます`FunctionLeave3WithInfo`を返します。  
  
 `FunctionLeave3WithInfo`関数がマネージ コードを呼び出していない、または任意の方法で管理されているメモリの割り当てが発生する必要があります。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorProf.idl  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)  
 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [グローバル静的関数のプロファイル](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
