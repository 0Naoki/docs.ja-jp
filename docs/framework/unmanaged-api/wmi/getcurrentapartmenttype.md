---
title: GetCurrentApartmentType 関数 (アンマネージ API リファレンス)
description: GetCurrentApartmentType 関数は、呼び出し元を実行しているアパートメントの種類を取得します。
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4de85eb310de70dc8fd61f7c06abca95ec267f87
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522526"
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType 関数
呼び出し元が実行されているアパートメントの種類が取得されます。   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a>パラメーター

`vFunc`  
[in]このパラメーターは使用されません。

`ptr`  
[in]ポインター、 [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)インスタンス。

`aptType`  
[out]ポインター、 [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype)呼び出し元のアパートメントを示す列挙値。

## <a name="return-value"></a>戻り値


|定数  |値  |説明  |
|---------|---------|---------|
| `S_OK` | 0 | 関数が正常に完了しました。 |
| `E_FAIL` | 0x80000008 | 呼び出し元は、アパートメントで実行していません。 |
  
## <a name="remarks"></a>Remarks

この関数の呼び出しをラップする、 [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)メソッド。

## <a name="requirements"></a>要件  
 **:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。  
  
 **ヘッダー:** WMINet_Utils.idl  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>関連項目  
[WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)](index.md)
