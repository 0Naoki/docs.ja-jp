---
title: "COR_TYPE_LAYOUT 構造体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPE_LAYOUT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPE_LAYOUT
helpviewer_keywords: COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 250d78dd9983b75fa7e1b3cfd99215160fbc2b1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="cortypelayout-structure"></a>COR_TYPE_LAYOUT 構造体
メモリ内のオブジェクトのレイアウトに関する情報が提供されます。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`parentID`|親の識別子は、この種類に入力します。 これは、NULL 型の id になります (token1 = 0、token2 = 0) に、型 id が対応している場合<xref:System.Object?displayProperty=nameWithType>です。|  
|`objectSize`|この型のオブジェクトの基本サイズ。 非可変サイズのオブジェクトの合計サイズです。|  
|`numFields`|この型のオブジェクトに含まれるフィールドの数。|  
|`boxOffset`|この型をボックス化する場合、先頭は、オブジェクトのフィールドのオフセット。 このフィールドは、プリミティブおよび構造体などの値の型に対してのみ有効です。|  
|`type`|この型が所属する CorElementType です。|  
  
## <a name="remarks"></a>コメント  
 場合`numFields`はゼロより大きく、呼び出すことができます、 [icordebugprocess 5::gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)メソッドをこの種類のフィールドに関する情報を取得します。 場合`type`は`ELEMENT_TYPE_STRING`、 `ELEMENT_TYPE_ARRAY`、または`ELEMENT_TYPE_SZARRAY`、この型のオブジェクトのサイズは変数、および渡すことができます、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)に構造体、 [icordebugprocess 5::getarraylayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)メソッドです。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [デバッグ構造体](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
