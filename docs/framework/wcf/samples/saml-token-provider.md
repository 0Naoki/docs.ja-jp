---
title: SAML トークン プロバイダー
ms.date: 03/30/2017
ms.assetid: eb16e5e2-4c8d-4f61-a479-9c965fcec80c
ms.openlocfilehash: 509469404e2c3866c26b5e1817a819519203c175
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2018
ms.locfileid: "46529289"
---
# <a name="saml-token-provider"></a><span data-ttu-id="d091a-102">SAML トークン プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d091a-102">SAML Token Provider</span></span>
<span data-ttu-id="d091a-103">このサンプルでは、カスタム クライアントの SAML トークン プロバイダーを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d091a-103">This sample demonstrates how to implement a custom client SAML token provider.</span></span> <span data-ttu-id="d091a-104">Windows Communication Foundation (WCF) でのトークン プロバイダーは、セキュリティ インフラストラクチャに資格情報を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-104">A token provider in Windows Communication Foundation (WCF) is used for supplying credentials to the security infrastructure.</span></span> <span data-ttu-id="d091a-105">一般的に、トークン プロバイダーは、ターゲットをチェックし、適切な証明書を発行して、セキュリティ インフラストラクチャがメッセージのセキュリティを保護できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d091a-105">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="d091a-106">WCF は、既定の Credential Manager Token Provider で出荷されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-106">WCF ships with the default Credential Manager Token Provider.</span></span> <span data-ttu-id="d091a-107">WCF にも付属、[!INCLUDE[infocard](../../../../includes/infocard-md.md)]トークン プロバイダー。</span><span class="sxs-lookup"><span data-stu-id="d091a-107">WCF also ships with an [!INCLUDE[infocard](../../../../includes/infocard-md.md)] token provider.</span></span> <span data-ttu-id="d091a-108">カスタム トークン プロバイダーは、次の場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d091a-108">Custom token providers are useful in the following cases:</span></span>  
  
-   <span data-ttu-id="d091a-109">トークン プロバイダーが連携動作できない資格情報ストアがある場合。</span><span class="sxs-lookup"><span data-stu-id="d091a-109">If you have a credential store that these token providers cannot operate with.</span></span>  
  
-   <span data-ttu-id="d091a-110">ユーザーは、WCF クライアント フレームワークが資格情報を使用する場合に、詳細を提供するときに、ポイントから資格情報を変換するための独自のカスタム メカニズムを提供する場合は。</span><span class="sxs-lookup"><span data-stu-id="d091a-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client framework uses the credentials.</span></span>  
  
-   <span data-ttu-id="d091a-111">カスタム トークンを構築している場合。</span><span class="sxs-lookup"><span data-stu-id="d091a-111">If you are building a custom token.</span></span>  
  
 <span data-ttu-id="d091a-112">このサンプルでは、使用する WCF クライアント フレームワークの外部から取得した SAML トークンを使用するカスタム トークン プロバイダーを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d091a-112">This sample shows how to build a custom token provider that allows a SAML token obtained from outside of the WCF client framework to be used.</span></span>  
  
 <span data-ttu-id="d091a-113">このサンプルに示されている手順の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d091a-113">To summarize, this sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="d091a-114">クライアントをカスタム トークン プロバイダーを使用して構成する手順。</span><span class="sxs-lookup"><span data-stu-id="d091a-114">How a client can be configured with a custom token provider.</span></span>  
  
-   <span data-ttu-id="d091a-115">SAML トークンをカスタム クライアント資格情報に渡す手順。</span><span class="sxs-lookup"><span data-stu-id="d091a-115">How a SAML token can be passed to the custom client credentials.</span></span>  
  
-   <span data-ttu-id="d091a-116">どのように、SAML トークンは、WCF クライアント フレームワークに提供されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-116">How the SAML token is provided to the WCF client framework.</span></span>  
  
