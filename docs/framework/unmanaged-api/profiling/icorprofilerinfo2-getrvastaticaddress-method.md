---
title: "ICorProfilerInfo2::GetRVAStaticAddress メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4320ed3cdd3d17932d03e98d4d35d27adad2532a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a>ICorProfilerInfo2::GetRVAStaticAddress メソッド
指定された相対仮想アドレス (RVA) の静的フィールドのアドレスを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `classId`  
 [in]要求された RVA 静的フィールドを格納するクラスの ID。  
  
 `fieldToken`  
 [in]要求された RVA 静的フィールドのメタデータ トークン。  
  
 `ppAddress`  
 [out]RVA 静的フィールドのアドレスへのポインター。  
  
## <a name="remarks"></a>コメント  
 `GetRVAStaticAddress`メソッドは、次のいずれかを返す可能性があります。  
  
-   指定された静的フィールドに指定されたコンテキスト内のアドレスが割り当てられていない場合の CORPROF_E_DATAINCOMPLETE HRESULT です。  
  
-   ガベージ コレクション ヒープ内で使用できるオブジェクトのアドレス。 これらのアドレスはガベージ コレクションの後にプロファイラーを想定しないでくださいが有効であるために、ガベージ コレクションの後に無効になる可能性があります。  
  
 クラスのクラスのコンス トラクターが完了するまで`GetRVAStaticAddress`は静的フィールドの一部は既に初期化し、ガベージ コレクション オブジェクトをルートする可能性がありますが、すべての静的フィールドの CORPROF_E_DATAINCOMPLETE を返します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー** : CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [ICorProfilerInfo インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
