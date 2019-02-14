---
title: '方法: カスタム セキュリティ トークン プロバイダーを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
ms.openlocfilehash: 1a81f6eac5648406f50d9600b030828551b21c56
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261349"
---
# <a name="how-to-create-a-custom-security-token-provider"></a><span data-ttu-id="2afec-102">方法: カスタム セキュリティ トークン プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2afec-102">How to: Create a Custom Security Token Provider</span></span>
<span data-ttu-id="2afec-103">ここでは、カスタム セキュリティ トークン プロバイダーを持つ新しいトークンの種類を作成する方法と、そのプロバイダーをカスタム セキュリティ トークン マネージャーと統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2afec-103">This topic shows how to create new token types with a custom security token provider and how to integrate the provider with a custom security token manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2afec-104"><xref:System.IdentityModel.Tokens> 名前空間にあるシステム指定のトークンがユーザーの要件に一致しない場合、カスタム トークン プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2afec-104">Create a custom token provider if the system-provided tokens found in the <xref:System.IdentityModel.Tokens> namespace do not match your requirements.</span></span>  
  
 <span data-ttu-id="2afec-105">セキュリティ トークン プロバイダーは、クライアントまたはサービスの資格情報に基づいてセキュリティ トークンの表現を作成します。</span><span class="sxs-lookup"><span data-stu-id="2afec-105">The security token provider creates a security token representation based on information in the client or service credentials.</span></span> <span data-ttu-id="2afec-106">Windows Communication Foundation (WCF) のセキュリティでカスタム セキュリティ トークン プロバイダーを使用するには、カスタム資格情報とセキュリティ トークン マネージャーの実装を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2afec-106">To use the custom security token provider in Windows Communication Foundation (WCF) security, you must create custom credentials and security token manager implementations.</span></span>  
  
 <span data-ttu-id="2afec-107">カスタム資格情報とセキュリティ トークン マネージャーの詳細については、次を参照してください。、[チュートリアル。カスタムのクライアントとサービスの資格情報を作成する](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)します。</span><span class="sxs-lookup"><span data-stu-id="2afec-107">For more information about custom credentials and security token manager see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
### <a name="to-create-a-custom-security-token-provider"></a><span data-ttu-id="2afec-108">カスタム セキュリティ トークン プロバイダーを作成するには</span><span class="sxs-lookup"><span data-stu-id="2afec-108">To create a custom security token provider</span></span>  
  
1.  <span data-ttu-id="2afec-109"><xref:System.IdentityModel.Selectors.SecurityTokenProvider> クラスから派生する新しいクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="2afec-109">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class.</span></span>  
  
2.  <span data-ttu-id="2afec-110"><xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="2afec-110">Implement the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="2afec-111">このメソッドは、セキュリティ トークンのインスタンスを作成して返す役割を担います。</span><span class="sxs-lookup"><span data-stu-id="2afec-111">The method is responsible for creating and returning an instance of the security token.</span></span> <span data-ttu-id="2afec-112">`MySecurityTokenProvider` という名前のクラスを作成し、<xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> メソッドをオーバーライドして <xref:System.IdentityModel.Tokens.X509SecurityToken> クラスのインスタンスを返す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2afec-112">The following example creates a class named `MySecurityTokenProvider`, and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method to return an instance of the <xref:System.IdentityModel.Tokens.X509SecurityToken> class.</span></span> <span data-ttu-id="2afec-113">クラス コンストラクターには <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> クラスのインスタンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2afec-113">The class constructor requires an instance of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class.</span></span>  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a><span data-ttu-id="2afec-114">カスタム セキュリティ トークン マネージャーにカスタム セキュリティ トークン プロバイダーを統合するには</span><span class="sxs-lookup"><span data-stu-id="2afec-114">To integrate a custom security token provider with a custom security token manager</span></span>  
  
1.  <span data-ttu-id="2afec-115"><xref:System.IdentityModel.Selectors.SecurityTokenManager> クラスから派生する新しいクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="2afec-115">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.</span></span> <span data-ttu-id="2afec-116">以下の例は、<xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> クラスから派生した <xref:System.IdentityModel.Selectors.SecurityTokenManager> クラスから派生したクラスです。</span><span class="sxs-lookup"><span data-stu-id="2afec-116">(The example below derives from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class, which derives from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.)</span></span>  
  
2.  <span data-ttu-id="2afec-117">まだオーバーライドされていない場合は、<xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2afec-117">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method if is not already overridden.</span></span>  
  
     <span data-ttu-id="2afec-118"><xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>メソッドのインスタンスを返す、<xref:System.IdentityModel.Selectors.SecurityTokenProvider>クラスに適した、 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> WCF セキュリティのフレームワークで、メソッドに渡されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="2afec-118">The <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method is responsible for returning an instance of the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class appropriate to the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter passed to the method by the WCF security framework.</span></span> <span data-ttu-id="2afec-119">メソッドが適切なセキュリティ トークン パラメーターで呼び出された場合に、カスタム セキュリティ トークン プロバイダーの実装 (以前の手順で作成済み) を返すようにメソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="2afec-119">Modify the method to return the custom security token provider implementation (created in the previous procedure) when the method is called with an appropriate security token parameter.</span></span> <span data-ttu-id="2afec-120">セキュリティ トークン マネージャーの詳細については、次を参照してください。、[チュートリアル。カスタムのクライアントとサービスの資格情報を作成する](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)します。</span><span class="sxs-lookup"><span data-stu-id="2afec-120">For more information about the security token manager, see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
3.  <span data-ttu-id="2afec-121">
  <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> パラメーターに基づいてカスタム セキュリティ トークン プロバイダーを返すカスタム ロジックをメソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="2afec-121">Add custom logic to the method to enable it to return your custom security token provider based on the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter.</span></span> <span data-ttu-id="2afec-122">トークンの要件が満たされた場合に、カスタム セキュリティ トークン プロバイダーを返す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2afec-122">The following sample returns the custom security token provider if the token requirements are met.</span></span> <span data-ttu-id="2afec-123">要件には、X.509 セキュリティ トークンとメッセージの方向 (メッセージ出力にトークンが使用される) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2afec-123">The requirements include an X.509 security token and the message direction (that the token is used for message output).</span></span> <span data-ttu-id="2afec-124">他のすべての場合で、コードは基本クラスを呼び出し、他のセキュリティ トークンの要件に合わせてシステム指定の動作を維持します。</span><span class="sxs-lookup"><span data-stu-id="2afec-124">For all other cases, the code calls the base class to maintain the system-provided behavior for other security token requirements.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="2afec-125">例</span><span class="sxs-lookup"><span data-stu-id="2afec-125">Example</span></span>  
 <span data-ttu-id="2afec-126">完全な <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 実装と対応する <xref:System.IdentityModel.Selectors.SecurityTokenManager> 実装を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2afec-126">The following shows a complete <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation along with a corresponding <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementation.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="2afec-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2afec-127">See also</span></span>
- <xref:System.IdentityModel.Selectors.SecurityTokenProvider>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.X509SecurityToken>
- [<span data-ttu-id="2afec-128">チュートリアル: カスタムのクライアントとサービスの資格情報を作成します。</span><span class="sxs-lookup"><span data-stu-id="2afec-128">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)
- [<span data-ttu-id="2afec-129">カスタム セキュリティ トークン オーセンティケーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="2afec-129">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)
