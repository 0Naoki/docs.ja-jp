---
title: メッセージ セキュリティ証明書
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
ms.openlocfilehash: b5a36d39e6e38f121bf3155c822681fb198f0850
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006420"
---
# <a name="message-security-certificate"></a><span data-ttu-id="dd232-102">メッセージ セキュリティ証明書</span><span class="sxs-lookup"><span data-stu-id="dd232-102">Message Security Certificate</span></span>
<span data-ttu-id="dd232-103">このサンプルでは、クライアントの認証で X.509 v3 証明書による WS-Security を使用するアプリケーションを実装する方法を示します。このアプリケーションでは、サーバーの X.509 v3 証明書を使用するサーバー認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd232-103">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span> <span data-ttu-id="dd232-104">このサンプルでは、クライアント/サーバー間のすべてのアプリケーション メッセージが署名されて暗号化される、既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd232-104">This sample uses default settings such that all application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="dd232-105">このサンプルがに基づいて、 [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md)クライアント コンソール プログラムとインターネット インフォメーション サービス (IIS) によってホストされるサービス ライブラリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-105">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) and consists of a client console program and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="dd232-106">サービスは、要求/応答通信パターンを定義するコントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="dd232-106">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd232-107">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd232-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="dd232-108">このサンプルは、構成を使用した認証の制御、およびセキュリティ コンテキストから呼び出し側の ID を取得する方法を示しています。次のサンプル コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd232-108">The sample demonstrates controlling authentication by using configuration and how to obtain the caller’s identity from the security context, as shown in the following sample code.</span></span>  

```csharp
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="dd232-109">サービスは、そのサービスとの通信に使用する 1 つのエンドポイントと、WS-MetadataExchange プロトコルを使用してサービスの WSDL ドキュメントを公開する 1 つのエンドポイントを公開します。これらのエンドポイントは構成ファイル (Web.config) で定義します。</span><span class="sxs-lookup"><span data-stu-id="dd232-109">The service exposes one endpoint for communicating with the service and one endpoint for exposing the service's WSDL document using the WS-MetadataExchange protocol, defined by using the configuration file (Web.config).</span></span> <span data-ttu-id="dd232-110">エンドポイントは、アドレス、バインディング、およびコントラクトがそれぞれ 1 つずつで構成されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-110">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="dd232-111">標準的なバインディングが構成されている[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)要素で、既定ではメッセージ セキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd232-111">The binding is configured with a standard [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element, which defaults to using message security.</span></span> <span data-ttu-id="dd232-112">このサンプルでは、クライアント認証が必要な証明書に `clientCredentialType` 属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="dd232-112">This sample sets the `clientCredentialType` attribute to Certificate to require client authentication.</span></span>  
  
```xml  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="dd232-113">この動作により、クライアントがサービスを認証する際に使用される、サービスの資格情報が指定されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-113">The behavior specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="dd232-114">サーバー証明書のサブジェクト名が指定された、`findValue`属性、 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)要素。</span><span class="sxs-lookup"><span data-stu-id="dd232-114">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="dd232-115">クライアント エンドポイント構成は、サービス エンドポイントの絶対アドレス、バインディング、およびコントラクトで構成されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-115">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="dd232-116">クライアント バインディングは、適切なセキュリティ モードおよび認証モードで構成されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-116">The client binding is configured with the appropriate security mode and authentication mode.</span></span> <span data-ttu-id="dd232-117">複数コンピューターのシナリオで実行する場合は、サービスのエンドポイント アドレスが適切に変更されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd232-117">When running in a cross-computer scenario, ensure that the service endpoint address is changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="dd232-118">クライアントの実装により、構成ファイルまたコードを使用して、使用する証明書が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-118">The client implementation can set the certificate to use, either through the configuration file or through code.</span></span> <span data-ttu-id="dd232-119">次のサンプルでは、使用する証明書を構成ファイルで設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dd232-119">The following sample shows how to set the certificate to use in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="dd232-120">次のサンプルでは、プログラムでサービスを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dd232-120">The following sample shows how to call the service in your program.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```
  
 <span data-ttu-id="dd232-121">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="dd232-122">クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="dd232-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="dd232-123">メッセージ セキュリティ サンプルに用意されている Setup.bat バッチ ファイルを使用すると、適切な証明書を使用してクライアントとサーバーを構成し、証明書ベースのセキュリティを必要とするホスト アプリケーションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dd232-123">The Setup.bat batch file included with the Message Security samples enables you to configure the client and server with relevant certificates to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="dd232-124">バッチ ファイルの実行には 3 つのモードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd232-124">The batch file can be run in three modes.</span></span> <span data-ttu-id="dd232-125">型の単一コンピューター モードで実行する**setup.bat** 、開発者コマンド プロンプトでサービス モードの種類は、Visual Studio のため**setup.bat service**; とクライアント モードの種類の**setup.bat client**.</span><span class="sxs-lookup"><span data-stu-id="dd232-125">To run in single-computer mode type **setup.bat** in a Developer Command Prompt for Visual Studio ; for service mode type **setup.bat service**; and for client mode type **setup.bat client**.</span></span> <span data-ttu-id="dd232-126">このサンプルを複数のコンピューターで実行している場合は、クライアントおよびサーバー モードを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd232-126">Use the client and server mode when running the sample across computers.</span></span> <span data-ttu-id="dd232-127">詳細については、このトピック末尾のセットアップ手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd232-127">See the setup procedure at the end of this topic for details.</span></span> <span data-ttu-id="dd232-128">次に、バッチ ファイルのセクションのうち、適切な構成で実行するために変更が必要となる部分を示します。</span><span class="sxs-lookup"><span data-stu-id="dd232-128">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration:</span></span>  
  
