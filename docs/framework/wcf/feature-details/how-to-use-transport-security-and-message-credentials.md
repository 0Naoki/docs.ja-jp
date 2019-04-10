---
title: '方法: トランスポート セキュリティとメッセージ資格情報を使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
ms.openlocfilehash: f9c90ac93a27f90479ee7225f62afb98a5000fe9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321481"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="94a5d-102">方法: トランスポート セキュリティとメッセージ資格情報を使用する</span><span class="sxs-lookup"><span data-stu-id="94a5d-102">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="94a5d-103">トランスポートとメッセージの両方のセキュリティ モードの Windows Communication Foundation (WCF) を使用してトランスポートとメッセージの両方の資格情報でサービスをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-103">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="94a5d-104">つまり、トランスポート層セキュリティでは整合性と機密性が提供され、メッセージ層セキュリティでは、厳密なトランスポート セキュリティ機構では実現できないさまざまな資格情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="94a5d-104">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="94a5d-105">ここでは、<xref:System.ServiceModel.WSHttpBinding> バインディングと <xref:System.ServiceModel.NetTcpBinding> バインディングを使用して、メッセージ資格情報付きトランスポートを実装するための基本手順を示します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-105">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> <span data-ttu-id="94a5d-106">セキュリティ モードを設定する方法についての詳細については、次を参照してください。[方法。セキュリティ モードを設定](../../../../docs/framework/wcf/how-to-set-the-security-mode.md)します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-106">For more information about setting the security mode, see [How to: Set the Security Mode](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="94a5d-107">セキュリティ モードを `TransportWithMessageCredential` に設定した場合、トランスポート レベルのセキュリティを提供する実際の機構はトランスポートによって決まります。</span><span class="sxs-lookup"><span data-stu-id="94a5d-107">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="94a5d-108">この機構は、HTTP の場合は SSL (Secure Sockets Layer) over HTTP (HTTPS)、TCP の場合は SSL over TCP または Windows です。</span><span class="sxs-lookup"><span data-stu-id="94a5d-108">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="94a5d-109">トランスポートが HTTP (<xref:System.ServiceModel.WSHttpBinding> を使用) の場合は、トランスポート レベルのセキュリティが SSL over HTTP によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="94a5d-109">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="94a5d-110">この場合、このトピックで後述するように、ポートにバインドされた SSL 証明書を使用してサービスをホストするコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a5d-110">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="94a5d-111">トランスポートが TCP (<xref:System.ServiceModel.NetTcpBinding> を使用) の場合、既定では、Windows セキュリティ または SSL over TCP によってトランスポート レベルのセキュリティが提供されます。</span><span class="sxs-lookup"><span data-stu-id="94a5d-111">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="94a5d-112">SSL over TCP を使用する場合は、このトピックで後述するように、<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> メソッドを使用して証明書を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a5d-112">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="94a5d-113">WSHttpBinding と証明書を使用してトランスポート セキュリティを提供するには (コードを使用する場合)</span><span class="sxs-lookup"><span data-stu-id="94a5d-113">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="94a5d-114">HttpCfg.exe ツールを使用して、コンピューターの任意のポートに SSL 証明書をバインドします。</span><span class="sxs-lookup"><span data-stu-id="94a5d-114">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> <span data-ttu-id="94a5d-115">詳細については、「[方法 :SSL 証明書でポートを構成](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-115">For more information, see [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2. <span data-ttu-id="94a5d-116"><xref:System.ServiceModel.WSHttpBinding> クラスのインスタンスを作成し、<xref:System.ServiceModel.WSHttpSecurity.Mode%2A> プロパティを <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> に設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-116">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3. <span data-ttu-id="94a5d-117"><xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-117">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="94a5d-118">(詳細については、次を参照してください[資格情報の種類を選択する](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)。)。次のコードでは、<xref:System.ServiceModel.MessageCredentialType.Certificate> 値を使用しています。</span><span class="sxs-lookup"><span data-stu-id="94a5d-118">(For more information, see [Selecting a Credential Type](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="94a5d-119">適切なベース アドレスを持つ <xref:System.Uri> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-119">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="94a5d-120">このアドレスでは、"HTTPS" スキームを使用し、コンピューターの実際の名前と SSL 証明書のバインド先のポート番号を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a5d-120">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="94a5d-121">(または、構成で基本アドレスを設定できます。)</span><span class="sxs-lookup"><span data-stu-id="94a5d-121">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="94a5d-122"><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> メソッドを使用してサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-122">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6. <span data-ttu-id="94a5d-123"><xref:System.ServiceModel.ServiceHost> のインスタンスを作成し、<xref:System.ServiceModel.ICommunicationObject.Open%2A> メソッドを呼び出します。コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="94a5d-123">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="94a5d-124">NetTcpBinding と証明書を使用してトランスポート セキュリティを提供するには (コードを使用する場合)</span><span class="sxs-lookup"><span data-stu-id="94a5d-124">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="94a5d-125"><xref:System.ServiceModel.NetTcpBinding> クラスのインスタンスを作成し、<xref:System.ServiceModel.NetTcpSecurity.Mode%2A> プロパティを <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> に設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-125">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="94a5d-126"><xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-126">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="94a5d-127">次のコードでは、<xref:System.ServiceModel.MessageCredentialType.Certificate> 値を使用しています。</span><span class="sxs-lookup"><span data-stu-id="94a5d-127">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3. <span data-ttu-id="94a5d-128">適切なベース アドレスを持つ <xref:System.Uri> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-128">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="94a5d-129">アドレスには "net.tcp" スキーマを使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="94a5d-129">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="94a5d-130">(または、構成で基本アドレスを設定できます。)</span><span class="sxs-lookup"><span data-stu-id="94a5d-130">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4. <span data-ttu-id="94a5d-131"><xref:System.ServiceModel.ServiceHost> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-131">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5. <span data-ttu-id="94a5d-132"><xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> クラスの <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> メソッドを使用して、サービスに X.509 資格情報を明示的に設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-132">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6. <span data-ttu-id="94a5d-133"><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> メソッドを使用してサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-133">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7. <span data-ttu-id="94a5d-134">次のコードに示すように、<xref:System.ServiceModel.ICommunicationObject.Open%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-134">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="94a5d-135">NetTcpBinding と Windows を使用してトランスポート セキュリティを提供するには (コードを使用する場合)</span><span class="sxs-lookup"><span data-stu-id="94a5d-135">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1. <span data-ttu-id="94a5d-136"><xref:System.ServiceModel.NetTcpBinding> クラスのインスタンスを作成し、<xref:System.ServiceModel.NetTcpSecurity.Mode%2A> プロパティを <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> に設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-136">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="94a5d-137">トランスポート セキュリティが Windows を使用するように、<xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> を <xref:System.ServiceModel.TcpClientCredentialType.Windows> に設定します </span><span class="sxs-lookup"><span data-stu-id="94a5d-137">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="94a5d-138">(これは、既定の設定です)。</span><span class="sxs-lookup"><span data-stu-id="94a5d-138">(Note that this is the default.)</span></span>  
  
3. <span data-ttu-id="94a5d-139"><xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-139">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="94a5d-140">次のコードでは、<xref:System.ServiceModel.MessageCredentialType.Certificate> 値を使用しています。</span><span class="sxs-lookup"><span data-stu-id="94a5d-140">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="94a5d-141">適切なベース アドレスを持つ <xref:System.Uri> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-141">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="94a5d-142">アドレスには "net.tcp" スキーマを使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="94a5d-142">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="94a5d-143">(または、構成で基本アドレスを設定できます。)</span><span class="sxs-lookup"><span data-stu-id="94a5d-143">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="94a5d-144"><xref:System.ServiceModel.ServiceHost> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-144">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6. <span data-ttu-id="94a5d-145"><xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> クラスの <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> メソッドを使用して、サービスに X.509 資格情報を明示的に設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-145">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7. <span data-ttu-id="94a5d-146"><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> メソッドを使用してサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-146">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8. <span data-ttu-id="94a5d-147">次のコードに示すように、<xref:System.ServiceModel.ICommunicationObject.Open%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-147">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="94a5d-148">構成の使用</span><span class="sxs-lookup"><span data-stu-id="94a5d-148">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="94a5d-149">WSHttpBinding を使用するには</span><span class="sxs-lookup"><span data-stu-id="94a5d-149">To use the WSHttpBinding</span></span>  
  
1. <span data-ttu-id="94a5d-150">ポートにバインドされた SSL 証明書を使用してコンピューターを構成します </span><span class="sxs-lookup"><span data-stu-id="94a5d-150">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="94a5d-151">(詳細については、次を参照してください。[方法。SSL 証明書でポートを構成](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md))。</span><span class="sxs-lookup"><span data-stu-id="94a5d-151">(For more information, see [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="94a5d-152">設定する必要はありません、<`transport`> この構成要素の値。</span><span class="sxs-lookup"><span data-stu-id="94a5d-152">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2. <span data-ttu-id="94a5d-153">メッセージ レベルのセキュリティのクライアント資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-153">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="94a5d-154">次の例のセット、`clientCredentialType`の属性、<`message`> 要素を`UserName`します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-154">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="94a5d-155">NetTcpBinding と証明書を使用してトランスポート セキュリティを提供するには</span><span class="sxs-lookup"><span data-stu-id="94a5d-155">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1. <span data-ttu-id="94a5d-156">SSL over TCP の場合、`<behaviors>` 要素内で証明書を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a5d-156">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="94a5d-157">既定のストアの場所 (ローカル コンピューターの個人ストア) にある証明書を、発行者で指定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-157">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="94a5d-158">追加、 [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)をバインディング セクション</span><span class="sxs-lookup"><span data-stu-id="94a5d-158">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3. <span data-ttu-id="94a5d-159">バインド要素を追加して、`name` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-159">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="94a5d-160">追加の <`security`> 要素、およびセット、`mode`属性を`TransportWithMessageCredential`します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-160">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5. <span data-ttu-id="94a5d-161">追加の <`message>`要素、およびセット、`clientCredentialType`属性に適切な値。</span><span class="sxs-lookup"><span data-stu-id="94a5d-161">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="94a5d-162">NetTcpBinding と Windows を使用してトランスポート セキュリティを提供するには</span><span class="sxs-lookup"><span data-stu-id="94a5d-162">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1. <span data-ttu-id="94a5d-163">追加、 [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)をバインディング セクションでは、</span><span class="sxs-lookup"><span data-stu-id="94a5d-163">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2. <span data-ttu-id="94a5d-164">追加の <`binding`> 要素、`name`属性に適切な値。</span><span class="sxs-lookup"><span data-stu-id="94a5d-164">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="94a5d-165">追加の <`security`> 要素、およびセット、`mode`属性を`TransportWithMessageCredential`します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-165">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4. <span data-ttu-id="94a5d-166">追加の <`transport`> 要素、`clientCredentialType`属性を`Windows`します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-166">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5. <span data-ttu-id="94a5d-167">追加の <`message`> 要素、`clientCredentialType`属性に適切な値。</span><span class="sxs-lookup"><span data-stu-id="94a5d-167">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="94a5d-168">次のコードは、値を証明書に設定します。</span><span class="sxs-lookup"><span data-stu-id="94a5d-168">The following code sets the value to a certificate.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="94a5d-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="94a5d-169">See also</span></span>

- [<span data-ttu-id="94a5d-170">方法: セキュリティ モードを設定する</span><span class="sxs-lookup"><span data-stu-id="94a5d-170">How to: Set the Security Mode</span></span>](../../../../docs/framework/wcf/how-to-set-the-security-mode.md)
- [<span data-ttu-id="94a5d-171">サービスのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="94a5d-171">Securing Services</span></span>](../../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="94a5d-172">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="94a5d-172">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
