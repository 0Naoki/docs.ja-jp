---
title: '方法: セキュリティ トークン サービスを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 98e82101-4cff-4bb8-a220-f7abed3556e5
ms.openlocfilehash: 1d2621b43428fa249fb6ebb820885ebe0a2221f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577259"
---
# <a name="how-to-create-a-security-token-service"></a><span data-ttu-id="eec20-102">方法: セキュリティ トークン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="eec20-102">How to: Create a Security Token Service</span></span>
<span data-ttu-id="eec20-103">セキュリティ トークン サービスは、WS-Trust 仕様に定義されているプロトコルを実装します。</span><span class="sxs-lookup"><span data-stu-id="eec20-103">A security token service implements the protocol defined in the WS-Trust specification.</span></span> <span data-ttu-id="eec20-104">このプロトコルでは、セキュリティ トークンの発行、更新、キャンセル、および検証を行うためのメッセージ形式とメッセージ交換パターンが定義されています。</span><span class="sxs-lookup"><span data-stu-id="eec20-104">This protocol defines message formats and message exchange patterns for issuing, renewing, canceling, and validating security tokens.</span></span> <span data-ttu-id="eec20-105">セキュリティ トークン サービスでは、これらの機能が 1 つ以上提供されます。</span><span class="sxs-lookup"><span data-stu-id="eec20-105">A given security token service provides one or more of these capabilities.</span></span> <span data-ttu-id="eec20-106">ここでは、最も一般的なシナリオであるトークンの発行の実装について説明します。</span><span class="sxs-lookup"><span data-stu-id="eec20-106">This topic looks at the most common scenario: implementing token issuance.</span></span>  
  
## <a name="issuing-tokens"></a><span data-ttu-id="eec20-107">トークンの発行</span><span class="sxs-lookup"><span data-stu-id="eec20-107">Issuing Tokens</span></span>  
 <span data-ttu-id="eec20-108">WS-Trust は、トークンを発行するための `RequestSecurityToken` XML スキーマ定義言語 (XSD: XML Schema Definition Language) スキーマ要素および `RequestSecurityTokenResponse` XSD スキーマ要素に基づいたメッセージ形式を定義しています。</span><span class="sxs-lookup"><span data-stu-id="eec20-108">WS-Trust defines message formats, based on the `RequestSecurityToken` XML Schema definition language (XSD) schema element, and `RequestSecurityTokenResponse` XSD schema element for performing token issuance.</span></span> <span data-ttu-id="eec20-109">また、関連するアクション URI (Uniform Resource Identifier) も定義しています。</span><span class="sxs-lookup"><span data-stu-id="eec20-109">In addition, it defines the associated Action Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="eec20-110">URI に関連付けられたアクション、`RequestSecurityToken`メッセージは `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue` します。</span><span class="sxs-lookup"><span data-stu-id="eec20-110">The action URI associated with the `RequestSecurityToken` message is `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`.</span></span> <span data-ttu-id="eec20-111">URI に関連付けられたアクション、`RequestSecurityTokenResponse`メッセージは `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue` します。</span><span class="sxs-lookup"><span data-stu-id="eec20-111">The action URI associated with the `RequestSecurityTokenResponse` message is   `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`.</span></span>  
  
### <a name="request-message-structure"></a><span data-ttu-id="eec20-112">要求メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="eec20-112">Request Message Structure</span></span>  
 <span data-ttu-id="eec20-113">発行要求メッセージの構造は、通常、次の項目で構成されます。</span><span class="sxs-lookup"><span data-stu-id="eec20-113">The issue request message structure typically consists of the following items:</span></span>  
  
-   <span data-ttu-id="eec20-114">要求の値は、URI を入力する`http://schemas.xmlsoap.org/ws/2005/02/trust/Issue`します。</span><span class="sxs-lookup"><span data-stu-id="eec20-114">A request type URI with a value of `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue`.</span></span>
  
-   <span data-ttu-id="eec20-115">"トークンの種類" URI。</span><span class="sxs-lookup"><span data-stu-id="eec20-115">A token type URI.</span></span> <span data-ttu-id="eec20-116">この URI の値は、Security Assertions Markup Language (SAML) 1.1 トークンの `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1` します。</span><span class="sxs-lookup"><span data-stu-id="eec20-116">For Security Assertions Markup Language (SAML) 1.1 tokens, the value of this URI is `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`.</span></span>  
  
