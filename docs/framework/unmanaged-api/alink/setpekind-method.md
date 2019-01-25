---
title: SetPEKind メソッド
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5fe770ffc5a9c187e9069e8a66553976f9a53b2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709885"
---
# <a name="setpekind-method"></a>SetPEKind メソッド
コンピューター固有またはマシンに依存しないのいずれかのノートブックの実行可能ファイル タイプを決定します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a>パラメーター  
 `AssemblyID`  
 アセンブリの ID。  
  
 `FileToken`  
 PE の種類を設定するファイルのトークン。 場合に NULL が`AssemblyID`バインドされていない netmodule では示されません。  
  
 `dwPEKind`  
 示されている PE の型、 [CorPEKind 列挙型](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)します。  
  
 `dwMachine`  
 ターゲット コンピューターのアーキテクチャ、NT ヘッダーに記載されています。  
  
## <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、S_OK を返します。  
  
## <a name="requirements"></a>必要条件  
 Alink.h が必要です。  
  
## <a name="see-also"></a>関連項目
- [GetPEKind メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)
- [IALink2 インターフェイス](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [IALink インターフェイス](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
