---
title: _AxlRSAKeyValueToPublicKeyToken 関数
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a340af9ba196dbcd8618afdd83bcf7e56124bf7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529909"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a>\_AxlRSAKeyValueToPublicKeyToken 関数

Modulus および Exponent を、厳密な名前の公開キー トークンに変換します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pModulusBlob`  
 [in]Base64 でエンコードされた Modulus blob (から、 \<Modulus > 要素)。  参照してください、 [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)構造体。  
  
 `pExponentBlob`  
 [in]Base64 でエンコードされた Exponent blob (から、\<指数 > 要素)。 参照してください、 [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)構造体。  
  
 `ppwszPublicKeyToken`  
 [out] 16 進エンコードされた公開キー トークンを受け取るための WCHAR * へのポインター。  
  
## <a name="return-value"></a>戻り値  
 関数が成功した場合は `S_OK`。 それ以外の場合はエラー コードを返します。  
  
## <a name="see-also"></a>関連項目
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
