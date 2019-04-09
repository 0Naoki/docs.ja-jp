---
title: '方法: 時刻のずれの最大値を設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: e487da6316ec381c2009ee33575848dd80df8ab2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076629"
---
# <a name="how-to-set-a-max-clock-skew"></a><span data-ttu-id="2d0f4-102">方法: 時刻のずれの最大値を設定する</span><span class="sxs-lookup"><span data-stu-id="2d0f4-102">How to: Set a Max Clock Skew</span></span>
<span data-ttu-id="2d0f4-103">時刻が重要な要素となる機能は、2 台のコンピューターで時刻の設定が異なっていると失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-103">Time-critical functions can be derailed if the clock settings on two computers are different.</span></span> <span data-ttu-id="2d0f4-104">この可能性を減らすには、`MaxClockSkew` プロパティを <xref:System.TimeSpan> に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-104">To mitigate this possibility, you can set the `MaxClockSkew` property to a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="2d0f4-105">このプロパティは、次の 2 つのクラスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-105">This property is available on two classes:</span></span>  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d0f4-106">セキュリティで保護されたメッセージ交換に対して重要な変更を`MaxClockSkew`プロパティは、サービスまたはクライアントがブートス トラップされているときに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-106">Important   For a secure conversation, changes to the `MaxClockSkew` property  must be made when the service or client is bootstrapped.</span></span> <span data-ttu-id="2d0f4-107">これを行うには、プロパティを設定する必要があります、<xref:System.ServiceModel.Channels.SecurityBindingElement>によって返される、<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-107">To do this, you must set the property on the <xref:System.ServiceModel.Channels.SecurityBindingElement> returned by the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.</span></span>  
  
 <span data-ttu-id="2d0f4-108">システム提供のバインディングの 1 つでこのプロパティを変更するには、バインディングのコレクションでセキュリティ バインド要素を見つけて、`MaxClockSkew` プロパティを新しい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-108">To change the property on one of the system-provided bindings, you must find the security binding element in the collection of bindings and set the `MaxClockSkew` property to a new value.</span></span> <span data-ttu-id="2d0f4-109"><xref:System.ServiceModel.Channels.SecurityBindingElement> から派生される 2 つのクラスは、<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> クラスおよび <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> クラスです。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-109">Two classes derive from the <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="2d0f4-110">コレクションからセキュリティ バインディングを取得する場合は、`MaxClockSkew` プロパティを正しく設定するために、これらの型のどちらかにキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-110">When retrieving the security binding from the collection, you must cast to one of these types in order to correctly set the `MaxClockSkew` property.</span></span> <span data-ttu-id="2d0f4-111">次の例では、<xref:System.ServiceModel.WSHttpBinding> を使用していますが、これは <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-111">The following example uses a <xref:System.ServiceModel.WSHttpBinding>, which uses the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="2d0f4-112">各システム指定のバインディングで使用するセキュリティ バインディングの型を示す一覧については[System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-112">For a list that specifies which type of security binding to use in each system-provided binding, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
### <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a><span data-ttu-id="2d0f4-113">コードを使用して時刻のずれの新しい値を持つカスタム バインドを作成するには</span><span class="sxs-lookup"><span data-stu-id="2d0f4-113">To create a custom binding with a new clock skew value in code</span></span>  
  
1.  > [!WARNING]
    >  <span data-ttu-id="2d0f4-114">次のコードで名前空間への参照の追加に注意してください: <xref:System.ServiceModel.Channels>、 <xref:System.ServiceModel.Description>、 <xref:System.Security.Permissions>、および<xref:System.ServiceModel.Security.Tokens>します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-114">Note   Add references to the following namespaces in your code: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, and <xref:System.ServiceModel.Security.Tokens>.</span></span>  
  
     <span data-ttu-id="2d0f4-115"><xref:System.ServiceModel.WSHttpBinding> クラスのインスタンスを作成し、セキュリティ モードを <xref:System.ServiceModel.SecurityMode.Message> に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-115">Create an instance of a <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>  
  
2.  <span data-ttu-id="2d0f4-116"><xref:System.ServiceModel.Channels.BindingElementCollection> メソッドを呼び出して、<xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> クラスの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-116">Create a new instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class by calling the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3.  <span data-ttu-id="2d0f4-117"><xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> クラスの <xref:System.ServiceModel.Channels.BindingElementCollection> メソッドを使用して、セキュリティ バインド要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-117">Use the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method of the <xref:System.ServiceModel.Channels.BindingElementCollection> class to find the security binding element.</span></span>  
  
4.  <span data-ttu-id="2d0f4-118"><xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> メソッドを使用する場合には、実際の型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-118">When using the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method, cast to the actual type.</span></span> <span data-ttu-id="2d0f4-119">次の例では <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 型にキャストしています。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-119">The example below casts to the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> type.</span></span>  
  
5.  <span data-ttu-id="2d0f4-120">セキュリティ バインド要素の <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-120">Set the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> property on the security binding element.</span></span>  
  
6.  <span data-ttu-id="2d0f4-121">適切なサービス型とベース アドレスを使用して、<xref:System.ServiceModel.ServiceHost> を作成します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-121">Create a <xref:System.ServiceModel.ServiceHost> with an appropriate service type and base address.</span></span>  
  
7.  <span data-ttu-id="2d0f4-122"><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> メソッドを使用してエンドポイントを追加し、<xref:System.ServiceModel.Channels.CustomBinding> を含めます。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-122">Use the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method to add an endpoint and include the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### <a name="to-set-the-maxclockskew-in-configuration"></a><span data-ttu-id="2d0f4-123">構成で MaxClockSkew を設定するには</span><span class="sxs-lookup"><span data-stu-id="2d0f4-123">To set the MaxClockSkew in configuration</span></span>  
  
1.  <span data-ttu-id="2d0f4-124">作成、 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)で、 [\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)要素セクション。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-124">Create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) in the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section.</span></span>  
  