-   <span data-ttu-id="eec20-117">発行済みトークンに関連付けられるキーのビット数を示すキー サイズの値。</span><span class="sxs-lookup"><span data-stu-id="eec20-117">A key size value that indicates the number of bits in the key to be associated with the issued token.</span></span>  
  
-   <span data-ttu-id="eec20-118">"キーの種類" URI。</span><span class="sxs-lookup"><span data-stu-id="eec20-118">A key type URI.</span></span> <span data-ttu-id="eec20-119">対称キーは、この URI の値は `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey` します。</span><span class="sxs-lookup"><span data-stu-id="eec20-119">For symmetric keys, the value of this URI is `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey`.</span></span>  
  
 <span data-ttu-id="eec20-120">さらに、2 つの項目が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eec20-120">In addition, a couple of other items might be present:</span></span>  
  
-   <span data-ttu-id="eec20-121">クライアントによって提供されたキー マテリアル。</span><span class="sxs-lookup"><span data-stu-id="eec20-121">Key material provided by the client.</span></span>  
  
-   <span data-ttu-id="eec20-122">発行済みトークンが使用されるターゲット サービスを示すスコープ情報。</span><span class="sxs-lookup"><span data-stu-id="eec20-122">Scope information that indicates the target service that the issued token will be used with.</span></span>  
  
 <span data-ttu-id="eec20-123">セキュリティ トークン サービスは、発行応答メッセージを作成する際に、発行要求メッセージの情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="eec20-123">The security token service uses the information in the issue request message when it constructs the Issue Response message.</span></span>  
  
## <a name="response-message-structure"></a><span data-ttu-id="eec20-124">応答メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="eec20-124">Response Message Structure</span></span>  
 <span data-ttu-id="eec20-125">発行応答メッセージの構造は、通常、次の項目で構成されます。</span><span class="sxs-lookup"><span data-stu-id="eec20-125">The issue response message structure typically consists of the following items;</span></span>  
  
-   <span data-ttu-id="eec20-126">発行済みセキュリティ トークン (例 : SAML 1.1 アサーション)。</span><span class="sxs-lookup"><span data-stu-id="eec20-126">The issued security token, for example, a SAML 1.1 assertion.</span></span>  
  
-   <span data-ttu-id="eec20-127">セキュリティ トークンに関連付けられた証明トークン。</span><span class="sxs-lookup"><span data-stu-id="eec20-127">A proof token associated with the security token.</span></span> <span data-ttu-id="eec20-128">対称キーでは、多くの場合、これは暗号化されたキー マテリアルです。</span><span class="sxs-lookup"><span data-stu-id="eec20-128">For symmetric keys, this is often an encrypted form of the key material.</span></span>  
  
-   <span data-ttu-id="eec20-129">発行済みセキュリティ トークンへの参照。</span><span class="sxs-lookup"><span data-stu-id="eec20-129">References to the issued security token.</span></span> <span data-ttu-id="eec20-130">通常、セキュリティ トークン サービスが返す参照は、2 とおりに使用できます。1 つは、クライアントによって送信された後続のメッセージ内に、発行済みトークンが存在する場合で、もう 1 つは、後続のメッセージ内にトークンが存在しない場合です。</span><span class="sxs-lookup"><span data-stu-id="eec20-130">Typically, the security token service returns a reference that can be used when the issued token appears in a subsequent message sent by the client and another that can be used when the token is not present in subsequent messages.</span></span>  
  
 <span data-ttu-id="eec20-131">さらに、2 つの項目が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eec20-131">In addition, a couple of other items might be present:</span></span>  
  
-   <span data-ttu-id="eec20-132">セキュリティ トークン サービスによって提供されたキー マテリアル。</span><span class="sxs-lookup"><span data-stu-id="eec20-132">Key material provided by the security token service.</span></span>  
  
-   <span data-ttu-id="eec20-133">共有キーを計算するために必要なアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="eec20-133">The algorithm needed to compute the shared key.</span></span>  
  
-   <span data-ttu-id="eec20-134">発行済みトークンの有効期間情報。</span><span class="sxs-lookup"><span data-stu-id="eec20-134">Lifetime information for the issued token.</span></span>  
  
