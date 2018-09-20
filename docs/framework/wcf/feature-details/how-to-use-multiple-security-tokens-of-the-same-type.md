---
title: '方法 : 同じ型の複数のセキュリティ トークンを使用する'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 25afbb268a0ef7772585a0f3829b56f135758b61
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46002685"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a>方法 : 同じ型の複数のセキュリティ トークンを使用する
-   [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0 では、クライアント メッセージには任意の型のトークンを 1 つしか含めることができませんでしたが、 現在は、同じ型の複数のトークンをクライアント メッセージに含めることができるようになりました。 このトピックでは、同じ型の複数のトークンをクライアント メッセージに含める方法について説明します。  
  
-   この方法でサービスを構成することはできません。サービスに含めることができるサポート トークンは 1 つだけです。  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a>同じ型の複数のセキュリティ トークンを使用するには  
  
1.  設定する空のバインド要素コレクションを作成します。  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <xref:System.ServiceModel.Channels.SecurityBindingElement> を呼び出して <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A> を作成します。  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> のコレクションを作成します。  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  SAML トークンをコレクションに追加します。  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  コレクションを <xref:System.ServiceModel.Channels.SecurityBindingElement> に追加します。  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  バインド要素をバインド要素コレクションに追加します。  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  作成した新しいカスタム バインディングをバインド要素コレクションから返します。  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a>例  
 上記の手順で説明したメソッド全体を次に示します。  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a>関連項目  
 [セキュリティ アーキテクチャ](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
