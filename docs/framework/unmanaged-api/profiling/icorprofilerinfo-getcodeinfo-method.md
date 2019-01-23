---
title: ICorProfilerInfo::GetCodeInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5004de587f715a2f3958c36999e432d7d6e9f2fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632661"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a>ICorProfilerInfo::GetCodeInfo メソッド
指定した関数 ID に関連付けられているネイティブ コードの範囲を取得します。  
  
 このメソッドは、互換性のために残されています。 使用して、 [icorprofilerinfo 2::getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)メソッド代わりにします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `functionId`  
 [in] ネイティブ コードが関連付けられている関数の ID。  
  
 `pStart`  
 [out] 関数のネイティブ コードを構成するバイトの配列へのポインター。  
  
 `pcSize`  
 [out] ネイティブ コードのバイト単位のサイズを指定する整数へのポインター。  
  
## <a name="remarks"></a>Remarks  
 パフォーマンスを最適化するために、.NET Framework Version 2.0 のランタイムは、関数のプリコンパイルされたネイティブ コードを複数の領域に分割します。 したがって、関数のネイティブ コードの範囲を処理できないため、.NET Framework 2.0 では `GetCodeInfo` メソッドは互換性のために残されているだけです。 プロファイラーは、より一般的な `ICorProfilerInfo2::GetCodeInfo2` メソッドを代わりに使用するように切り替える必要があります。  
  
 この関数は、呼び出し元が割り当てたバッファーを使用します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:** 1  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerInfo インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [プロファイリングのインターフェイス](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [プロファイル](../../../../docs/framework/unmanaged-api/profiling/index.md)
