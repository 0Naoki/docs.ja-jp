---
title: "方法 : クレームを比較する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], comparing
- claims [WCF]
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf7a621a7aa457b2993c761caa2ad576d216638b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-compare-claims"></a>方法 : クレームを比較する
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 内の識別モデル インフラストラクチャを使用して、承認確認を実行します。 この場合、一般的なタスクとして、承認コンテキスト内のクレームが、要求されたアクションの実行や要求されたリソースへのアクセスに必要なクレームと比較されます。 このトピックでは、組み込みとカスタム クレームの型を含め、クレームの比較方法について説明します。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Id モデル インフラストラクチャを参照してください[管理クレームと Id モデル承認](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)です。  
  
 クレームの比較では、クレーム間で 3 つの部分 (型、権限、およびリソース) の比較が行われ、等しいかどうかが判断されます。 次の例を参照してください。  
  
 [!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
 [!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]  
  
 いずれのクレームにも、クレームの型として <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>、権限として <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>、および文字列リソースとして "someone" が設定されています。 クレームの 3 つの部分のすべてが等しいため、この 2 つのクレームは等しくなります。  
  
 組み込みのクレームの型の比較には、<xref:System.IdentityModel.Claims.Claim.Equals%2A> メソッドを使用します。 必要に応じて、クレーム固有の比較コードが使用されます。 たとえば、次の 2 つのユーザー プリンシパル名 (UPN) クレームがあるとします。  
  
 [!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
 [!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]  
  
 内の比較コード、<xref:System.IdentityModel.Claims.Claim.Equals%2A>メソッドを返します。`true`と見なし、`example\someone`と同じドメイン ユーザーを識別"someone@example.com"です。  
  
 カスタム クレームの型の比較にも、<xref:System.IdentityModel.Claims.Claim.Equals%2A> メソッドを使用できます。 ただし、クレームの <xref:System.IdentityModel.Claims.Claim.Resource%2A> プロパティから返された型がプリミティブ型ではない場合、<xref:System.IdentityModel.Claims.Claim.Equals%2A> が `true` を返すのは、`Resource` プロパティから返された値どうしが等しいと <xref:System.IdentityModel.Claims.Claim.Equals%2A> メソッドが見なした場合のみです。 これに該当しない場合は、`Resource` プロパティから返されたカスタム型で <xref:System.IdentityModel.Claims.Claim.Equals%2A> メソッドと <xref:System.Object.GetHashCode%2A> メソッドを上書きし、必要なカスタム処理を実行する必要があります。  
  
### <a name="comparing-built-in-claims"></a>組み込みのクレームの比較  
  
1.  <xref:System.IdentityModel.Claims.Claim> クラスの 2 つのインスタンスがある場合、次に示すコードのように、<xref:System.IdentityModel.Claims.Claim.Equals%2A> を使用して比較します。  
  
     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]  
  
### <a name="comparing-custom-claims-with-primitive-resource-types"></a>カスタム クレームとプリミティブ リソース型の比較  
  
1.  プリミティブ リソース型を含むカスタム クレームでは、次のコードのように、組み込みのクレームとして比較を実行できます。  
  
     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]  
  
2.  構造体またはクラスをベースとしたリソース型を含むカスタム クレームでは、そのリソース型で <xref:System.IdentityModel.Claims.Claim.Equals%2A> メソッドを上書きする必要があります。  
  
3.  まず、`obj` パラメーターが `null` であるかどうかを確認し、null である場合は `false` を返します。  
  
     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]  
  
4.  次に、<xref:System.Object.ReferenceEquals%2A> を呼び出し、パラメーターとして `this` と `obj` を渡します。 `true` が返されたら、`true` を返します。  
  
     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]  
  
5.  さらに、`obj` をクラスの型のローカル変数に割り当てます。 この処理が失敗すると、参照が `null` になります。 この場合、`false` が返されます。  
  
6.  現在のクレームと提供されたクレームを正しく比較するために必要なカスタム比較を実行します。  
  
## <a name="example"></a>例  
 次の例では、クレームの型がプリミティブ型以外のカスタム クレームを比較します。  
  
 [!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
 [!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]  
  
## <a name="see-also"></a>参照  
 [ID モデルを使用したクレームと承認の管理](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [方法 : カスタム クレームを作成する](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
