---
title: EClrFailure 列挙型
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef4e12015adc3d6e67ad9c8ba8b152cd775b85e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="eclrfailure-enumeration"></a>EClrFailure 列挙型
ホストがポリシーのアクションを設定できるエラーのセットについて説明します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|コードの重要ではない領域で、(スレッド、メモリのブロックまたはロック) などのリソースの割り当ての試行中にエラーが発生しました。|  
|`FAIL_CriticalResource`|コードの重要な領域で、(スレッド、メモリのブロックまたはロック) などのリソースの割り当ての試行中にエラーが発生しました。|  
|`FAIL_FatalRuntime`|共通言語ランタイム (CLR) は、プロセスでマネージ コードを実行することはありません。 今後は、ホスティングの関数に呼び出すには、HOST_E_CLRNOTAVAILABLE の HRESULT 値が返されます。|  
|`FAIL_OrphanedLock`|スレッドがから戻ったときにロックの解除に失敗しました、<xref:System.AppDomain>オブジェクト。 ホストは、スレッドを終了させるには、このエラーを設定できません。|  
|`FAIL_StackOverflow`|スタック オーバーフローが発生しました。|  
|`FAIL_AccessViolation`|読み取りまたは書き込み保護されているメモリを試みました。 サポートされていません、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]です。|  
|`FAIL_CodeContract`|コード コントラクト エラーが発生しました。 参照してください[コード コントラクト](../../../../docs/framework/debug-trace-profile/code-contracts.md)です。|  
  
## <a name="remarks"></a>コメント  
 参照してください、 [iclrpolicymanager::setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)メソッドの一覧については[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値が、ホストを使用して、エラー状態のポリシーのアクションを指定します。 コードの詳細については、重要および重大でない地域は、次を参照してください。 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)です。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:** を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll  
  
 **.NET framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [ICLRPolicyManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetActionOnFailure メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [IHostPolicyManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [ホスティングの列挙型](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
