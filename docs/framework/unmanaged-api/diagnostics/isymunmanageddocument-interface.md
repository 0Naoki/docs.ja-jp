---
title: "ISymUnmanagedDocument インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument
helpviewer_keywords: ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8654f28cc4d82a5ed1419215807ec3360522fd55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument インターフェイス
シンボル ストアによって参照されるドキュメントを表します。 ドキュメントは、uniform resource locator (URL) と GUID のドキュメント型によって定義されます。 URL を使用して格納方法に関係なく、ドキュメントを検索し、ドキュメントの種類の GUID できます。 ドキュメントのソースをシンボル ストアに格納でき、このインターフェイスを通じて取得できます。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[FindClosestLine メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|行を指定した場合も、シーケンス ポイントができない可能性があります、このドキュメントでは、シーケンス ポイントである最も近い行を返します。|  
|[GetCheckSum メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|チェックサムを取得します。|  
|[GetCheckSumAlgorithmId メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|チェックサム アルゴリズム識別子を取得またはチェックサムがない場合に、すべてがゼロの GUID を取得します。|  
|[GetDocumentType メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|このドキュメントのドキュメントの種類を取得します。|  
|[GetLanguage メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|このドキュメントの言語識別子を取得します。|  
|[GetLanguageVendor メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|このドキュメントの言語の販売元を取得します。|  
|[GetSourceLength メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|埋め込まれたソースの長さをバイト数で取得します。|  
|[GetSourceRange メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|指定されたバッファーに埋め込まれたソースの指定した範囲を返します。|  
|[GetURL メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|このドキュメントの URL を返します。|  
|[HasEmbeddedSource メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|返します`true`場合は、ドキュメントには、デバッグ シンボルに埋め込まれたソースを返しますそれ以外の場合、`false`です。|  
  
## <a name="see-also"></a>関連項目  
 [シンボル ストア診断インターフェイスします。](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
