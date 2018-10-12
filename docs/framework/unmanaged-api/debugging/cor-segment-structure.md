---
title: COR_SEGMENT 構造体
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deea4e6128eace0ffa539d77bb63f7629eb72354
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207405"
---
# <a name="corsegment-structure"></a>COR_SEGMENT 構造体
マネージ ヒープのメモリ領域に関する情報が含まれます。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`start`|メモリ領域の開始アドレス。|  
|`end`|メモリ領域の終了アドレス。|  
|`gen`|メモリ領域の生成を示す [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) 列挙メンバー。|  
|`heap`|メモリ領域が存在するヒープ番号。 詳細については、次の「解説」を参照してください。|  
  
## <a name="remarks"></a>コメント  
 `COR_SEGMENTS` 構造体は、マネージド ヒープのメモリ領域を表します。  `COR_SEGMENTS` オブジェクトは、[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) メソッドを呼び出すことによって入力される [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) コレクション オブジェクトのメンバーです。  
  
 `heap` フィールドは、報告されたヒープに対応するプロセッサ番号です。 ワークステーション ガベージ コレクターでは、ワークステーションにガベージ コレクション ヒープが 1 つしかないため、その値は常に 0 です。 サーバー ガベージ コレクターでは、その値はヒープがアタッチされているプロセッサに対応します。 ガベージ コレクターの実装の詳細が原因で、実際のプロセッサ数よりも、ガベージ コレクション ヒープが多かったり少なかったりする場合があります。  
  
## <a name="requirements"></a>必要条件  
 **:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [デバッグ構造体](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
