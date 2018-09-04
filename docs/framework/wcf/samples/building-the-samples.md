---
title: Windows Communication Foundation サンプルのビルド
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: 46f4015c00916a5cab932e8fd2539c7c86588a30
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43565787"
---
# <a name="building-the-windows-communication-foundation-samples"></a><span data-ttu-id="e2a8a-102">Windows Communication Foundation サンプルのビルド</span><span class="sxs-lookup"><span data-stu-id="e2a8a-102">Building the Windows Communication Foundation Samples</span></span>

<span data-ttu-id="e2a8a-103">Visual Studio IDE を使用してまたはを使用して、Windows Communication Foundation (WCF) サンプルを構築できる、 **msbuild**コマンドラインからコマンド。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-103">The Windows Communication Foundation (WCF) samples can be built using the Visual Studio IDE or using the **msbuild** command from the command line.</span></span> <span data-ttu-id="e2a8a-104">ここでは、両方の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-104">Both procedures are described in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="e2a8a-105">構築しても、WCF サンプルのいずれかを実行する前に実行済みであることを確認します、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-105">Before building or running any of the WCF samples, ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

## <a name="to-build-the-sample-using-a-command-prompt"></a><span data-ttu-id="e2a8a-106">コマンド プロンプトを使用してサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="e2a8a-106">To build the sample using a command prompt</span></span>

1.  <span data-ttu-id="e2a8a-107">Visual Studio 用開発者コマンド プロンプトを開きし、サンプルがインストールされているディレクトリの場所の言語固有のサブディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-107">Open Developer Command Prompt for Visual Studio and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>

2.  <span data-ttu-id="e2a8a-108">型`msbuild`コマンドライン。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-108">Type `msbuild` at the command line.</span></span> <span data-ttu-id="e2a8a-109">クライアントのプログラム ファイルが組み込まれて*client \bin*に構築された、サービス プログラム ファイルと*service \bin*します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-109">The client program files are built to *client\bin* and the service program files are built to *service\bin*.</span></span> <span data-ttu-id="e2a8a-110">サービス プログラム ファイルもにコピーする場合は、サービスは、インターネット インフォメーション サービス (IIS) によってホストされている、 *servicemodelsamples*ディレクトリとその*\bin*サブディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-110">If the service is hosted by Internet Information Services (IIS), the service program files are also copied to the *servicemodelsamples* directory and its *\bin* subdirectory.</span></span>

> [!NOTE]
> <span data-ttu-id="e2a8a-111">Acl を設定する必要があります *%systemdrive%\inetpub\wwwroot*を付与するを実行しているアカウントにアクセス許可を変更します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-111">You must set the ACLs on *%systemdrive%\inetpub\wwwroot* to grant modify permissions to the account under which you are running.</span></span> <span data-ttu-id="e2a8a-112">このように設定しない場合、ビルド後のイベントが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-112">Otherwise some post build events fail.</span></span> <span data-ttu-id="e2a8a-113">代わりに、ACL の設定はそのままにして、SDK コマンド プロンプトを管理者として実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-113">Alternatively, you can leave the ACLs as they are and run the SDK command prompt as administrator.</span></span>

## <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="e2a8a-114">Visual Studio を使用してサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="e2a8a-114">To build the sample using Visual Studio</span></span>

1. <span data-ttu-id="e2a8a-115">**ファイル** メニューの選択 Visual Studio で**オープン** > **プロジェクト/ソリューション**します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-115">From the **File** menu in Visual Studio, select **Open** > **Project/Solution**.</span></span> <span data-ttu-id="e2a8a-116">サンプルをインストールしたディレクトリの言語固有のサブディレクトリに移動し、Visual Studio でソリューションを開く .sln ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-116">Navigate to the language-specific subdirectory under the directory in which you installed the sample, and double-click the .sln file icon to open the solution in Visual Studio.</span></span>