- <span data-ttu-id="dd232-129">クライアント証明書の作成。</span><span class="sxs-lookup"><span data-stu-id="dd232-129">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="dd232-130">バッチ ファイルの次の行では、クライアント証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="dd232-130">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="dd232-131">指定されたクライアント名が、作成される証明書のサブジェクト名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-131">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="dd232-132">証明書は、`My` ストアの場所の `CurrentUser` ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-132">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```bat
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
- <span data-ttu-id="dd232-133">サーバーの信頼された証明書ストアへのクライアント証明書のインストール。</span><span class="sxs-lookup"><span data-stu-id="dd232-133">Installing the client certificate into the server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="dd232-134">バッチ ファイルの次の行では、クライアント証明書をサーバーの TrustedPeople ストアにコピーし、サーバーが信頼/非信頼を判断できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dd232-134">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="dd232-135">TrustedPeople ストアにインストールされている証明書で Windows Communication Foundation (WCF) サービスから信頼されるためには、クライアントの証明書検証モードに設定する必要があります`PeerOrChainTrust`または`PeerTrust`します。</span><span class="sxs-lookup"><span data-stu-id="dd232-135">In order for a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust`.</span></span> <span data-ttu-id="dd232-136">前のサービス構成サンプルを参照して、構成ファイルを使用してこれを行う手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd232-136">See the previous service configuration sample to learn how this can be done by using a configuration file.</span></span>  
  
    ```bat
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople   
    ```  
  