-   <span data-ttu-id="d091a-117">サーバーがクライアントによってサーバーの X.509 証明書を使用して認証される手順。</span><span class="sxs-lookup"><span data-stu-id="d091a-117">How the server is authenticated by the client using the server's X.509 certificate.</span></span>  
  
 <span data-ttu-id="d091a-118">サービスは、そのサービスとの通信に使用する 2 つのエンドポイントを公開します。エンドポイントは構成ファイル App.config で定義します。各エンドポイントは、アドレス、バインディング、およびコントラクトがそれぞれ 1 つずつで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-118">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="d091a-119">バインディングの構成には、標準の `wsFederationHttpBinding` が使用されます。これはメッセージ セキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d091a-119">The binding is configured with a standard `wsFederationHttpBinding`, which uses Message security.</span></span> <span data-ttu-id="d091a-120">1 つのエンドポイントは、クライアントが対称証明キーを使用する SAML トークンで認証を行うことを想定しています。これに対してもう 1 つのエンドポイントでは、クライアントが非対称証明キーを使用する SAML トークンで認証を行うことを想定しています。</span><span class="sxs-lookup"><span data-stu-id="d091a-120">One endpoint expects the client to authenticate with a SAML token that uses a symmetric proof key while the other expects the client to authenticate with a SAML token that uses an asymmetric proof key.</span></span> <span data-ttu-id="d091a-121">また、サービスは `serviceCredentials` 動作を使用してサービス証明書の構成も行います。</span><span class="sxs-lookup"><span data-stu-id="d091a-121">The service also configures the service certificate using `serviceCredentials` behavior.</span></span> <span data-ttu-id="d091a-122">`serviceCredentials` 動作を使用すると、サービス証明書を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d091a-122">The `serviceCredentials` behavior allows you to configure a service certificate.</span></span> <span data-ttu-id="d091a-123">クライアントはサービス証明書を使用して、サービスを認証し、メッセージを保護します。</span><span class="sxs-lookup"><span data-stu-id="d091a-123">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="d091a-124">次の構成では、このトピックの最後のセットアップ手順で説明しているサンプル セットアップでインストールされる "localhost" 証明書を参照しています。</span><span class="sxs-lookup"><span data-stu-id="d091a-124">The following configuration references the "localhost" certificate installed during the sample setup as described in the setup instructions at the end of this topic.</span></span> <span data-ttu-id="d091a-125">`serviceCredentials` 動作を使用すると、SAML トークンに署名する信頼できる証明書を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d091a-125">The `serviceCredentials` behavior also allows you to configure certificates that are trusted to sign SAML tokens.</span></span> <span data-ttu-id="d091a-126">次の構成では、サンプルでインストールされる 'Alice' 証明書を参照しています。</span><span class="sxs-lookup"><span data-stu-id="d091a-126">The following configuration references the 'Alice' certificate installed during the sample.</span></span>  
  