1. <span data-ttu-id="e2a8a-117">**ビルド**メニューの **ソリューションのリビルド**します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-117">From the **Build** menu, select **Rebuild Solution**.</span></span>

   <span data-ttu-id="e2a8a-118">クライアント プログラムが client\bin にビルドされ、サービス プログラムが service\bin にビルドされます。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-118">The client program files are built to client\bin and the service program files are built to service\bin.</span></span> <span data-ttu-id="e2a8a-119">サービス プログラム ファイルもにコピーする場合は、サービスは IIS でホストされる、 *servicemodelsamples*ディレクトリとその*\bin*サブディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-119">If the service is hosted in IIS, the service program files are also copied to the *servicemodelsamples* directory and its *\bin* subdirectory.</span></span>

> [!NOTE]
> <span data-ttu-id="e2a8a-120">%systemdrive%\inetpub\wwwroot 上の ACL を、実行中のアカウントに変更権限を付与するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-120">You must set the ACLs on %systemdrive%\inetpub\wwwroot to grant modify permissions to the account under which you are running.</span></span> <span data-ttu-id="e2a8a-121">このように設定しない場合、ビルド後のイベントが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-121">Otherwise some post build events fail.</span></span> <span data-ttu-id="e2a8a-122">代わりに、ACL の設定はそのままにして、SDK コマンド プロンプトまたは Visual Studio を管理者として実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-122">Alternatively, you can leave the ACLs as they are and run the SDK command prompt or Visual Studio as administrator.</span></span> <span data-ttu-id="e2a8a-123">Visual Studio の一部のアクション (デバッガを ASP.Net ワーカー プロセスにアタッチするアクションなど) では、さらに管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-123">Some Visual Studio actions (such as attaching a debugger to the ASP.Net worker process) also require administrative privileges.</span></span>

## <a name="setup-batch-files-and-scripts"></a><span data-ttu-id="e2a8a-124">セットアップ バッチ ファイルとスクリプト</span><span class="sxs-lookup"><span data-stu-id="e2a8a-124">Setup Batch Files and Scripts</span></span>
 <span data-ttu-id="e2a8a-125">Setup.exe、Cleanup.exe バッチ ファイルやスクリプトする必要がありますと、開発者コマンド プロンプトからが for Visual Studio を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-125">Setup.exe and Cleanup.exe batch files and scripts should be run from Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="e2a8a-126">いくつかのセットアップ ファイルとクリーンアップ ファイルは、管理特権が必要なタスクを実行します。したがって、これらのファイルは管理特権で起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-126">Several set up and clean up files perform tasks that require administrative privileges and should be launched with administrator privileges.</span></span>

