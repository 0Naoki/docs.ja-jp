---
title: ICeeGen::AllocateMethodBuffer メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd51f9c05c49fefc790ce69dcdc3117680c8e6b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500031"
---
# <a name="iceegenallocatemethodbuffer-method"></a>ICeeGen::AllocateMethodBuffer メソッド
メソッドで指定されたサイズのバッファーを作成し、メソッドの相対仮想アドレスを取得します。  
  
 このメソッドは廃止され、使用する必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cchBuffer`  
 [in]作成するバッファーの長さ。  
  
 `lpBuffer`  
 [out]返されたバッファー。  
  
 `RVA`  
 [out]メソッドの相対仮想アドレス。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** Cor.h  
  
 **ライブラリ:** MsCorEE.dll にリソースとして使用  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICeeGen インターフェイス](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