- <span data-ttu-id="dd232-137">サーバー証明書の作成。</span><span class="sxs-lookup"><span data-stu-id="dd232-137">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="dd232-138">Setup.bat バッチ ファイルの次の行は、使用するサーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="dd232-138">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="dd232-139">%SERVER_NAME% 変数はサーバー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd232-139">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="dd232-140">証明書は LocalMachine ストアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-140">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="dd232-141">Setup.bat バッチ ファイルがサービスの引数で実行されているかどうか (など、 **setup.bat service**)、%server_name% には、コンピューターの完全修飾ドメイン名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd232-141">If the Setup.bat batch file is run with an argument of service (such as, **setup.bat service**) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="dd232-142">それ以外の場合、既定値は localhost です。</span><span class="sxs-lookup"><span data-stu-id="dd232-142">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="dd232-143">クライアントの信頼された証明書ストアへのサーバー証明書のインストール。</span><span class="sxs-lookup"><span data-stu-id="dd232-143">Installing the server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="dd232-144">次の行は、サーバー証明書をクライアントの信頼されたユーザーのストアにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dd232-144">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="dd232-145">この手順が必要なのは、Makecert.exe によって生成される証明書がクライアント システムにより暗黙には信頼されないからです。</span><span class="sxs-lookup"><span data-stu-id="dd232-145">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="dd232-146">マイクロソフト発行の証明書など、クライアントの信頼されたルート証明書に基づいた証明書が既にある場合は、クライアント証明書ストアにサーバー証明書を配置するこの手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="dd232-146">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="dd232-147">証明書の秘密キーに関する権限の付与。</span><span class="sxs-lookup"><span data-stu-id="dd232-147">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="dd232-148">Setup.bat ファイルの次の行は、LocalMachine ストアに保存されたサーバー証明書を [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ワーカー プロセス アカウントでアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="dd232-148">The following lines in the Setup.bat file make the server certificate stored in the LocalMachine store accessible to the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] worker process account.</span></span>  
  
    ```bat
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="dd232-149">英語 (米国) 以外の英語版の Windows を使用している場合は、Setup.bat ファイルを編集し、"NT AUTHORITY\NETWORK SERVICE" アカウント名を現在の地域に適した名前に変更してください。</span><span class="sxs-lookup"><span data-stu-id="dd232-149">If you are using a non-U.S. English edition of Windows, you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd232-150">このバッチ ファイルで使用されるツールは、C:\Program Files\Microsoft Visual Studio 8\Common7\tools または C:\Program Files\Microsoft SDKs\Windows\v6.0\bin にあります。</span><span class="sxs-lookup"><span data-stu-id="dd232-150">The tools used in this batch file are located in either C:\Program Files\Microsoft Visual Studio 8\Common7\tools or C:\Program Files\Microsoft SDKs\Windows\v6.0\bin.</span></span> <span data-ttu-id="dd232-151">これらのディレクトリのうちいずれか 1 つは、システム パスにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd232-151">One of these directories must be in your system path.</span></span> <span data-ttu-id="dd232-152">Visual Studio をインストールした場合、パスにこのディレクトリを取得する最も簡単な方法が、Visual Studio 用開発者コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="dd232-152">If you have Visual Studio installed, the easiest way to get this directory in your path is to open the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="dd232-153">クリックして**開始**、し、**すべてのプログラム**、 **Visual Studio 2012**、**ツール**します。</span><span class="sxs-lookup"><span data-stu-id="dd232-153">Click **Start**, and then select **All Programs**, **Visual Studio 2012**, **Tools**.</span></span> <span data-ttu-id="dd232-154">このコマンド プロンプトには、適切なパスが既に設定されています。</span><span class="sxs-lookup"><span data-stu-id="dd232-154">This command prompt has the appropriate paths already configured.</span></span> <span data-ttu-id="dd232-155">設定されていない場合は、適切なディレクトリをパスに手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd232-155">Otherwise you must add the appropriate directory to your path manually.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd232-156">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd232-156">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dd232-157">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd232-157">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dd232-158">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="dd232-158">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd232-159">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-159">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dd232-160">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="dd232-160">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="dd232-161">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="dd232-161">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="dd232-162">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dd232-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="dd232-163">サンプルを同じコンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="dd232-163">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="dd232-164">管理者特権で Visual Studio の開発者コマンド プロンプトを開き、サンプルのインストール フォルダーから Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="dd232-164">Open a Developer Command Prompt for Visual Studio  with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="dd232-165">これにより、サンプルの実行に必要なすべての証明書がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dd232-165">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd232-166">Setup.bat バッチ ファイルは、Visual Studio の開発者コマンド プロンプトから実行する設計されています。</span><span class="sxs-lookup"><span data-stu-id="dd232-166">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="dd232-167">path 環境変数が SDK のインストール ディレクトリを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd232-167">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="dd232-168">この環境変数は、Visual Studio (2010) の開発者コマンド プロンプトでを自動的に設定が。</span><span class="sxs-lookup"><span data-stu-id="dd232-168">This environment variable is automatically set within a Developer Command Prompt for Visual Studio (2010).</span></span>  
  
2. <span data-ttu-id="dd232-169">アドレスを入力して、ブラウザーを使用して、サービスへのアクセスを確認してください `http://localhost/servicemodelsamples/service.svc` です。</span><span class="sxs-lookup"><span data-stu-id="dd232-169">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
3. <span data-ttu-id="dd232-170">Client.exe を \client\bin で起動します。</span><span class="sxs-lookup"><span data-stu-id="dd232-170">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="dd232-171">クライアント アクティビティがクライアントのコンソール アプリケーションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd232-171">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="dd232-172">クライアントとサービスが通信できるようにされていない場合[WCF サンプルのトラブルシューティングのヒント](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="dd232-172">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="dd232-173">サンプルを複数のコンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="dd232-173">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="dd232-174">サービス コンピューターにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd232-174">Create a directory on the service computer.</span></span> <span data-ttu-id="dd232-175">インターネット インフォメーション サービス (IIS) 管理ツールを使用して、このディレクトリ用に servicemodelsamples という仮想アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd232-175">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="dd232-176">サービス プログラム ファイルを \inetpub\wwwroot\servicemodelsamples からサービス コンピューターの仮想ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dd232-176">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="dd232-177">ファイルのコピー先が \bin サブディレクトリであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dd232-177">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="dd232-178">また Setup.bat、Cleanup.bat、ImportClientCert.bat の各ファイルもサービス コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dd232-178">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="dd232-179">クライアント コンピューターにクライアント バイナリ用のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd232-179">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="dd232-180">クライアント プログラム ファイルを、クライアント コンピューターに作成したクライアント ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dd232-180">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="dd232-181">Setup.bat、Cleanup.bat、ImportServiceCert.bat の各ファイルもクライアントにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dd232-181">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="dd232-182">サーバーで実行**setup.bat service**管理者特権で Visual Studio 用開発者コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="dd232-182">On the server, run **setup.bat service** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="dd232-183">実行している**setup.bat**で、**サービス**引数が、コンピューターの完全修飾ドメイン名でサービス証明書を作成し、Service.cer というファイルに、サービス証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dd232-183">Running **setup.bat** with the **service** argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="dd232-184">新しい証明書名を反映するように Web.config を編集 (で、`findValue`属性、 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) これは、コンピューターの完全修飾ドメイン名と同じです。</span><span class="sxs-lookup"><span data-stu-id="dd232-184">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="dd232-185">Service.cer ファイルを、サービス ディレクトリからクライアント コンピューターのクライアント ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dd232-185">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="dd232-186">クライアントでは、次のように実行します。 **setup.bat client**管理者特権で Visual Studio 用開発者コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="dd232-186">On the client, run **setup.bat client** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="dd232-187">実行している**setup.bat**で、**クライアント**引数は、client.com というクライアント証明書を作成し、Client.cer というファイルに、クライアント証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dd232-187">Running **setup.bat** with the **client** argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="dd232-188">クライアント コンピューターの Client.exe.config ファイルで、エンドポイントのアドレス値をサービスの新しいアドレスに合わせます。</span><span class="sxs-lookup"><span data-stu-id="dd232-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="dd232-189">そのためには、localhost をサーバーの完全修飾ドメイン名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="dd232-189">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="dd232-190">Client.cer ファイルを、クライアント ディレクトリからサーバーのサービス ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dd232-190">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="dd232-191">クライアントでは、管理者特権で Visual Studio の ImportServiceCert.bat 開発者コマンド プロンプトでを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd232-191">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="dd232-192">これにより、サービス証明書が Service.cer ファイルから CurrentUser - TrustedPeople ストアにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="dd232-192">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="dd232-193">サーバーで、importclientcert.bat の各開発者コマンド プロンプトで Visual Studio の管理者特権で実行します。</span><span class="sxs-lookup"><span data-stu-id="dd232-193">On the server, run ImportClientCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="dd232-194">これにより、クライアント証明書が Client.cer ファイルから LocalMachine - TrustedPeople ストアにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="dd232-194">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="dd232-195">クライアント コンピューターで、コマンド プロンプト ウィンドウから Client.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="dd232-195">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="dd232-196">クライアントとサービスが通信できるようにされていない場合[WCF サンプルのトラブルシューティングのヒント](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="dd232-196">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="dd232-197">サンプルの実行後にクリーンアップするには</span><span class="sxs-lookup"><span data-stu-id="dd232-197">To clean up after the sample</span></span>  
  
- <span data-ttu-id="dd232-198">サンプルの実行が終わったら、サンプル フォルダーにある Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="dd232-198">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd232-199">このサンプルを複数のコンピューターで実行している場合、このスクリプトはサービス証明書をクライアントから削除しません。</span><span class="sxs-lookup"><span data-stu-id="dd232-199">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="dd232-200">コンピューター間で証明書を使用する Windows Communication Foundation (WCF) サンプルを実行すると、必ず、CurrentUser - TrustedPeople ストアにインストールされているサービス証明書をオフにします。</span><span class="sxs-lookup"><span data-stu-id="dd232-200">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="dd232-201">これを行うには、次のコマンドを使用します。`certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 例:`certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`します。</span><span class="sxs-lookup"><span data-stu-id="dd232-201">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