```xml  
<system.serviceModel>  
 <services>  
  <service   
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
   <host>  
    <baseAddresses>  
     <!-- configure base address provided by host -->  
     <add    
  baseAddress="http://localhost:8000/servicemodelsamples/service/" />  
    </baseAddresses>  
   </host>  
   <!-- use base address provided by host -->  
   <!-- Endpoint that expect SAML tokens with Symmetric proof keys -->  
   <endpoint address="calc/symm"  
             binding="wsFederationHttpBinding"  
             bindingConfiguration="Binding1"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   <!-- Endpoint that expect SAML tokens with Asymmetric proof keys -->  
   <endpoint address="calc/asymm"  
             binding="wsFederationHttpBinding"  
             bindingConfiguration="Binding2"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </service>  
 </services>  
  
 <bindings>  
  <wsFederationHttpBinding>  
   <!-- Binding that expect SAML tokens with Symmetric proof keys -->  
   <binding name="Binding1">  
    <security mode="Message">  
     <message negotiateServiceCredential ="false"   
              issuedKeyType="SymmetricKey"   
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />  
    </security>  
   </binding>  
   <!-- Binding that expect SAML tokens with Asymmetric proof keys -->  
   <binding name="Binding2">  
    <security mode="Message">  
     <message negotiateServiceCredential ="false"  
              issuedKeyType="AsymmetricKey"   
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />  
    </security>  
   </binding>          
  </wsFederationHttpBinding>  
 </bindings>  
  
 <behaviors>  
  <serviceBehaviors>  
   <behavior name="CalculatorServiceBehavior">  
    <!--   
    The serviceCredentials behavior allows one to define a service certificate.  
    A service certificate is used by a client to authenticate the service and provide message protection.  
    This configuration references the "localhost" certificate installed during the setup instructions.  
    -->  
    <serviceCredentials>  
     <!-- Set allowUntrustedRsaIssuers to true to allow self-signed, asymmetric key based SAML tokens -->  
     <issuedTokenAuthentication allowUntrustedRsaIssuers ="true" >  
      <!-- Add Alice to the list of certs trusted to issue SAML tokens -->  
      <knownCertificates>  
       <add storeLocation="LocalMachine"   
            storeName="TrustedPeople"   
            x509FindType="FindBySubjectName"   
            findValue="Alice"/>  
      </knownCertificates>  
     </issuedTokenAuthentication>  
     <serviceCertificate storeLocation="LocalMachine"  
                         storeName="My"  
                         x509FindType="FindBySubjectName"  
                         findValue="localhost"  />  
    </serviceCredentials>  
   </behavior>  
  </serviceBehaviors>  
 </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="d091a-127">次の手順は、カスタムの SAML トークン プロバイダーを開発し、それを WCF に統合する方法を示します。 セキュリティ フレームワーク。</span><span class="sxs-lookup"><span data-stu-id="d091a-127">The following steps show how to develop a custom SAML token provider and integrate it with WCF: security framework:</span></span>  
  
1.  <span data-ttu-id="d091a-128">カスタムの SAML トークン プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d091a-128">Write a custom SAML token provider.</span></span>  
  
     <span data-ttu-id="d091a-129">サンプルでは、構築時に提供される SAML アサーションに基づいてセキュリティ トークンを返す、カスタムの SAML トークン プロバイダーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d091a-129">The sample implements a custom SAML token provider that returns a security token based on a SAML assertion that is provided at construction time.</span></span>  
  
     <span data-ttu-id="d091a-130">このタスクを実行するため、カスタム トークン プロバイダーは <xref:System.IdentityModel.Selectors.SecurityTokenProvider> クラスから派生し、<xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d091a-130">To perform this task, the custom token provider is derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> method.</span></span> <span data-ttu-id="d091a-131">このメソッドは、新しい `SecurityToken` を作成して返します。</span><span class="sxs-lookup"><span data-stu-id="d091a-131">This method creates and returns a new `SecurityToken`.</span></span>  
  
    ```  
    protected override SecurityToken GetTokenCore(TimeSpan timeout)  
    {  
     // Create a SamlSecurityToken from the provided assertion  
     SamlSecurityToken samlToken = new SamlSecurityToken(assertion);  
  
     // Create a SecurityTokenSerializer that will be used to   
     // serialize the SamlSecurityToken  
     WSSecurityTokenSerializer ser = new WSSecurityTokenSerializer();  
     // Create a memory stream to write the serialized token into  
     // Use an initial size of 64Kb  
     MemoryStream s = new MemoryStream(UInt16.MaxValue);  
  
     // Create an XmlWriter over the stream  
     XmlWriter xw = XmlWriter.Create(s);  
  
     // Write the SamlSecurityToken into the stream  
     ser.WriteToken(xw, samlToken);  
  
     // Seek back to the beginning of the stream  
     s.Seek(0, SeekOrigin.Begin);  
  
     // Load the serialized token into a DOM  
     XmlDocument dom = new XmlDocument();  
     dom.Load(s);  
  
     // Create a KeyIdentifierClause for the SamlSecurityToken  
     SamlAssertionKeyIdentifierClause samlKeyIdentifierClause = samlToken.CreateKeyIdentifierClause<SamlAssertionKeyIdentifierClause>();  
  
    // Return a GenericXmlToken from the XML for the   
    // SamlSecurityToken, the proof token, the valid from and valid  
    // until times from the assertion and the key identifier clause  
    // created above  
    return new GenericXmlSecurityToken(dom.DocumentElement, proofToken, assertion.Conditions.NotBefore, assertion.Conditions.NotOnOrAfter, samlKeyIdentifierClause, samlKeyIdentifierClause, null);  
    }  
    ```  
  
2.  <span data-ttu-id="d091a-132">カスタム セキュリティ トークン マネージャーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d091a-132">Write custom security token manager.</span></span>  
  
     <span data-ttu-id="d091a-133"><xref:System.IdentityModel.Selectors.SecurityTokenManager> クラスは、<xref:System.IdentityModel.Selectors.SecurityTokenProvider> メソッド内で渡される特定の <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> の `CreateSecurityTokenProvider` の作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-133">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> class is used to create <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="d091a-134">セキュリティ トークン マネージャーは、トークン認証システムとトークン シリアライザーの作成にも使用されますが、このサンプルでは扱っていません。</span><span class="sxs-lookup"><span data-stu-id="d091a-134">A security token manager is also used to create token authenticators and token serializer, but those are not covered by this sample.</span></span> <span data-ttu-id="d091a-135">このサンプルでは、カスタム セキュリティ トークン マネージャーは <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> クラスを継承し、渡されたトークンの要件で SAML トークンが必要であることが示されている場合に、`CreateSecurityTokenProvider` メソッドをオーバーライドしてカスタムの SAML トークン プロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="d091a-135">In this sample the custom security token manager inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return the custom SAML token provider when the passed token requirements indicate that the SAML token is requested.</span></span> <span data-ttu-id="d091a-136">クライアント資格情報クラス (手順 3. を参照) がアサーションを指定していない場合、セキュリティ トークン マネージャーは適切なインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d091a-136">If the client credentials class (see step 3) has not specified an assertion, the security token manager creates an appropriate instance.</span></span>  
  
    ```  
    public class SamlSecurityTokenManager :  
     ClientCredentialsSecurityTokenManager  
    {  
     SamlClientCredentials samlClientCredentials;  
  
     public SamlSecurityTokenManager ( SamlClientCredentials samlClientCredentials)  
      : base(samlClientCredentials)  
     {  
      // Store the creating client credentials  
      this.samlClientCredentials = samlClientCredentials;  
     }  
  
     public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )  
     {  
      // If token requirement matches SAML token return the   
      // custom SAML token provider  
      if (tokenRequirement.TokenType == SecurityTokenTypes.Saml ||  
          tokenRequirement.TokenType == "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1")  
      {  
       // Retrieve the SAML assertion and proof token from the   
       // client credentials  
       SamlAssertion assertion = this.samlClientCredentials.Assertion;  
       SecurityToken prooftoken = this.samlClientCredentials.ProofToken;  
  
       // If either the assertion of proof token is null...  
       if (assertion == null || prooftoken == null)  
       {  
        // ...get the SecurityBindingElement and then the   
        // specified algorithm suite  
        SecurityBindingElement sbe = null;  
        SecurityAlgorithmSuite sas = null;  
  
        if ( tokenRequirement.TryGetProperty<SecurityBindingElement> ( "http://schemas.microsoft.com/ws/2006/05/servicemodel/securitytokenrequirement/SecurityBindingElement", out sbe))  
        {  
         sas = sbe.DefaultAlgorithmSuite;  
        }  
  
        // If the token requirement is for a SymmetricKey based token..  
        if (tokenRequirement.KeyType == SecurityKeyType.SymmetricKey)  
        {  
         // Create a symmetric proof token  
         prooftoken = SamlUtilities.CreateSymmetricProofToken ( tokenRequirement.KeySize );  
         // and a corresponding assertion based on the claims specified in the client credentials  
         assertion = SamlUtilities.CreateSymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, new X509SecurityToken ( samlClientCredentials.ClientCertificate.Certificate ), new X509SecurityToken ( samlClientCredentials.ServiceCertificate.DefaultCertificate ), (BinarySecretSecurityToken)prooftoken, sas);  
        }  
        // otherwise...  
        else  
        {  
         // Create an asymmetric proof token  
         prooftoken = SamlUtilities.CreateAsymmetricProofToken();  
         // and a corresponding assertion based on the claims   
         // specified in the client credentials  
         assertion = SamlUtilities.CreateAsymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, prooftoken, sas );  
        }  
       }  
  
       // Create a SamlSecurityTokenProvider based on the assertion and proof token  
       return new SamlSecurityTokenProvider(assertion, prooftoken);  
      }  
      // otherwise use base implementation  
      else  
      {  
       return base.CreateSecurityTokenProvider(tokenRequirement);  
      }  
    }  
    ```  
  
3.  <span data-ttu-id="d091a-137">カスタム クライアント資格情報を作成します。</span><span class="sxs-lookup"><span data-stu-id="d091a-137">Write a custom client credential.</span></span>  
  
     <span data-ttu-id="d091a-138">クライアント資格情報クラスは、クライアント プロキシ用に構成された資格情報を表すために使用され、トークン認証システム、トークン プロバイダー、およびトークン シリアライザーの取得に使用されるセキュリティ トークン マネージャーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d091a-138">Client credentials class is used to represent the credentials that are configured for the client proxy and creates a security token manager that is used to obtain token authenticators, token providers and token serializer.</span></span>  
  
    ```  
    public class SamlClientCredentials : ClientCredentials  
    {  
     ClaimSet claims;  
     SamlAssertion assertion;  
     SecurityToken proofToken;  
  
     public SamlClientCredentials() : base()  
     {  
      // Set SupportInteractive to false to suppress Cardspace UI  
      base.SupportInteractive = false;  
     }  
  
     protected SamlClientCredentials(SamlClientCredentials other) : base ( other )  
     {  
      // Just do reference copy given sample nature  
      this.assertion = other.assertion;  
      this.claims = other.claims;  
      this.proofToken = other.proofToken;  
     }  
  
     public SamlAssertion Assertion { get { return assertion; } set { assertion = value; } }  
  
     public SecurityToken ProofToken { get { return proofToken; } set { proofToken = value; } }  
     public ClaimSet Claims { get { return claims; } set { claims = value; } }  
  
     protected override ClientCredentials CloneCore()  
     {  
      return new SamlClientCredentials(this);  
     }  
  
     public override SecurityTokenManager CreateSecurityTokenManager()  
     {  
      // return custom security token manager  
      return new SamlSecurityTokenManager(this);  
     }  
    }  
    ```  
  
4.  <span data-ttu-id="d091a-139">カスタム クライアント資格情報を使用するようクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="d091a-139">Configure the client to use the custom client credential.</span></span>  
  
     <span data-ttu-id="d091a-140">サンプルでは既定のクライアント資格情報を削除し、新しいクライアント資格情報クラスを提供して、クライアントがカスタム クライアント資格情報を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d091a-140">The sample deletes the default client credential class and supplies the new client credential class so the client can use the custom client credential.</span></span>  
  
    ```  
    // Create new credentials class  
    SamlClientCredentials samlCC = new SamlClientCredentials();  
  
    // Set the client certificate. This is the cert that will be used to sign the SAML token in the symmetric proof key case  
    samlCC.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "Alice");  
  
    // Set the service certificate. This is the cert that will be used to encrypt the proof key in the symmetric proof key case  
    samlCC.ServiceCertificate.SetDefaultCertificate(StoreLocation.CurrentUser, StoreName.TrustedPeople, X509FindType.FindBySubjectName, "localhost");  
  
    // Create some claims to put in the SAML assertion  
    IList<Claim> claims = new List<Claim>();  
    claims.Add(Claim.CreateNameClaim(samlCC.ClientCertificate.Certificate.Subject));  
    ClaimSet claimset = new DefaultClaimSet(claims);  
    samlCC.Claims = claimset;  
  
    // set new credentials  
    client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));  
    client.ChannelFactory.Endpoint.Behaviors.Add(samlCC);  
    ```  
  
 <span data-ttu-id="d091a-141">サービスでは、呼び出し元に関連するクレームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-141">On the service, the claims associated with the caller are displayed.</span></span> <span data-ttu-id="d091a-142">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-142">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d091a-143">クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d091a-143">Press ENTER in the client window to shut down the client.</span></span>  
  
## <a name="setup-batch-file"></a><span data-ttu-id="d091a-144">セットアップ バッチ ファイル</span><span class="sxs-lookup"><span data-stu-id="d091a-144">Setup Batch File</span></span>  
 <span data-ttu-id="d091a-145">このサンプルに用意されている Setup.bat バッチ ファイルを使用すると、適切な証明書を使用してサーバーを構成し、サーバー証明書ベースのセキュリティを必要とする自己ホスト型アプリケーションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d091a-145">The Setup.bat batch file included with this sample allows you to configure the server with the relevant certificate to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="d091a-146">このバッチ ファイルは、複数のコンピューターを使用する場合またはホストなしの場合に応じて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d091a-146">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="d091a-147">次に、バッチ ファイルのセクションのうち、該当する構成で実行するために変更が必要となる部分を示します。</span><span class="sxs-lookup"><span data-stu-id="d091a-147">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>  
  
-   <span data-ttu-id="d091a-148">サーバー証明書の作成 :</span><span class="sxs-lookup"><span data-stu-id="d091a-148">Creating the server certificate:</span></span>  
  
     <span data-ttu-id="d091a-149">Setup.bat バッチ ファイルの次の行は、使用するサーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="d091a-149">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="d091a-150">`%SERVER_NAME%` 変数はサーバー名です。</span><span class="sxs-lookup"><span data-stu-id="d091a-150">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="d091a-151">この変数を変更して、使用するサーバー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d091a-151">Change this variable to specify your own server name.</span></span> <span data-ttu-id="d091a-152">このバッチ ファイルでの既定値は localhost です。</span><span class="sxs-lookup"><span data-stu-id="d091a-152">The default value in this batch file is localhost.</span></span>  
  
     <span data-ttu-id="d091a-153">証明書は、LocalMachine ストアの場所の My (Personal) ストアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-153">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss My -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="d091a-154">クライアントの信頼された証明書ストアへのサーバー証明書のインストール。</span><span class="sxs-lookup"><span data-stu-id="d091a-154">Installing the server certificate into the client's trusted certificate store:</span></span>  
  
     <span data-ttu-id="d091a-155">Setup.bat バッチ ファイルの次の行は、サーバー証明書をクライアントの信頼されたユーザーのストアにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d091a-155">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="d091a-156">この手順が必要なのは、Makecert.exe によって生成される証明書がクライアント システムにより暗黙には信頼されないからです。</span><span class="sxs-lookup"><span data-stu-id="d091a-156">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="d091a-157">マイクロソフト発行の証明書など、クライアントの信頼されたルート証明書に基づいた証明書が既にある場合は、クライアント証明書ストアにサーバー証明書を配置するこの手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="d091a-157">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r LocalMachine -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="d091a-158">発行元の証明書の作成</span><span class="sxs-lookup"><span data-stu-id="d091a-158">Creating the issuer certificate.</span></span>  
  
     <span data-ttu-id="d091a-159">Setup.bat バッチ ファイルの次の行は、使用する発行元の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="d091a-159">The following lines from the Setup.bat batch file create the issuer certificate to be used.</span></span> <span data-ttu-id="d091a-160">`%USER_NAME%` 変数は発行元の名前です。</span><span class="sxs-lookup"><span data-stu-id="d091a-160">The `%USER_NAME%` variable specifies the issuer name.</span></span> <span data-ttu-id="d091a-161">この変数を変更して、使用する発行元の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d091a-161">Change this variable to specify your own issuer name.</span></span> <span data-ttu-id="d091a-162">このバッチ ファイルでの既定値は Alice です。</span><span class="sxs-lookup"><span data-stu-id="d091a-162">The default value in this batch file is Alice.</span></span>  
  
     <span data-ttu-id="d091a-163">証明書は、CurrentUser 保存場所の My ストアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-163">The certificate is stored in My store under the CurrentUser store location.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss My -a sha1 -n CN=%USER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="d091a-164">サーバーの信頼された証明書ストアへの発行元証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="d091a-164">Installing the issuer certificate into the server's trusted certificate store.</span></span>  
  
     <span data-ttu-id="d091a-165">Setup.bat バッチ ファイルの次の行は、サーバー証明書をクライアントの信頼されたユーザーのストアにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d091a-165">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="d091a-166">この手順が必要なのは、Makecert.exe によって生成される証明書がクライアント システムにより暗黙には信頼されないからです。</span><span class="sxs-lookup"><span data-stu-id="d091a-166">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="d091a-167">マイクロソフト発行の証明書など、クライアントの信頼されたルート証明書に基づいた証明書が既にある場合は、サーバー証明書ストアに発行元証明書を配置するこの手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="d091a-167">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the server certificate store with the issuer certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="d091a-168">サンプルをセットアップしてビルドするには</span><span class="sxs-lookup"><span data-stu-id="d091a-168">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="d091a-169">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="d091a-169">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d091a-170">ソリューションをビルドする手順については、 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="d091a-170">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d091a-171">Svcutil.exe を使用してこのサンプルの構成を再生成した場合は、クライアント コードに一致するように、クライアント構成内のエンドポイント名を変更してください。</span><span class="sxs-lookup"><span data-stu-id="d091a-171">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="d091a-172">サンプルを同じコンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="d091a-172">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="d091a-173">管理特権で [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] コマンド プロンプトを実行し、サンプルのインストール フォルダーから Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="d091a-173">Run Setup.bat from the sample installation folder inside a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt run with administrator privileges.</span></span> <span data-ttu-id="d091a-174">これにより、サンプルの実行に必要なすべての証明書がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d091a-174">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d091a-175">Setup.bat バッチ ファイルは、[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] コマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="d091a-175">The Setup.bat batch file is designed to be run from a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt.</span></span> <span data-ttu-id="d091a-176">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] コマンド プロンプト内で設定された PATH 環境変数は、Setup.bat スクリプトで必要な実行可能ファイルが格納されているディレクトリを指しています。</span><span class="sxs-lookup"><span data-stu-id="d091a-176">The PATH environment variable set within the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2.  <span data-ttu-id="d091a-177">Service.exe を service\bin で起動します。</span><span class="sxs-lookup"><span data-stu-id="d091a-177">Launch Service.exe from service\bin.</span></span>  
  
3.  <span data-ttu-id="d091a-178">Client.exe を \client\bin で起動します。</span><span class="sxs-lookup"><span data-stu-id="d091a-178">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="d091a-179">クライアント アクティビティがクライアントのコンソール アプリケーションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d091a-179">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="d091a-180">クライアントとサービスが通信できるようにされていない場合[トラブルシューティングのヒント](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)します。</span><span class="sxs-lookup"><span data-stu-id="d091a-180">If the client and service are not able to communicate, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="d091a-181">サンプルを複数のコンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="d091a-181">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="d091a-182">サービス コンピューターにサービス バイナリ用のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d091a-182">Create a directory on the service computer for the service binaries.</span></span>  
  
2.  <span data-ttu-id="d091a-183">サービス プログラム ファイルを、サービス コンピューターのサービス ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d091a-183">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="d091a-184">Setup.bat ファイルと Cleanup.bat ファイルもサービス コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d091a-184">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="d091a-185">コンピューターの完全修飾ドメイン名を含むサブジェクト名を持つサーバー証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="d091a-185">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="d091a-186">新しい証明書名を反映するには、Service.exe.config ファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d091a-186">The Service.exe.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="d091a-187">サーバー証明書を作成するには、Setup.bat バッチ ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="d091a-187">You can create server certificate by modifying the Setup.bat batch file.</span></span> <span data-ttu-id="d091a-188">setup.bat ファイルは、管理特権を使用して開いた Visual Studio コマンド プロンプト ウィンドウで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d091a-188">Note that the setup.bat file must be run in a Visual Studio command prompt window opened with administrator privileges.</span></span> <span data-ttu-id="d091a-189">`%SERVER_NAME%` 変数には、サービスをホストするコンピューターの完全修飾ホスト名を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d091a-189">You must set the `%SERVER_NAME%` variable to the fully-qualified host name of the computer that is used to host the service.</span></span>  
  
4.  <span data-ttu-id="d091a-190">サーバー証明書をクライアントの CurrentUser-TrustedPeople ストアにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d091a-190">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="d091a-191">この手順は、サーバー証明書の発行元をクライアントが信頼できる場合は不要です。</span><span class="sxs-lookup"><span data-stu-id="d091a-191">This step is not necessary when the server certificate is issued by a client trusted issuer.</span></span>  
  
5.  <span data-ttu-id="d091a-192">サービス コンピューターの Service.exe.config ファイルで、ベース アドレスの値を localhost から完全修飾コンピューター名に変更します。</span><span class="sxs-lookup"><span data-stu-id="d091a-192">In the Service.exe.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6.  <span data-ttu-id="d091a-193">サービス コンピューターで、コマンド プロンプトから Service.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="d091a-193">On the service computer, run Service.exe from a command prompt.</span></span>  
  
7.  <span data-ttu-id="d091a-194">クライアント プログラム ファイルを、言語固有のフォルダーにある \client\bin\ フォルダーからクライアント コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d091a-194">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8.  <span data-ttu-id="d091a-195">クライアント コンピューターの Client.exe.config ファイルで、エンドポイントのアドレス値をサービスの新しいアドレスに合わせます。</span><span class="sxs-lookup"><span data-stu-id="d091a-195">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="d091a-196">クライアント コンピューターで、コマンド プロンプト ウィンドウから `Client.exe` を起動します。</span><span class="sxs-lookup"><span data-stu-id="d091a-196">On the client computer, launch `Client.exe` from a command prompt window.</span></span>  
  
10. <span data-ttu-id="d091a-197">クライアントとサービスが通信できるようにされていない場合[トラブルシューティングのヒント](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)します。</span><span class="sxs-lookup"><span data-stu-id="d091a-197">If the client and service are not able to communicate, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="d091a-198">サンプルの実行後にクリーンアップするには</span><span class="sxs-lookup"><span data-stu-id="d091a-198">To clean up after the sample</span></span>  
  
1.  <span data-ttu-id="d091a-199">サンプルの実行が終わったら、サンプル フォルダーにある Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="d091a-199">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d091a-200">関連項目</span><span class="sxs-lookup"><span data-stu-id="d091a-200">See Also</span></span>
