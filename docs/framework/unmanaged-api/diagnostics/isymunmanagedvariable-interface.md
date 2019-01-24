---
title: ISymUnmanagedVariable インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50c38c5a9e1799a460c5be1f7234b36968dc3da2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706892"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable インターフェイス
パラメーター、ローカル変数またはフィールドなどの変数を表します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetAddressField1 メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|この変数の最初のアドレス フィールドを取得します。 その意味は、アドレスの種類によって異なります。|  
|[GetAddressField2 メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|この変数の 2 番目のアドレス フィールドを取得します。 その意味は、アドレスの種類によって異なります。|  
|[GetAddressField3 メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|この変数の 3 番目のアドレス フィールドを取得します。 その意味は、アドレスの種類によって異なります。|  
|[GetAddressKind メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|この変数のアドレスの種類を取得します。|  
|[GetAttributes メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|この変数の属性フラグを取得します。|  
|[GetEndOffSet メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|親内でこの変数の終了オフセットを取得します。|  
|[GetName メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|この変数の名前を取得します。|  
|[GetSignature メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|この変数のシグネチャを取得します。|  
|[GetStartOffSet メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|この変数の親内の開始オフセットを取得します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>関連項目
- [シンボル ストア診断インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
