---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8060e95f06fd53ca985f84666cc81cfe49394fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659658"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a>AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体
Authenticode のタイム スタンパー情報を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`cbSize`|この構造のサイズ。|  
|`dwError`|エラー コード。|  
|`algHash`|ハッシュアルゴリズム。|  
|`ftTimestamp`|タイム スタンプの時刻。|  
|`pChainContext`|タイム スタンパーのチェーン コンテキスト。  参照してください、 [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context)構造体。|  
  
## <a name="see-also"></a>関連項目
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