## <a name="processing-request-messages"></a><span data-ttu-id="eec20-135">要求メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="eec20-135">Processing Request Messages</span></span>  
 <span data-ttu-id="eec20-136">セキュリティ トークン サービスは、要求メッセージのさまざまな部分を検査し、要求を満たすトークンを発行できることを確認することによって発行要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="eec20-136">The security token service processes the issue request by examining the various pieces of the request message and ensuring that it can issue a token that satisfies the request.</span></span> <span data-ttu-id="eec20-137">セキュリティ トークン サービスは、発行するトークンを作成する前に次のことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eec20-137">The security token service must determine the following before it constructs the token to be issued:</span></span>  
  
-   <span data-ttu-id="eec20-138">要求が、実際に発行されるトークンに対する要求であること。</span><span class="sxs-lookup"><span data-stu-id="eec20-138">The request really is a request for a token to be issued.</span></span>  
  
-   <span data-ttu-id="eec20-139">要求されたトークンの種類をセキュリティ トークン サービスがサポートしていること。</span><span class="sxs-lookup"><span data-stu-id="eec20-139">The security token service supports the requested token type.</span></span>  
  
-   <span data-ttu-id="eec20-140">要求を行う権限が要求者にあること。</span><span class="sxs-lookup"><span data-stu-id="eec20-140">The requester is authorized to make the request.</span></span>  
  
-   <span data-ttu-id="eec20-141">キー マテリアルに関する要求者の期待にセキュリティ トークン サービスが応えられること。</span><span class="sxs-lookup"><span data-stu-id="eec20-141">The security token service can meet the requester's expectations with respect to key material.</span></span>  
  
 <span data-ttu-id="eec20-142">トークンを作成する際には、トークンの署名に使用されるキーと共有キーの暗号化に使用されるキーの 2 つを決定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="eec20-142">Two vital parts of constructing a token are determining what key to sign the token with and what key to encrypt the shared key with.</span></span> <span data-ttu-id="eec20-143">トークンに署名が必要なのは、クライアントがターゲット サービスにトークンを提示する際に、そのサービスが、そのトークンを発行したのが信頼されるセキュリティ トークン サービスであると判定できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="eec20-143">The token needs to be signed so that when the client presents the token to the target service, that service can determine that the token was issued by a security token service that it trusts.</span></span> <span data-ttu-id="eec20-144">キー マテリアルは、ターゲット サービスが復号化できる方法で暗号化される必要があります。</span><span class="sxs-lookup"><span data-stu-id="eec20-144">The key material needs to be encrypted in such a way that the target service can decrypt that key material.</span></span>  
  
 <span data-ttu-id="eec20-145">SAML アサーションに署名する処理では、<xref:System.IdentityModel.Tokens.SigningCredentials> インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="eec20-145">Signing a SAML assertion involves creating a <xref:System.IdentityModel.Tokens.SigningCredentials> instance.</span></span> <span data-ttu-id="eec20-146">このクラスのコンストラクターは、次のものを受け取ります</span><span class="sxs-lookup"><span data-stu-id="eec20-146">The constructor for this class takes the following:</span></span>  
  
-   <span data-ttu-id="eec20-147">SAML アサーションに署名するために使用する <xref:System.IdentityModel.Tokens.SecurityKey>。</span><span class="sxs-lookup"><span data-stu-id="eec20-147">A <xref:System.IdentityModel.Tokens.SecurityKey> for the key to use to sign the SAML assertion.</span></span>  
  
-   <span data-ttu-id="eec20-148">使用する署名アルゴリズムを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="eec20-148">A string identifying the signature algorithm to use.</span></span>  
  
-   <span data-ttu-id="eec20-149">使用するダイジェスト アルゴリズムを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="eec20-149">A string identifying the digest algorithm to use.</span></span>  
  
