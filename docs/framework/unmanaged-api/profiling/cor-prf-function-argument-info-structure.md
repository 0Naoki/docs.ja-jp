---
title: "COR_PRF_FUNCTION_ARGUMENT_INFO 構造体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e26377fe3c5cfbae68f90087e3fb624ae4db0dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="corprffunctionargumentinfo-structure"></a>COR_PRF_FUNCTION_ARGUMENT_INFO 構造体
関数の引数を左から右方向で表します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`numRanges`|引数のブロックの数。 この値は、数、つまり、 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)構造体に、`ranges`配列。|  
|`totalArgumentSize`|すべての引数の合計サイズ。 つまり、この値は、引数の長さの合計です。|  
|`ranges`|配列`COR_PRF_FUNCTION_ARGUMENT_RANGE`関数の引数の 1 つのブロックを表す構造です。|  
  
## <a name="remarks"></a>コメント  
 関数は、多くの引数があります。 これらの引数には、メモリ内連続して格納される可能性がありますされません。 1 か所で 3 つの引数のブロック、別の場所に、2 つの引数のブロックと別の場所に 1 つの引数の最後のブロックがあります。 これらの引数はすべて、同じ関数の場合です。さまざまな場所にだけ格納されます。  
  
 `COR_PRF_FUNCTION_ARGUMENT_INFO`構造体は、1 つの関数の引数すべてを表します。 関数の引数のすべてのブロックを参照するのに配列を使用します。 そのため、1 つの関数があるか、1 つ`COR_PRF_FUNCTION_ARGUMENT_INFO`構造体は、複数の参照`COR_PRF_FUNCTION_ARGUMENT_RANGE`構造体、1 つまたは複数の関数の引数を参照します。  
  
 レジスタに格納されている引数は、構造を構築するためのメモリに書き込まれました。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorProf.idl  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [構造体のプロファイリング](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
