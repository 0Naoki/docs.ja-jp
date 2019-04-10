---
title: '方法: ユーザー名とパスワードで認証する'
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: 08703209fd465f87e9dbc5e81a6ed90a4056324c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174136"
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="cd050-102">方法: ユーザー名とパスワードで認証する</span><span class="sxs-lookup"><span data-stu-id="cd050-102">How to: Authenticate with a User Name and Password</span></span>

<span data-ttu-id="cd050-103">このトピックでは、Windows ドメイン ユーザー名とパスワードを使用するクライアントの認証に Windows Communication Foundation (WCF) サービスを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cd050-103">This topic demonstrates how to enable a Windows Communication Foundation (WCF) service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="cd050-104">自己ホスト型 WCF サービスが稼働していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="cd050-104">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="cd050-105">基本的な自己ホスト型 WCF サービスは、「作成の例については[チュートリアル入門](../../../../docs/framework/wcf/getting-started-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="cd050-105">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="cd050-106">このトピックでは、サービスがコードで構成されているものとします。</span><span class="sxs-lookup"><span data-stu-id="cd050-106">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="cd050-107">構成ファイルを使用して同様のサービスを構成する例を参照してください表示したい場合[メッセージ セキュリティ ユーザー名](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span><span class="sxs-lookup"><span data-stu-id="cd050-107">If you would like to see an example of configuring a similar service using a configuration file see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span></span>  
  
 <span data-ttu-id="cd050-108">Windows ドメイン ユーザー名とパスワードを使用してクライアントを認証するようにサービスを構成するには、<xref:System.ServiceModel.WSHttpBinding> を使用し、その `Security.Mode` プロパティを `Message` に設定します。</span><span class="sxs-lookup"><span data-stu-id="cd050-108">To configure a service to authenticate its clients using Windows Domain username and passwords use the <xref:System.ServiceModel.WSHttpBinding> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="cd050-109">また、ユーザー名とパスワードをクライアントからサービスに送信するときに X.509 証明書を指定する必要があります。この証明書は、ユーザー名とパスワードの暗号化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="cd050-109">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>  
  
 <span data-ttu-id="cd050-110">クライアント側では、ユーザーにユーザー名とパスワードの入力を求め、WCF クライアント プロキシでユーザーの資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd050-110">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>  
  
## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="cd050-111">Windows ドメイン ユーザー名とパスワードを使用して認証する WCF サービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="cd050-111">To configure a WCF service to authenticate using Windows domain username and password</span></span>
  
1.  <span data-ttu-id="cd050-112">次のコードに示すように、<xref:System.ServiceModel.WSHttpBinding> のインスタンスを作成し、バインディングのセキュリティ モードを <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType> に設定した後、バインディングの `ClientCredentialType` を <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType> に設定し、構成されたバインディングを使用するサービス エンドポイントをサービス ホストに追加します。</span><span class="sxs-lookup"><span data-stu-id="cd050-112">Create an instance of the <xref:System.ServiceModel.WSHttpBinding>, set the security mode of the binding to <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, set the `ClientCredentialType` of the binding to <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType>, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  <span data-ttu-id="cd050-113">ネットワーク経由で送信されるユーザー名とパスワードの情報を暗号化するために使用するサーバー証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd050-113">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="cd050-114">次のコードは、上記のコードの直後に追加します。</span><span class="sxs-lookup"><span data-stu-id="cd050-114">This code should immediately follow the code above.</span></span> <span data-ttu-id="cd050-115">次の例から setup.bat ファイルによって作成される証明書を使用して、[メッセージ セキュリティ ユーザー名](../../../../docs/framework/wcf/samples/message-security-user-name.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="cd050-115">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md) sample:</span></span>  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     <span data-ttu-id="cd050-116">独自の証明書を使用する場合は、その証明書を参照するようにコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="cd050-116">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="cd050-117">作成して、証明書の使用の詳細については、次を参照してください。 [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="cd050-117">For more information about creating and using certificates see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="cd050-118">証明書がローカル コンピューターの信頼されたユーザー証明書ストア内に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd050-118">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="cd050-119">Mmc.exe を実行し、選択してこれを行う、**ファイル**、**スナップインの追加/削除しています.** メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="cd050-119">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="cd050-120">**スナップインを追加または**ダイアログ ボックスで、**証明書スナップイン** をクリック**追加**します。</span><span class="sxs-lookup"><span data-stu-id="cd050-120">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="cd050-121">証明書スナップイン] ダイアログ ボックス [**コンピューター アカウント**します。</span><span class="sxs-lookup"><span data-stu-id="cd050-121">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="cd050-122">既定では、「メッセージ セキュリティ ユーザー名」のサンプルから生成された証明書は個人/証明書フォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="cd050-122">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="cd050-123">[MMC のウィンドウ内の列に発行] には、"localhost"として表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd050-123">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="cd050-124">ドラッグ アンド ドロップに証明書、**信頼されたユーザー**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="cd050-124">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="cd050-125">これにより、WCF は、認証の実行時に、証明書を信頼された証明書として処理することができます。</span><span class="sxs-lookup"><span data-stu-id="cd050-125">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>  
  
## <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="cd050-126">ユーザー名とパスワードを渡すサービスを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="cd050-126">To call the service passing username and password</span></span>  
  
1.  <span data-ttu-id="cd050-127">クライアント アプリケーションは、ユーザー名とパスワードの入力をユーザーに求める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd050-127">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="cd050-128">次のコードでは、ユーザー名とパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="cd050-128">The following code asks the user for username and password.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="cd050-129">このコードは、入力中のパスワードが表示されるため、運用環境では使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cd050-129">This code should not be used in production as the password is displayed while being entered.</span></span>  
  
    ```  
    public static void GetPassword(out string username, out string password)  
            {  
                Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");  
                Console.WriteLine("   Enter username:");  
                username = Console.ReadLine();  
                Console.WriteLine("   Enter password:");  
                password = Console.ReadLine();             
                return;  
            }  
    ```  
  
2.  <span data-ttu-id="cd050-130">次のコードに示すように、クライアントの資格情報を指定して、クライアント プロキシのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd050-130">Create an instance of the client proxy specifying the client’s credentials as shown in the following code:</span></span>  
  
    ```  
    string username;  
    string password;  
  
    // Instantiate the proxy  
    Service1Client proxy = new Service1Client();  
  
    // Prompt the user for username & password  
    GetPassword(out username, out password);  
  
    // Set the user’s credentials on the proxy  
    proxy.ClientCredentials.UserName.UserName = username;  
    proxy.ClientCredentials.UserName.Password = password;  
  
    // Treat the test certificate as trusted  
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;  
    // Call the service operation using the proxy  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cd050-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd050-131">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.SecurityMode>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>
- [<span data-ttu-id="cd050-132">基本認証でのトランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="cd050-132">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)
- [<span data-ttu-id="cd050-133">分散アプリケーションのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="cd050-133">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)
- [<span data-ttu-id="cd050-134">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="cd050-134">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
