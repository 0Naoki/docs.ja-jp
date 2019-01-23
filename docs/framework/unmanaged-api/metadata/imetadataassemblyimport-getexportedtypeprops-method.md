---
title: IMetaDataAssemblyImport::GetExportedTypeProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e222f1a39276b6debc348bfb25e8db65cb648ba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544641"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>IMetaDataAssemblyImport::GetExportedTypeProps メソッド
指定したメタデータ シグネチャを持つエクスポートされた型のプロパティのセットを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `mdct`  
 [in]`mdExportedType`エクスポートされた型を表すメタデータ トークン。  
  
 `szName`  
 [out]エクスポートされる型の名前。  
  
 `cchName`  
 [in]ワイド文字単位のサイズの`szName`します。  
  
 `pchName`  
 [out]実際に返されるワイド文字の数 `szName`  
  
 `ptkImplementation`  
 [out]`mdFile`、 `mdAssemblyRef`、または`mdExportedType`またはエクスポートされる型のプロパティにアクセスできるようにするメタデータ トークン。  
  
 `ptkTypeDef`  
 [out]ポインター、`mdTypeDef`ファイル内の型を表すトークン。  
  
 `pdwExportedTypeFlags`  
 [out]エクスポートされた型に適用されるメタデータを記述するフラグへのポインター。 1 つまたは複数フラグ値を指定できます[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)値。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** Cor.h  
  
 **ライブラリ:** MsCorEE.dll にリソースとして使用  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [IMetaDataAssemblyImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