-   <span data-ttu-id="eec20-150">アサーションの署名に使用されるキーを識別する <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="eec20-150">Optionally, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> that identifies the key to use to sign the assertion.</span></span>  
  
 [!code-csharp[c_CreateSTS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#1)]
 [!code-vb[c_CreateSTS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#1)]  
  
 <span data-ttu-id="eec20-151">共有キーを暗号化する処理では、キー マテリアルを受け取り、それをターゲット サービスが共有キーの復号化に使用できるキーで暗号化します。</span><span class="sxs-lookup"><span data-stu-id="eec20-151">Encrypting the shared key involves taking the key material and encrypting it with a key that the target service can use to decrypt the shared key.</span></span> <span data-ttu-id="eec20-152">通常は、ターゲット サービスの公開キーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="eec20-152">Typically, the public key of the target service is used.</span></span>  
  
 [!code-csharp[c_CreateSTS#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#2)]
 [!code-vb[c_CreateSTS#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#2)]  
  
 <span data-ttu-id="eec20-153">さらに、暗号化されたキーの <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> も必要です。</span><span class="sxs-lookup"><span data-stu-id="eec20-153">In addition, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> for the encrypted key is needed.</span></span>  
  
 [!code-csharp[c_CreateSTS#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#3)]
 [!code-vb[c_CreateSTS#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#3)]  
  
 <span data-ttu-id="eec20-154">最後に、この <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> を使用して、`SamlSubject` を `SamlToken` の一部として作成します。</span><span class="sxs-lookup"><span data-stu-id="eec20-154">This <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> is then used to create a `SamlSubject` as part of the `SamlToken`.</span></span>  
  
 [!code-csharp[c_CreateSTS#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#4)]
 [!code-vb[c_CreateSTS#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#4)]  
  
 <span data-ttu-id="eec20-155">詳細については、次を参照してください。[フェデレーション サンプル](../../../../docs/framework/wcf/samples/federation-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="eec20-155">For more information, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
## <a name="creating-response-messages"></a><span data-ttu-id="eec20-156">応答メッセージの作成</span><span class="sxs-lookup"><span data-stu-id="eec20-156">Creating Response Messages</span></span>  
 <span data-ttu-id="eec20-157">セキュリティ トークン サービスによって発行要求が処理され、発行されるトークンと証明キーが作成されたら、少なくとも、要求されたトークン、証明トークン、および発行されたトークンの参照を含む応答メッセージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eec20-157">Once the security token service processes the issue request and constructs the token to be issued along with the proof key, the response message needs to be constructed, including at least the requested token, the proof token, and the issued token references.</span></span> <span data-ttu-id="eec20-158">発行済みトークンは、通常、<xref:System.IdentityModel.Tokens.SamlSecurityToken> から作成された <xref:System.IdentityModel.Tokens.SamlAssertion> です。次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eec20-158">The issued token is typically a <xref:System.IdentityModel.Tokens.SamlSecurityToken> created from the <xref:System.IdentityModel.Tokens.SamlAssertion>, as shown in the following example.</span></span>  
  
 [!code-csharp[c_CreateSTS#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#5)]
 [!code-vb[c_CreateSTS#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#5)]  
  
 <span data-ttu-id="eec20-159">セキュリティ トークン サービスによって共有キー マテリアルが提供される場合は、<xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken> を作成することにより、証明トークンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eec20-159">In the case where the security token service provides the shared key material, the proof token is constructed by creating a <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span></span>  
  
 [!code-csharp[c_CreateSTS#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#6)]
 [!code-vb[c_CreateSTS#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#6)]  
  
 <span data-ttu-id="eec20-160">クライアントとセキュリティ トークン サービスは、共有キーのキー マテリアルを提供するときに、証明トークンを構成する方法の詳細については、次を参照してください。[フェデレーション サンプル](../../../../docs/framework/wcf/samples/federation-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="eec20-160">For more information about how to construct the proof token when the client and the security token service both provide key material for the shared key, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
 <span data-ttu-id="eec20-161">発行済みトークンの参照を作成するには、<xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="eec20-161">The issued token references are constructed by creating instances of the <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> class.</span></span>  
  
 [!code-csharp[c_CreateSTS#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#7)]
 [!code-vb[c_CreateSTS#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#7)]  
  
 <span data-ttu-id="eec20-162">最後に、これらの値を、クライアントに返される応答メッセージにシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="eec20-162">These various values are then serialized into the response message returned to the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eec20-163">例</span><span class="sxs-lookup"><span data-stu-id="eec20-163">Example</span></span>  
 <span data-ttu-id="eec20-164">セキュリティ トークン サービスの完全なコードは、次を参照してください。[フェデレーション サンプル](../../../../docs/framework/wcf/samples/federation-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="eec20-164">For full code for a security token service, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec20-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="eec20-165">See also</span></span>
- <xref:System.IdentityModel.Tokens.SigningCredentials>
- <xref:System.IdentityModel.Tokens.SecurityKey>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>
- <xref:System.IdentityModel.Tokens.SamlSecurityToken>
- <xref:System.IdentityModel.Tokens.SamlAssertion>
- <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>
- [<span data-ttu-id="eec20-166">フェデレーション サンプル</span><span class="sxs-lookup"><span data-stu-id="eec20-166">Federation Sample</span></span>](../../../../docs/framework/wcf/samples/federation-sample.md)
