---
title: CertVerifyAuthenticodeLicense 関数
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6e9a10dabc778b91fc738d28e9f841538d7c3f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701808"
---
# <a name="certverifyauthenticodelicense-function"></a>CertVerifyAuthenticodeLicense 関数
Authenticode XrML ライセンスの有効性を検証します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pLicenseBlob`  
 [in] 検証する Authenticode XrML ライセンス。  
  
 参照してください、 [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)構造体。  
  
 `dwFlags`  
 [in] オプション。 以下の値の組み合わせ。  
  
-   AXL_REVOCATION_NO_CHECK  
  
-   AXL_REVOCATION_CHECK_END_CERT_ONLY  
  
-   AXL_REVOCATION_CHECK_ENTIRE_CHAIN  
  
-   AXL_URL_CACHE_ONLY_RETRIEVAL  
  
-   AXL_LIFETIME_SIGNING  
  
-   AXL_TRUST_MICROSOFT_ROOT_ONLY  
  
 `pSignerInfo`  
 [out] 署名者の情報を受け取るため。 ライセンスに署名がない場合、`dwError` は TRUST_E_NOSIGNATURE に設定されます。 使用してリソースを解放する呼び出し元の責任、 [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)使用後に機能します。  
  
 参照してください[AXL_AUTHENTICODE_SIGNER_INFO 構造体](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)します。  
  
 `pTimestamperInfo`  
 [out] 可能な場合は、タイム スタンプの情報を受け取るため。 ライセンスにタイム スタンプがない場合、`dwError` は TRUST_E_NOSIGNATURE に設定されます。 使用してリソースを解放する呼び出し元の責任、 [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)使用後に機能します。  
  
 参照してください[AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)します。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `S_OK` を返します。 それ以外の場合はエラー コードを返します。  
  
## <a name="see-also"></a>関連項目
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
- [GetHashFromHandle メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [ICLRStrongName インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