## <a name="important-security-information-about-metadata-endpoints"></a><span data-ttu-id="e2a8a-127">メタデータ エンドポイントに関する重要なセキュリティ情報</span><span class="sxs-lookup"><span data-stu-id="e2a8a-127">Important Security Information about Metadata Endpoints</span></span>
 <span data-ttu-id="e2a8a-128">可能性のある機密性の高いサービス メタデータが誤って漏洩を防ぐためには、Windows Communication Foundation (WCF) サービスの既定の構成ではメタデータの公開を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-128">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="e2a8a-129">この動作は、既定の設定ではセキュリティで保護されますが、同時に、サービスの構成の中でメタデータ発行の動作が明示的に有効化されない限り、サービスの呼び出しに必要なクライアント コードをメタデータ インポート ツール (Svcutil.exe など) を使用して生成できないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-129">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="e2a8a-130">サンプルでの試みを容易にするため、ほとんどすべてのサンプルでは、セキュリティ保護されていないメタデータ公開エンドポイントを公開しています。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-130">To make experimenting with the samples easier, almost all samples expose an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="e2a8a-131">このようなエンドポイントを利用するコンシューマーは、匿名で、認証を受けていない可能性もあります。したがって、エンドポイントを配置する前には注意を払い、サービスのメタデータをパブリックに開示することが適切であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-131">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> <span data-ttu-id="e2a8a-132">サービス メタデータの公開の詳細については、次を参照してください。、[メタデータ公開動作](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-132">For more information about publishing service metadata, see the [Metadata Publishing Behavior](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md) sample.</span></span> <span data-ttu-id="e2a8a-133">参照してください、[メタデータ エンドポイントのセキュリティで保護されたカスタム](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)メタデータ エンドポイントをセキュリティで保護するサンプルのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-133">See the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample for a sample securing a metadata endpoint.</span></span>

## <a name="exception-handling"></a><span data-ttu-id="e2a8a-134">例外処理</span><span class="sxs-lookup"><span data-stu-id="e2a8a-134">Exception Handling</span></span>
 <span data-ttu-id="e2a8a-135">通常、コードではサンプルの主題を重視するので、これらのサンプルに例外処理は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-135">Generally speaking these samples do not include exception handling to keep the code focused on the subject of the sample.</span></span> <span data-ttu-id="e2a8a-136">例外処理の詳細については、次を参照してください。、[予想例外](../../../../docs/framework/wcf/samples/expected-exceptions.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-136">For more information about exception handling, see the [Expected Exceptions](../../../../docs/framework/wcf/samples/expected-exceptions.md) sample.</span></span>

## <a name="regenerating-clients-and-configuration-with-svcutil"></a><span data-ttu-id="e2a8a-137">Svcutil を使用したクライアントと構成の再生成</span><span class="sxs-lookup"><span data-stu-id="e2a8a-137">Regenerating Clients and Configuration with Svcutil</span></span>
 <span data-ttu-id="e2a8a-138">使用することができます、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)をクライアント コードとほとんどのサンプルの構成を再生成します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-138">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to regenerate client code and configuration for most of the samples.</span></span> <span data-ttu-id="e2a8a-139">一部のサンプルでは、構成を手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-139">Some samples require manually edited configuration.</span></span> <span data-ttu-id="e2a8a-140">たとえば、Svcutil.exe を使用して、クライアント証明書の資格情報を使用するサンプルの構成を再生成する場合は、以前に構成された資格情報を手動で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-140">For example, if you use Svcutil.exe to regenerate the configuration for a sample that uses client certificate credentials, you must manually specify the credentials previously configured.</span></span> <span data-ttu-id="e2a8a-141">一部のサンプルでは、生成コードに影響を与える、Svcutil.exe の特定のオプションを使用します。これらのオプションは、そうした特定のサンプルのトピックで指定されます。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-141">Some samples use specific Svcutil.exe options to affect the generated code, these options are specified in the specific sample topics.</span></span>

### <a name="to-regenerate-the-client-and-configuration-files"></a><span data-ttu-id="e2a8a-142">クライアントと構成ファイルを再生成するには</span><span class="sxs-lookup"><span data-stu-id="e2a8a-142">To regenerate the client and configuration files</span></span>

1.  <span data-ttu-id="e2a8a-143">SDK コマンド プロンプトを開き、サンプルのインストール ディレクトリに存在する言語固有のサブディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-143">Open an SDK command prompt and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>

2.  <span data-ttu-id="e2a8a-144">サービスが Web ホスト型の場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-144">If the service is a Web-hosted type, use the following command.</span></span>

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     <span data-ttu-id="e2a8a-145">サービスが自己ホスト型の場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-145">If the service is a self-hosted type the following command.</span></span>

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     <span data-ttu-id="e2a8a-146">置換 http://localhost:8000/ServiceModelSamples/service.svc/mex自己ホスト型サービスの mex エンドポイントのアドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-146">Replace http://localhost:8000/ServiceModelSamples/service.svc/mex with the address of the self-hosted service's mex endpoint.</span></span>

     <span data-ttu-id="e2a8a-147">Visual Basic の型でクライアントを生成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-147">To generate the client in a Visual Basic type, use the following command.</span></span>

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

     <span data-ttu-id="e2a8a-148">サービスが自己ホスト型の場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-148">If the service is a self-hosted type, use the following command.</span></span>

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

    > [!NOTE]
    > <span data-ttu-id="e2a8a-149">クライアント構成の生成の追加をスキップする、 **/noConfig**オプション。</span><span class="sxs-lookup"><span data-stu-id="e2a8a-149">To skip the generation of client configuration add the **/noConfig** option.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2a8a-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2a8a-150">See Also</span></span>

- [<span data-ttu-id="e2a8a-151">Windows Communication Foundation サンプルの実行</span><span class="sxs-lookup"><span data-stu-id="e2a8a-151">Running the Windows Communication Foundation Samples</span></span>](../../../../docs/framework/wcf/samples/running-the-samples.md)
- [<span data-ttu-id="e2a8a-152">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="e2a8a-152">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
