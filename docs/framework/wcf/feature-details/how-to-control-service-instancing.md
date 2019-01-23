---
title: '方法: サービスのインスタンス化の制御します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: 3e1e0669b083e30db01c571c44830adfaff31d79
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515310"
---
# <a name="how-to-control-service-instancing"></a>方法: サービスのインスタンス化の制御します。
サービスのインスタンス モードを設定することにより、<xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (およびそのユーザー定義のサービス オブジェクト) をいつ生成するかを指定できます。 設定できるモードについては、<xref:System.ServiceModel.InstanceContextMode> 列挙体を参照してください。 動作の詳細については、次を参照してください。[構成と、ランタイムの動作を拡張](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)します。 実施例については、次を参照してください。[動作](../../../../docs/framework/wcf/samples/behaviors.md)します。  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a>サービス インスタンスの有効期間をコードで制御するには  
  
1.  サービス クラスに <xref:System.ServiceModel.ServiceBehaviorAttribute> 属性を適用します。  
  
2.  <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> プロパティを <xref:System.ServiceModel.InstanceContextMode.PerCall>、<xref:System.ServiceModel.InstanceContextMode.PerSession>、<xref:System.ServiceModel.InstanceContextMode.Single> のいずれかの値に設定します。  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a>例  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 属性の <xref:System.ServiceModel.ServiceBehaviorAttribute> プロパティを <xref:System.ServiceModel.InstanceContextMode.PerCall> に設定するコード例を示します。  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a>関連項目
- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [サービス:動作サンプル](https://msdn.microsoft.com/library/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)
