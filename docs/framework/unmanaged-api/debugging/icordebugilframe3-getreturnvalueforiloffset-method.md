---
title: "ICorDebugILFrame3::GetReturnValueForILOffset メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- csharp
- vb
api_name: ICorDebugILFrame3.GetReturnValueForILOffset
api_location: mscordbi.dll
api_type: COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c58319de99bdd8d7cce0ea55ccb3140a31a39bd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>ICorDebugILFrame3::GetReturnValueForILOffset メソッド
関数の戻り値をカプセル化する"ICorDebugValue"オブジェクトを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ILOffset`  
 オフセット IL。 「解説」を参照してください。  
  
 `ppReturnValue`  
 関数呼び出しの戻り値に関する情報を提供する"ICorDebugValue"インターフェイス オブジェクトのアドレスへのポインター。  
  
## <a name="remarks"></a>コメント  
 このメソッドはと共に使用、 [icordebugcode 3::getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)メソッドの戻り値を取得します。 次の 2 つのコード例で示すように、これは戻り値が無視されるメソッドの場合に特に役立ちます。 1 番目の例では、<xref:System.Int32.TryParse%2A?displayProperty=nameWithType> メソッドを呼び出しますが、メソッドの戻り値を無視します。  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 2 番目の例は、より一般的なデバッグの問題を示しています。 メソッド呼び出しで引数としてメソッドが使用されるため、デバッガーで呼び出されたメソッドをステップ実行する場合に限り、戻り値にアクセスできます。 多くの場合、特に呼び出されたメソッドが外部ライブラリで定義されている場合にはアクセスできません。  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 渡す場合、 [icordebugcode 3::getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)メソッド il オフセットを関数呼び出しサイトに、1 つまたは複数のネイティブ オフセット返します。 これによってデバッガーは、関数内のこうしたネイティブ オフセット上でブレークポイントを設定できます。 デバッガーがいずれかのブレークポイントに到達すると、戻り値を取得するためにこのメソッドに同じ IL オフセットを渡すことができます。 この場合、デバッガーは設定したブレークポイントすべてをクリアする必要があります。  
  
> [!WARNING]
>  [Icordebugcode 3::getreturnvalueliveoffset メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)と`ICorDebugILFrame3::GetReturnValueForILOffset`メソッドを使用する参照型だけの戻り値の情報を取得できます。 値型 (つまり、<xref:System.ValueType> から派生するすべての型) からの戻り値情報の取得はサポートされません。  
  
 によって指定された IL オフセット、`ILOffset`パラメーターは、関数呼び出しサイトにする必要があり、デバッグ対象をによって返されるネイティブ オフセットに設定されたブレークポイントで停止するか、 [icordebugcode 3::getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)メソッド同じ IL オフセット。 デバッグ対象が指定の IL オフセットに対して正確な場所で停止しない場合、API は失敗します。  
  
 関数呼び出しで値が返されない場合、API は失敗します。  
  
 `ICorDebugILFrame3::GetReturnValueForILOffset` メソッドは、x86 ベースおよび AMD64 システムでのみ使用できます。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [GetReturnValueLiveOffSet メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)  
 [ICorDebugILFrame3 インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
