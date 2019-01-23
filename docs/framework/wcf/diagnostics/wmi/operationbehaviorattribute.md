---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: d0bf59e6064748a045f761777a2f8f3e88f1cb5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504328"
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>構文  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>メソッド  
 OperationBehaviorAttribute クラスで定義されるメソッドはありません。  
  
## <a name="properties"></a>プロパティ  
 OperationBehaviorAttribute クラスには、次のプロパティがあります。  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  
 データ型 : boolean  
  
 アクセスの種類:読み取り専用  
  
 パラメーターの自動破棄機能の状態です。  
  
### <a name="impersonation"></a>偽装  
 データ型: string  
  
 アクセスの種類:読み取り専用  
  
 操作がサポートする、呼び出し元の偽装レベルを示します。  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  
 データ型: string  
  
 アクセスの種類:読み取り専用  
  
 操作の呼び出し過程のどの時点でオブジェクトをリサイクルするかを示します。  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  
 データ型 : boolean  
  
 アクセスの種類:読み取り専用  
  
 未処理の例外が発生しなかった場合に、現在のトランザクションを自動的にコミットするかどうかを示します。  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  
 データ型 : boolean  
  
 アクセスの種類:読み取り専用  
  
 操作がトランザクションを必要とするかどうかを示します。  
  
## <a name="requirements"></a>必要条件  
  
|MOF|Servicemodel.mof にて宣言済み。|  
|---------|-----------------------------------|  
|Namespace|root\ServiceModel で定義|  
  
## <a name="see-also"></a>関連項目
- <xref:System.ServiceModel.OperationBehaviorAttribute>
