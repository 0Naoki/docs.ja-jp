---
title: "方法 : PrincipalPermissionAttribute クラスでアクセスを制限する"
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
- PrincipalPermissionAttribute class
- WCF, authorization
- WCF, security
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da91e3456fdca863980c89f45e0cc28db19170be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a>方法 : PrincipalPermissionAttribute クラスでアクセスを制限する
Windows ドメイン コンピューターのリソースへのアクセスを制御することは、基本的なセキュリティ タスクです。 たとえば、給与情報のような機密データは、特定のユーザーだけが表示できるようにする必要があります。 ここでは、ユーザーが定義済みグループに属していることを要求することによって、メソッドへのアクセスを制限する方法について説明します。 作業用サンプルについては、次を参照してください。[サービス操作へのアクセスを承認する](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)です。  
  
 タスクは、2 つの別個の手順で構成されます。 最初の手順では、グループを作成してユーザーを追加します。 2 番目の手順では、グループを指定するために <xref:System.Security.Permissions.PrincipalPermissionAttribute> クラスを適用します。  
  
### <a name="to-create-a-windows-group"></a>Windows グループを作成するには  
  
1.  開く、**コンピューターの管理**コンソールです。  
  
2.  左側のパネルでをクリックして**ローカル ユーザーとグループ**です。  
  
3.  右クリック**グループ**、 をクリック**新規グループ**です。  
  
4.  **グループ名**ボックスで、新しいグループの名前を入力します。  
  
5.  **説明**ボックスで、新しいグループの説明を入力します。  
  
6.  クリックして、**追加**グループに新しいメンバーを追加するボタンをクリックします。  
  
7.  自分自身をグループに追加した場合は、次のコードをテストする前に、コンピューターからいったんログオフし、再度ログオンして自分自身をグループに含める必要があります。  
  
### <a name="to-demand-user-membership"></a>ユーザー メンバーシップを要求するには  
  
1.  実装されたサービス コントラクト コードを含む [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] コード ファイルを開きます。 [!INCLUDE[crabout](../../../includes/crabout-md.md)]参照してください、コントラクトを実装する[サービス コントラクトを実装する](../../../docs/framework/wcf/implementing-service-contracts.md)です。  
  
2.  特定のグループに制限される必要がある各メソッドに <xref:System.Security.Permissions.PrincipalPermissionAttribute> 属性を適用します。 <xref:System.Security.Permissions.SecurityAttribute.Action%2A> プロパティを <xref:System.Security.Permissions.SecurityAction.Demand> に設定し、<xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> プロパティをグループの名前に設定します。 例:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    >  <xref:System.Security.Permissions.PrincipalPermissionAttribute> 属性をコントラクトに適用すると、<xref:System.Security.SecurityException> がスローされます。 この属性はメソッド レベルにのみ適用できます。  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a>証明書を使用したメソッドへのアクセスの制御  
 クライアント資格情報の種類が "証明書" の場合は、`PrincipalPermissionAttribute` クラスを使用してメソッドへのアクセスを制御することもできます。 そのためには、証明書のサブジェクトと拇印が必要になります。  
  
 そのプロパティ用の証明書を検証するを参照してください。[する方法: MMC スナップインで証明書の表示](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)です。 拇印の値を検索するには、次を参照してください。[する方法: 証明書のサムプリントを取得](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)です。  
  
#### <a name="to-control-access-using-a-certificate"></a>証明書を使用してアクセスを制御するには  
  
1.  アクセスを制限するメソッドに <xref:System.Security.Permissions.PrincipalPermissionAttribute> クラスを適用します。  
  
2.  属性のアクションを <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType> に設定します。  
  
3.  `Name` プロパティを、サブジェクト名と証明書の拇印で構成される文字列に設定します。 次の例に示すように、2 つの値をセミコロンと空白で区切ってください。  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4.  次の構成例に示すように、<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> プロパティを <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> に設定します。  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     この値を `UseAspNetRoles` に設定すると、`Name` の `PrincipalPermissionAttribute` プロパティを使用して文字列が比較されます。 クライアント資格情報として証明書を使用している場合、既定では、[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] は証明書の共通名と拇印をセミコロンで連結して、クライアントのプライマリ ID を表す一意の値が作成されます。 `UseAspNetRoles` をサービスの `PrincipalPermissionMode` として設定している場合、このプライマリ ID の値と `Name` プロパティの値を比較してユーザーのアクセス権が決定されます。  
  
     また、自己ホスト型サービスを作成する場合は、次のコードに示すように、コードの <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> プロパティを設定します。  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a>参照  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.SecurityAction.Demand>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>  
 [サービス操作へのアクセスの承認](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [セキュリティの概要](../../../docs/framework/wcf/feature-details/security-overview.md)  
 [サービス コントラクトの実装](../../../docs/framework/wcf/implementing-service-contracts.md)
