---
title: "IMetaDataAssemblyImport インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport
helpviewer_keywords: IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ef5b913dc9b1391c63cb123e1f922ca61da6a5bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport インターフェイス
アセンブリ マニフェストの内容にアクセスして確認するメソッドを提供します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[CloseEnum メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|指定した列挙子を識別するハンドルを解放します。|  
|[EnumAssemblyRefs メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|インターフェイス ポインターを含む列挙子を取得、`mdAssemblyRef`の現在のメタデータ スコープ内のアセンブリによって参照されるアセンブリのトークン。|  
|[EnumExportedTypes メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|インターフェイス ポインターを含む列挙子を取得、`mdExportedType`の現在のメタデータ スコープ内のアセンブリによって参照されている COM 型のトークン。|  
|[EnumFiles メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|インターフェイス ポインターを含む列挙子を取得、`mdFile`の現在のメタデータ スコープ内のアセンブリによって参照されるファイルのトークン。|  
|[EnumManifestResources メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|インターフェイス ポインターを含む列挙子を取得、`mdManifestResource`の現在のメタデータ スコープ内のアセンブリによって参照されているリソースのトークン。|  
|[FindAssembliesByName メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|配列を取得`mdAssemblyRef`指定した名前のアセンブリのトークン。|  
|[FindExportedTypeByName メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|取得、`mdExportedType`指定した名前を持つ COM 型のトークン。|  
|[FindManifestResourceByName メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|取得、`mdManifestResource`指定の名前を持つリソースのトークン。|  
|[GetAssemblyFromScope メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|現在のメタデータ スコープ内のアセンブリのトークンを取得します。|  
|[GetAssemblyProps メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|指定したアセンブリのプロパティの設定を取得します。|  
|[GetAssemblyRefProps メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|指定したプロパティの設定を取得`mdAssemblyRef`トークンです。|  
|[GetExportedTypeProps メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|指定した COM 型のプロパティの設定を取得します。|  
|[GetFileProps メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|指定されたファイルのプロパティの設定を取得します。|  
|[GetManifestResourceProps メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|指定されたマニフェスト リソースのプロパティの設定を取得します。|  
  
## <a name="requirements"></a>要件  
 **Platform:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** Cor.h  
  
 **ライブラリ:** MsCorEE.dll にリソースとして使用  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [メタデータ インターフェイス](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataAssemblyEmit インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
