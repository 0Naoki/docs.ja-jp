---
title: '方法 : 要求/応答コントラクトを作成する'
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: 76a3bbb9415a34218896bc561066c7ac4a30e6b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489574"
---
# <a name="how-to-create-a-request-reply-contract"></a>方法 : 要求/応答コントラクトを作成する
要求/応答コントラクトは、応答を返すメソッドを指定します。 応答が送信され、このコントラクトの条件の下で要求に関連付けられる必要があります。 メソッドが応答を返さない場合 (C# の場合は `void` または Visual Basic の場合は `Sub`) でも、インフラストラクチャは、空のメッセージを作成して送信することで、メソッドが返ったことを呼び出し元に示します。 空の応答メッセージが送信されるのを防ぐには、操作で 1 方向コントラクトを使用します。  
  
### <a name="to-create-a-request-reply-contract"></a>要求/応答コントラクトを作成するには  
  
1.  選択したプログラミング言語でインターフェイスを作成します。  
  
2.  インターフェイスに <xref:System.ServiceModel.ServiceContractAttribute> 属性を適用します。  
  
3.  クライアントが呼び出すことのできる各メソッドに <xref:System.ServiceModel.OperationContractAttribute> 属性を適用します。  
  
4.  任意。 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> プロパティの値を `true` に設定して、空の応答メッセージが送信されることを防止します。 既定では、すべての操作は要求/応答コントラクトです。  
  
## <a name="example"></a>例  
 次のサンプルは、`Add` メソッドと `Subtract` メソッドを提供する電卓サービスのコントラクトを定義します。 `Multiply` メソッドは <xref:System.ServiceModel.OperationContractAttribute> クラスでマークされていないため、このコントラクトの一部ではありません。したがって、クライアントからはアクセスできません。  
  
```
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);
    
    [OperationContract]
    int Subtract(int a, int b);
    
    int Multiply(int a, int b)
}
```
  
-   操作コントラクトを指定する方法の詳細については、次を参照してください。、<xref:System.ServiceModel.OperationContractAttribute>クラスおよび<xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>プロパティです。  
  
-   <xref:System.ServiceModel.ServiceContractAttribute> 属性と <xref:System.ServiceModel.OperationContractAttribute> 属性を適用すると、サービスを展開した後に Web サービス記述言語 (WSDL) ドキュメントでサービス コントラクト定義が自動的に生成されます。 ドキュメントは、サービスの HTTP ベース アドレスに `?wsdl` を付け加えてしてダウンロードできます。 たとえば、`http://microsoft/CalculatorService?wsdl`  
  
## <a name="see-also"></a>関連項目  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [サービス コントラクトの設計](../../../../docs/framework/wcf/designing-service-contracts.md)  
 [方法 : 双方向コントラクトを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
