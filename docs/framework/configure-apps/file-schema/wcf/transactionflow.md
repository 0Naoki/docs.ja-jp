---
title: "&lt;トランザクション フロー&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3720294ac937c6aa7ce99ab687efa76b2e860abb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="lttransactionflowgt"></a>&lt;トランザクション フロー&gt;
カスタム バインドのトランザクション フロー サポートを指定します。  
  
 \<system.serviceModel >  
\<バインド >  
\<customBinding >  
\<バインド >  
\<transactionFlow >  
  
## <a name="syntax"></a>構文  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|transactionProtocol|使用されるトランザクション プロトコルを指定します。 以下の値が有効です。<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> 既定値は OleTransactions です。<br /><br /> この属性は <xref:System.ServiceModel.TransactionProtocol> 型です。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<バインド >](../../../../../docs/framework/misc/binding.md)|カスタム バインドのすべてのバインド機能を定義します。|  
  
## <a name="remarks"></a>コメント  
 この要素により、受信トランザクションの目的のプロトコル形式を指定できるだけでなく、エンドポイントのバインディング設定で受信トランザクション フローを有効または無効にできます。 この構成要素を使用する方法については、次を参照してください。 [ServiceModel トランザクションの構成](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)と[トランザクション フローを有効にすると](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)です。  
  
> [!CAUTION]
>  `OleTransactions` プロトコルを使用してエンドポイント間でトランザクションをフローさせるとき、フロー先のエンドポイントが `OleTransactions` 以外のプロトコルを使用して再びフローを試みると、トランザクション タイムアウトが失われる場合があります。 その結果、OleTransactions ホップより後のすべてのダウンレベル ノードが、予想より遅くタイムアウトする可能性があります。  
  
## <a name="see-also"></a>参照  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [ServiceModel トランザクションの構成](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [トランザクション フローの有効化](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [バインディング](../../../../../docs/framework/wcf/bindings.md)  
 [バインディングの拡張](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [カスタム バインディング](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