2.  <span data-ttu-id="2d0f4-125">作成、 [\<バインド >](../../../../docs/framework/misc/binding.md)要素、`name`属性に適切な値。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-125">Create a [\<binding>](../../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="2d0f4-126">`MaxClockSkewBinding` に設定する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-126">The following example sets it to `MaxClockSkewBinding`.</span></span>  
  
3.  <span data-ttu-id="2d0f4-127">エンコーディング要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-127">Add an encoding element.</span></span> <span data-ttu-id="2d0f4-128">次の例を追加、 [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-128">The example below adds a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
4.  <span data-ttu-id="2d0f4-129">追加、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素、`authenticationMode`属性を適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-129">Add a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element and set the `authenticationMode` attribute to an appropriate setting.</span></span> <span data-ttu-id="2d0f4-130">次の例では、この属性を `Kerberos` に設定して、サービスが Windows 認証を使用するように指定しています。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-130">The following example set the attribute to `Kerberos` to specify that the service use Windows authentication.</span></span>  
  
5.  <span data-ttu-id="2d0f4-131">追加、 [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)設定と、`maxClockSkew`属性の形式で値を`"##:##:##"`します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-131">Add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to a value in the form of `"##:##:##"`.</span></span> <span data-ttu-id="2d0f4-132">次の例では 7 分に設定しています。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-132">The following example sets it to 7 minutes.</span></span> <span data-ttu-id="2d0f4-133">必要に応じて、追加、 [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)設定と、`maxClockSkew`属性を適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-133">Optionally, add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to an appropriate setting.</span></span>  
  
6.  <span data-ttu-id="2d0f4-134">transport 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-134">Add a transport element.</span></span> <span data-ttu-id="2d0f4-135">次の例では、 [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-135">The following example uses an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
7.  <span data-ttu-id="2d0f4-136">セキュリティで保護されたメッセージ交換のセキュリティ設定がブートス トラップで行う必要があります、 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)要素。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-136">For a secure conversation, the security settings must occur at the bootstrap in the [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2d0f4-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d0f4-137">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2d0f4-138">方法: SecurityBindingElement を使用してカスタム バインドを作成する</span><span class="sxs-lookup"><span data-stu-id="2d0f4-138">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
