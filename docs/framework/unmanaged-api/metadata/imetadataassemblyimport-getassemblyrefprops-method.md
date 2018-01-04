---
title: "IMetaDataAssemblyImport::GetAssemblyRefProps メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76ae1d81db314530ab33a42cb99824da1745dff0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps メソッド
指定したメタデータ シグネチャを持つアセンブリ参照のプロパティのセットを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `mdar`  
 [in]`mdAssemblyRef`プロパティを取得する対象のアセンブリ参照を表すメタデータ トークン。  
  
 `ppbPublicKeyOrToken`  
 [out]公開キーまたはメタデータ トークンへのポインター。  
  
 `pcbPublicKeyOrToken`  
 [out]返される公開キー、またはトークンのバイト数。  
  
 `szName`  
 [out]アセンブリの簡易名。  
  
 `cchName`  
 [in]ワイド文字単位のサイズの`szName`します。  
  
 `pchName`  
 [out]実際に返されるワイド文字数へのポインター`szName`です。  
  
 `pMetaData`  
 [out]アセンブリのメタデータを含む ASSEMBLYMETADATA 構造体へのポインター。  
  
 `ppbHashValue`  
 [out]ハッシュ値へのポインター。 これは、sha-1 アルゴリズムを使用して、ハッシュ、 `PublicKey` 、arfFullOriginator のフラグを設定しない限り、参照されるアセンブリのプロパティ、 [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)列挙型を設定します。  
  
 `pcbHashValue`  
 [out]返されるハッシュ値のワイド文字の数。  
  
 `pdwAssemblyRefFlags`  
 [out]アセンブリに適用されるメタデータを記述するフラグをへのポインター。 フラグの値は 1 つまたは複数の組み合わせ[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)値。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは、それが成功した場合は S_OK を返します。それ以外の場合、Winerror.h ヘッダー ファイルで定義されているエラー コードのいずれかを返します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** Cor.h  
  
 **ライブラリ:** MsCorEE.dll にリソースとして使用  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [IMetaDataAssemblyImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
