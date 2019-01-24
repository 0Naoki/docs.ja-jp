---
title: ISymUnmanagedNamespace インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace
helpviewer_keywords:
- ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: d42bea4e-5848-4e43-a883-69af7a313ce9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb5a833f7d6ed8f681f1f8d7ae79ac6113b8f2bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744376"
---
# <a name="isymunmanagednamespace-interface"></a>ISymUnmanagedNamespace インターフェイス
名前空間を表します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetName メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getname-method.md)|この名前空間の名前を取得します。|  
|[GetNamespaces メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getnamespaces-method.md)|この名前空間の子を取得します。|  
|[GetVariables メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getvariables-method.md)|この名前空間内のグローバル スコープで定義されたすべての変数を返します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>関連項目
- [シンボル ストア診断インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
