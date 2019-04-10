---
title: '方法: PrincipalPermissionAttribute クラスでアクセスを制限する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrincipalPermissionAttribute class
- WCF, authorization
- WCF, security
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
ms.openlocfilehash: ae2aa4c5629096ee7d888e7c4e334c3b6696db3f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323318"
---
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a><span data-ttu-id="6667f-102">方法: PrincipalPermissionAttribute クラスでアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="6667f-102">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>
<span data-ttu-id="6667f-103">Windows ドメイン コンピューターのリソースへのアクセスを制御することは、基本的なセキュリティ タスクです。</span><span class="sxs-lookup"><span data-stu-id="6667f-103">Controlling the access to resources on a Windows-domain computer is a basic security task.</span></span> <span data-ttu-id="6667f-104">たとえば、給与情報のような機密データは、特定のユーザーだけが表示できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6667f-104">For example, only certain users should be able to view sensitive data, such as payroll information.</span></span> <span data-ttu-id="6667f-105">ここでは、ユーザーが定義済みグループに属していることを要求することによって、メソッドへのアクセスを制限する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6667f-105">This topic explains how to restrict access to a method by demanding that the user belong to a predefined group.</span></span> <span data-ttu-id="6667f-106">実際のサンプルでは、次を参照してください。[サービス操作へのアクセスの承認](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="6667f-106">For a working sample, see [Authorizing Access to Service Operations](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).</span></span>  
  
 <span data-ttu-id="6667f-107">タスクは、2 つの別個の手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-107">The task consists of two separate procedures.</span></span> <span data-ttu-id="6667f-108">最初の手順では、グループを作成してユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6667f-108">The first creates the group and populates it with users.</span></span> <span data-ttu-id="6667f-109">2 番目の手順では、グループを指定するために <xref:System.Security.Permissions.PrincipalPermissionAttribute> クラスを適用します。</span><span class="sxs-lookup"><span data-stu-id="6667f-109">The second applies the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to specify the group.</span></span>  
  
### <a name="to-create-a-windows-group"></a><span data-ttu-id="6667f-110">Windows グループを作成するには</span><span class="sxs-lookup"><span data-stu-id="6667f-110">To create a Windows group</span></span>  
  
1. <span data-ttu-id="6667f-111">開く、**コンピュータの管理**コンソール。</span><span class="sxs-lookup"><span data-stu-id="6667f-111">Open the **Computer Management** console.</span></span>  
  
2. <span data-ttu-id="6667f-112">左側のパネルでをクリックして**ローカル ユーザーとグループ**します。</span><span class="sxs-lookup"><span data-stu-id="6667f-112">In the left panel, click **Local Users and Groups**.</span></span>  
  
3. <span data-ttu-id="6667f-113">右クリックして**グループ**、 をクリック**新規グループ**します。</span><span class="sxs-lookup"><span data-stu-id="6667f-113">Right-click **Groups**, and click **New Group**.</span></span>  
  
4. <span data-ttu-id="6667f-114">**グループ名**ボックスに、新しいグループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6667f-114">In the **Group Name** box, type a name for the new group.</span></span>  
  
5. <span data-ttu-id="6667f-115">**説明**ボックスに、新しいグループの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="6667f-115">In the **Description** box, type a description of the new group.</span></span>  
  
6. <span data-ttu-id="6667f-116">をクリックして、**追加**グループに新しいメンバーを追加するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6667f-116">Click the **Add** button to add new members to the group.</span></span>  
  
7. <span data-ttu-id="6667f-117">自分自身をグループに追加した場合は、次のコードをテストする前に、コンピューターからいったんログオフし、再度ログオンして自分自身をグループに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6667f-117">If you have added yourself to the group and want to test the following code, you must log off the computer and log back on to be included in the group.</span></span>  
  
### <a name="to-demand-user-membership"></a><span data-ttu-id="6667f-118">ユーザー メンバーシップを要求するには</span><span class="sxs-lookup"><span data-stu-id="6667f-118">To demand user membership</span></span>  
  
1. <span data-ttu-id="6667f-119">実装されたサービス コントラクト コードを含む Windows Communication Foundation (WCF) のコード ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6667f-119">Open the Windows Communication Foundation (WCF) code file that contains the implemented service contract code.</span></span> <span data-ttu-id="6667f-120">コントラクトの実装の詳細については、次を参照してください。 [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="6667f-120">For more information about implementing a contract, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="6667f-121">特定のグループに制限される必要がある各メソッドに <xref:System.Security.Permissions.PrincipalPermissionAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="6667f-121">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to each method that must be restricted to a specific group.</span></span> <span data-ttu-id="6667f-122"><xref:System.Security.Permissions.SecurityAttribute.Action%2A> プロパティを <xref:System.Security.Permissions.SecurityAction.Demand> に設定し、<xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> プロパティをグループの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="6667f-122">Set the <xref:System.Security.Permissions.SecurityAttribute.Action%2A> property to <xref:System.Security.Permissions.SecurityAction.Demand> and the <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> property to the name of the group.</span></span> <span data-ttu-id="6667f-123">例:</span><span class="sxs-lookup"><span data-stu-id="6667f-123">For example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="6667f-124"><xref:System.Security.Permissions.PrincipalPermissionAttribute> 属性をコントラクトに適用すると、<xref:System.Security.SecurityException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="6667f-124">If you apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a contract a <xref:System.Security.SecurityException> will be thrown.</span></span> <span data-ttu-id="6667f-125">この属性はメソッド レベルにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="6667f-125">You can only apply the attribute at the method level.</span></span>  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a><span data-ttu-id="6667f-126">証明書を使用したメソッドへのアクセスの制御</span><span class="sxs-lookup"><span data-stu-id="6667f-126">Using a Certificate to Control Access to a Method</span></span>  
 <span data-ttu-id="6667f-127">クライアント資格情報の種類が "証明書" の場合は、`PrincipalPermissionAttribute` クラスを使用してメソッドへのアクセスを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="6667f-127">You can also use the `PrincipalPermissionAttribute` class to control access to a method if the client credential type is a certificate.</span></span> <span data-ttu-id="6667f-128">そのためには、証明書のサブジェクトと拇印が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6667f-128">To do this, you must have the certificate's subject and thumbprint.</span></span>  
  
 <span data-ttu-id="6667f-129">そのプロパティ用の証明書を検証するを参照してください。[方法。MMC スナップインで証明書を表示](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)します。</span><span class="sxs-lookup"><span data-stu-id="6667f-129">To examine a certificate for its properties, see [How to: View Certificates with the MMC Snap-in](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span> <span data-ttu-id="6667f-130">拇印の値を検索するには、次を参照してください。[方法。証明書のサムプリントを取得](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)します。</span><span class="sxs-lookup"><span data-stu-id="6667f-130">To find the thumbprint value, see [How to: Retrieve the Thumbprint of a Certificate](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
#### <a name="to-control-access-using-a-certificate"></a><span data-ttu-id="6667f-131">証明書を使用してアクセスを制御するには</span><span class="sxs-lookup"><span data-stu-id="6667f-131">To control access using a certificate</span></span>  
  
1. <span data-ttu-id="6667f-132">アクセスを制限するメソッドに <xref:System.Security.Permissions.PrincipalPermissionAttribute> クラスを適用します。</span><span class="sxs-lookup"><span data-stu-id="6667f-132">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to the method you want to restrict access to.</span></span>  
  
2. <span data-ttu-id="6667f-133">属性のアクションを <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType> に設定します。</span><span class="sxs-lookup"><span data-stu-id="6667f-133">Set the action of the attribute to <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span></span>  
  
3. <span data-ttu-id="6667f-134">`Name` プロパティを、サブジェクト名と証明書の拇印で構成される文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="6667f-134">Set the `Name` property to a string that consists of the subject name and the certificate's thumbprint.</span></span> <span data-ttu-id="6667f-135">次の例に示すように、2 つの値をセミコロンと空白で区切ってください。</span><span class="sxs-lookup"><span data-stu-id="6667f-135">Separate the two values with a semicolon and a space, as shown in the following example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4. <span data-ttu-id="6667f-136">次の構成例に示すように、<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> プロパティを <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> に設定します。</span><span class="sxs-lookup"><span data-stu-id="6667f-136">Set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> as shown in the following configuration example:</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="6667f-137">この値を `UseAspNetRoles` に設定すると、`Name` の `PrincipalPermissionAttribute` プロパティを使用して文字列が比較されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-137">Setting this value to `UseAspNetRoles` indicates that the `Name` property of the `PrincipalPermissionAttribute` will be used to perform a string comparison.</span></span> <span data-ttu-id="6667f-138">証明書は、クライアント資格情報として使用される、既定で WCF を連結します証明書の共通名と、クライアントのプライマリ id に一意の値を作成する、セミコロンで拇印。</span><span class="sxs-lookup"><span data-stu-id="6667f-138">When a certificate is used as a client credential, by default WCF concatenates the certificate common name and the thumbprint with a semicolon to create a unique value for the client's primary identity.</span></span> <span data-ttu-id="6667f-139">`UseAspNetRoles` をサービスの `PrincipalPermissionMode` として設定している場合、このプライマリ ID の値と `Name` プロパティの値を比較してユーザーのアクセス権が決定されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-139">With `UseAspNetRoles` set as the `PrincipalPermissionMode` on the service, this primary identity value is compared with the `Name` property value to determine the access rights of the user.</span></span>  
  
     <span data-ttu-id="6667f-140">また、自己ホスト型サービスを作成する場合は、次のコードに示すように、コードの <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6667f-140">Alternatively, when creating a self-hosted service, set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property in code as shown in the following code:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6667f-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="6667f-141">See also</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- <xref:System.Security.Permissions.SecurityAction.Demand>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>
- [<span data-ttu-id="6667f-142">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="6667f-142">Authorizing Access to Service Operations</span></span>](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="6667f-143">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="6667f-143">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="6667f-144">サービス コントラクトの実装</span><span class="sxs-lookup"><span data-stu-id="6667f-144">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
