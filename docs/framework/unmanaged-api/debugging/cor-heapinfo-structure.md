---
title: "COR_HEAPINFO 構造体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPINFO
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPINFO
helpviewer_keywords: COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e316b964e3e983f50b81228709623e162529b05c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="corheapinfo-structure"></a>COR_HEAPINFO 構造体
列挙可能かどうかなど、ガベージ コレクション ヒープに関する情報が提供されます。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`ガベージ コレクション構造は有効では、ヒープを列挙することができます。それ以外の場合、`false`です。|  
|`pointerSize`|対象となるアーキテクチャ上のポインターのバイト単位のサイズ。|  
|`numHeaps`|プロセスでヒープ論理ガベージ コレクションの数。|  
|`concurrent`|`TRUE`場合は、同時実行ガベージ コレクションの (バック グラウンド) が有効であります。それ以外の場合、`FALSE`です。|  
|`gcType`|メンバー、 [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)をガベージ コレクターがワークステーションまたはサーバーで実行されているかどうかを示す列挙体です。|  
  
## <a name="remarks"></a>コメント  
 インスタンス、`COR_HEAPINFO`構造体が呼び出しによって返される、 [icordebugprocess 5::getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)メソッドです。  
  
 ガベージ コレクション ヒープ上のオブジェクトを列挙するには、前にする必要があります常に確認する、`areGCStructuresValid`フィールドをヒープが列挙可能な状態であることを確認します。 詳細については、次を参照してください。、 [icordebugprocess 5::getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)メソッドです。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [デバッグ構造体](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
