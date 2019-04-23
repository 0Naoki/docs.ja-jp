---
title: '方法: WCF サービスと WSE 3.0 クライアントを相互運用するために構成する'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 8f4407f66095f97a213d6cd987b4bd9a3ed340fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59303896"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="a78e5-102">方法: WCF サービスと WSE 3.0 クライアントを相互運用するために構成する</span><span class="sxs-lookup"><span data-stu-id="a78e5-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>
<span data-ttu-id="a78e5-103">Windows Communication Foundation (WCF) サービス ワイヤレベルの互換性が Web サービス拡張 3.0 Microsoft .NET (WSE) クライアントの Ws-addressing 仕様の 2004 年 8 月バージョンを使用する WCF サービスが構成されている場合。</span><span class="sxs-lookup"><span data-stu-id="a78e5-103">Windows Communication Foundation (WCF) services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when WCF services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="a78e5-104">WCF サービスを WSE 3.0 クライアントと相互運用できるようにするには</span><span class="sxs-lookup"><span data-stu-id="a78e5-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>  
  
1. <span data-ttu-id="a78e5-105">WCF サービス用のカスタム バインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-105">Define a custom binding for the WCF service.</span></span>  
  
     <span data-ttu-id="a78e5-106">メッセージ エンコーディングに 2004 年 8 月版の WS-Addressing 仕様が使用されるように指定するには、カスタム バインディングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a78e5-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>  
  
    1.  <span data-ttu-id="a78e5-107">子を追加[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)を[\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)のサービスの構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="a78e5-107">Add a child [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>  
  
    2.  <span data-ttu-id="a78e5-108">追加することで、バインディングの名前を指定、 [\<バインド >](../../../../docs/framework/misc/binding.md)を[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)と設定、`name`属性。</span><span class="sxs-lookup"><span data-stu-id="a78e5-108">Specify a name for the binding, by adding a [\<binding>](../../../../docs/framework/misc/binding.md) to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>  
  
    3.  <span data-ttu-id="a78e5-109">認証モードと子を追加することで、WSE 3.0 と互換性があるメッセージをセキュリティで保護するために使用する Ws-security 仕様のバージョン指定[\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)を[ \<バインド >](../../../../docs/framework/misc/binding.md)します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../../../docs/framework/misc/binding.md).</span></span>  
  
         <span data-ttu-id="a78e5-110">認証モードを設定するには、設定、`authenicationMode`の属性、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-110">To set the authentication mode, set the `authenicationMode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="a78e5-111">認証モードは、WSE 3.0 の設定不要のセキュリティ アサーションとほぼ同等です。</span><span class="sxs-lookup"><span data-stu-id="a78e5-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="a78e5-112">次の表では、WSE 3.0 の設定不要のセキュリティ アサーションに WCF での認証モードがマップされます。</span><span class="sxs-lookup"><span data-stu-id="a78e5-112">The following table maps authentication modes in WCF to turnkey security assertions in WSE 3.0.</span></span>  
  
        |<span data-ttu-id="a78e5-113">WCF 認証モード</span><span class="sxs-lookup"><span data-stu-id="a78e5-113">WCF Authentication Mode</span></span>|<span data-ttu-id="a78e5-114">WSE 3.0 の設定不要のセキュリティ アサーション</span><span class="sxs-lookup"><span data-stu-id="a78e5-114">WSE 3.0 turnkey security assertion</span></span>|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         <span data-ttu-id="a78e5-115">\* 主な違いの 1 つ、`mutualCertificate10Security`と`mutualCertificate11Security`設定不要のセキュリティ アサーションは WSE が SOAP メッセージをセキュリティ保護に使用する Ws-security 仕様のバージョン。</span><span class="sxs-lookup"><span data-stu-id="a78e5-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="a78e5-116">`mutualCertificate10Security` では WS-Security 1.0 が使用され、`mutualCertificate11Security` では WS-Security 1.1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a78e5-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="a78e5-117">Wcf の場合、Ws-security 仕様のバージョンがで指定された、`messageSecurityVersion`の属性、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-117">For WCF, the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="a78e5-118">SOAP メッセージ セキュリティで保護するために使用する Ws-security 仕様のバージョンを設定するには、設定、`messageSecurityVersion`の属性、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="a78e5-119">WSE 3.0 と相互運用するには、`messageSecurityVersion` 属性の値を <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A> に設定します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>  
  
    4.  <span data-ttu-id="a78e5-120">追加することで、WCF、Ws-addressing 仕様の 2004 年 8 月バージョンを使用するように指定、 [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)設定と、`messageVersion`の値を<xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-120">Specify that the August 2004 version of the WS-Addressing specification is used by WCF by adding a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a78e5-121">SOAP 1.2 の使用時には、`messageVersion` 属性を <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A> に設定します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>  
  
2. <span data-ttu-id="a78e5-122">サービスがカスタム バインドを使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-122">Specify that the service uses the custom binding.</span></span>  
  
    1.  <span data-ttu-id="a78e5-123">設定、`binding`の属性、 [\<エンドポイント >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)要素`customBinding`します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-123">Set the `binding` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>  
  
    2.  <span data-ttu-id="a78e5-124">設定、`bindingConfiguration`の属性、 [\<エンドポイント >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)要素で指定された値を`name`の属性、 [\<バインド >](../../../../docs/framework/misc/binding.md)カスタムバインディング。</span><span class="sxs-lookup"><span data-stu-id="a78e5-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) for the custom binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a78e5-125">例</span><span class="sxs-lookup"><span data-stu-id="a78e5-125">Example</span></span>  
 <span data-ttu-id="a78e5-126">次のコード例では、`Service.HelloWorldService` が WSE 3.0 クライアントと相互運用するためにカスタム バインドを使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="a78e5-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="a78e5-127">カスタム バインドには 2004 年 8 月版の WS-Addressing が指定され、WS-Security 1.1 の一連の仕様が、交換されるメッセージのエンコードに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a78e5-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="a78e5-128">メッセージは、<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> 認証モードを使用してセキュリティ保護されます。</span><span class="sxs-lookup"><span data-stu-id="a78e5-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a78e5-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a78e5-129">See also</span></span>

- [<span data-ttu-id="a78e5-130">方法: システム指定のバインディングをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="a78e5-130">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
