---
title: "IMetaDataAssemblyEmit::DefineAssemblyRef メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssemblyRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 123bd37d189477eade72e3b0e74f923fecce57a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>IMetaDataAssemblyEmit::DefineAssemblyRef メソッド
このアセンブリが参照するアセンブリのメタデータを含む `AssemblyRef` 構造体を作成し、関連付けられたメタデータ トークンを返します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbPublicKeyOrToken`  
 [in]参照先アセンブリの発行者の公開キー。 ヘルパー関数[StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)このパラメーターとして渡すための公開キーのハッシュを取得するために使用できます。  
  
 `cbPublicKeyOrToken`  
 [in]バイト サイズ`pbPublicKeyOrToken`です。  
  
 `szName`  
 [in]アセンブリの人間が判読できるテキストの名前。 この値は 1024 文字を超えない必要があります。  
  
 `pMetaData`  
 [in]参照されたアセンブリのバージョン、プラットフォーム、およびロケール情報を含む ASSEMBLYMETADATA インスタンス。  
  
 `pbHashValue`  
 [in]参照されたアセンブリに関連付けられているデータをハッシュします。 任意。  
  
 `cbHashValue`  
 [in]バイト サイズ`pbHashValue`です。  
  
 `dwAssemblyRefFlags`  
 [in]ビットごとの組み合わせ[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)実行エンジンの動作を決定する値。  
  
 `pmdar`  
 [out]返されたへのポインター`AssemblyRef`メタデータ トークン。  
  
## <a name="remarks"></a>コメント  
 1 つ`AssemblyRef`このアセンブリが参照する各アセンブリのメタデータ構造体を定義する必要があります。  
  
 実行時に、参照先アセンブリの詳細については、"組み込み"として情報を表すことを示す値をアセンブリの競合回避モジュールに渡されます。 アセンブリ リゾルバーは、ポリシーを適用します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** Cor.h  
  
 **ライブラリ:** MsCorEE.dll にリソースとして使用  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [IMetaDataAssemblyEmit インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
