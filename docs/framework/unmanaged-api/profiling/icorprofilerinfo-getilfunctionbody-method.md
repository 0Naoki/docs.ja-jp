---
title: "ICorProfilerInfo::GetILFunctionBody メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6908b6c765a56ef0aa43a66cc58ec74b525bc2d3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody メソッド
開始位置のヘッダーとして、Microsoft intermediate language (MSIL) コードでメソッドの本体へのポインターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `moduleId`  
 [in]関数が存在するモジュールの ID。  
  
 `methodId`  
 [in]メソッドのメタデータ トークン。  
  
 `ppMethodHeader`  
 [out]メソッドのヘッダーへのポインター。  
  
 `pcbMethodSize`  
 [out]メソッドのサイズを指定する整数。  
  
## <a name="remarks"></a>コメント  
 メソッドは、中で、モジュールによって制限されます。 `GetILFunctionBody`メソッドが共通言語ランタイム (CLR) によって読み込まれた前に、MSIL コードにツールへのアクセスを提供するように設計で、目的のインスタンスを検索するメソッドのメタデータ トークンを使用しています。  
  
 `GetILFunctionBody`CORPROF_E_FUNCTION_NOT_IL HRESULT を返す場合、`methodId`任意の MSIL コード (など、抽象メソッドまたはプラットフォームは、(PInvoke) メソッドを呼び出す) ことがなく、メソッドを指します。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー** : CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [ICorProfilerInfo インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
