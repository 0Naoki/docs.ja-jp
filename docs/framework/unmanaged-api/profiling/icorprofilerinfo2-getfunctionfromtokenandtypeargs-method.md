---
title: "ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b225b87eab6e65055618c8b6659459637e8a01be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs メソッド
取得、 `FunctionID` 、クラスを含む、指定したメタデータ トークンを使用して関数のおよび`ClassID`いずれかの値が引数を入力します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `moduleID`  
 [in]関数が存在するモジュールの ID。  
  
 `funcDef`  
 [in]`mdMethodDef`関数を参照するメタデータ トークン。  
  
 `classId`  
 [in]関数の外側のクラスの ID です。  
  
 `cTypeArgs`  
 [in]指定された関数の型パラメーターの数。 この値は、非ジェネリック関数を 0 にする必要があります。  
  
 `typeArgs`  
 [in]配列`ClassID`関数の引数は、それぞれの値。 値`typeArgs`場合は NULL にすることができます`cTypeArgs`は 0 に設定します。  
  
 `pFunctionID`  
 [out]ポインター、`FunctionID`指定された関数。  
  
## <a name="remarks"></a>コメント  
 呼び出す、`GetFunctionFromTokenAndTypeArgs`メソッドを`mdMethodRef`メタデータの代わりに、`mdMethodDef`メタデータ トークンが予期しない結果を持つことができます。 呼び出し元を解決する必要があります、`mdMethodRef`を`mdMethodDef`渡すときです。  
  
 関数が既に読み込まれていない場合は、呼び出す`GetFunctionFromTokenAndTypeArgs`危険性のある操作でさまざまな状況で発生するへの読み込みが発生します。 たとえば、モジュールまたは型の読み込み中にこのメソッドを呼び出すと、ランタイムが循環的に読み込みしようと無限ループが発生する可能性があります。  
  
 一般の使用`GetFunctionFromTokenAndTypeArgs`をお勧めします。 プロファイラーは、特定の関数のイベントに関心がある場合、保存する必要があります、`ModuleID`と`mdMethodDef`その関数、および使用の[icorprofilerinfo 2::getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)を確認するかどうか、指定された`FunctionID`は必要な関数のです。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー** : CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [ICorProfilerInfo インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
