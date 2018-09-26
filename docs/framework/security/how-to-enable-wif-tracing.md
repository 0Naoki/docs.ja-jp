---
title: '方法: WIF トレースの有効化'
ms.date: 03/30/2017
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
author: BrucePerlerMS
ms.openlocfilehash: f763c279c29bec73d4fc20d59dc86726d84e21bd
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171700"
---
# <a name="how-to-enable-wif-tracing"></a><span data-ttu-id="fb01b-102">方法: WIF トレースの有効化</span><span class="sxs-lookup"><span data-stu-id="fb01b-102">How To: Enable WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="fb01b-103">対象</span><span class="sxs-lookup"><span data-stu-id="fb01b-103">Applies To</span></span>  
  
-   <span data-ttu-id="fb01b-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="fb01b-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="fb01b-105">ASP.NET® Web フォーム</span><span class="sxs-lookup"><span data-stu-id="fb01b-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="fb01b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="fb01b-106">Summary</span></span>  
 <span data-ttu-id="fb01b-107">ここでは、ASP.NET アプリケーションの WIF トレースを有効にするための詳細な操作手順を示します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-107">This How-To provides detailed step-by-step procedures for enabling WIF tracing in an ASP.NET application.</span></span> <span data-ttu-id="fb01b-108">また、トレース リスナーとログが正しく動作していることを確認するためにアプリケーションをテストする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-108">It also provides instructions testing the application to verify that the trace listener and log are working correctly.</span></span> <span data-ttu-id="fb01b-109">ここでは、セキュリティ トークン サービス (STS) を作成するための詳細な手順については説明しません。代わりに、Identity and Access Tool に付属している開発用 STS を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="fb01b-110">開発用 STS はテスト用に用意されたもので、実際の認証は行いません。</span><span class="sxs-lookup"><span data-stu-id="fb01b-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="fb01b-111">このページの内容を完了するには、Identity and Access Tool をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb01b-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="fb01b-112">これは、「[Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="fb01b-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fb01b-113">パッシブ アプリケーション (つまり、WS フェデレーション プロトコルを使用するアプリケーション) の WIF トレースを有効にすると、アプリケーションをサービス拒否 (DoS) 攻撃に晒したり、悪意のあるユーザーに情報を開示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb01b-113">Enabling WIF tracing for passive applications, that is, applications that use the WS-Federation protocol, can potentially expose the application to denial of service (DoS) attacks or to information disclosure to a malicious party.</span></span> <span data-ttu-id="fb01b-114">これにはパッシブ RP とパッシブ STS の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fb01b-114">This includes both passive RPs and passive STSes.</span></span> <span data-ttu-id="fb01b-115">したがって、稼動環境ではパッシブ RP またはパッシブ STS の WIF トレースを有効にしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fb01b-115">For this reason, we recommend that you not enable WIF tracing for passive RPs or STSes in a production environment.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="fb01b-116">目次</span><span class="sxs-lookup"><span data-stu-id="fb01b-116">Contents</span></span>  
  
-   <span data-ttu-id="fb01b-117">目的</span><span class="sxs-lookup"><span data-stu-id="fb01b-117">Objectives</span></span>  
  
-   <span data-ttu-id="fb01b-118">概要</span><span class="sxs-lookup"><span data-stu-id="fb01b-118">Overview</span></span>  
  
-   <span data-ttu-id="fb01b-119">手順の要約</span><span class="sxs-lookup"><span data-stu-id="fb01b-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="fb01b-120">手順 1 – 簡単な ASP.NET Web フォーム アプリケーションの作成とトレースの有効化</span><span class="sxs-lookup"><span data-stu-id="fb01b-120">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="fb01b-121">手順 2 – ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="fb01b-121">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="fb01b-122">目的</span><span class="sxs-lookup"><span data-stu-id="fb01b-122">Objectives</span></span>  
  
-   <span data-ttu-id="fb01b-123">Identity and Access Tool の WIF および開発用 STS を使用する簡単な ASP.NET アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="fb01b-123">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="fb01b-124">トレースの有効化と動作確認</span><span class="sxs-lookup"><span data-stu-id="fb01b-124">Enable tracing and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="fb01b-125">概要</span><span class="sxs-lookup"><span data-stu-id="fb01b-125">Overview</span></span>  
 <span data-ttu-id="fb01b-126">トレースすると、トークン、クッキー、クレーム、プロトコル メッセージなどを含む、さまざまな種類の WIF の問題をデバッグおよびトラブルシューティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb01b-126">Tracing enables you to debug and troubleshoot many types of issues with WIF, including tokens, cookies, claims, protocol messages, and more.</span></span> <span data-ttu-id="fb01b-127">WIF トレースは、WCF トレースに似ています。たとえば、トレースの詳細レベルを選択して、警告メッセージから全メッセージまで、すべてを表示させることができます。</span><span class="sxs-lookup"><span data-stu-id="fb01b-127">WIF tracing is similar to WCF tracing; for example, you can choose the verbosity of traces to display everything from critical messages to all messages.</span></span> <span data-ttu-id="fb01b-128">WIF トレースは、**.xml** ファイル、またはサービス トレース ビューアー ツールを使用して表示できる **.svclog** ファイルで生成できます。</span><span class="sxs-lookup"><span data-stu-id="fb01b-128">WIF traces can be generated in **.xml** files or in **.svclog** files that are viewable by using the Service Trace Viewer Tool.</span></span> <span data-ttu-id="fb01b-129">このツールは、コンピューターの Windows SDK インストール パスの **bin** ディレクトリにあります (例: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**)。</span><span class="sxs-lookup"><span data-stu-id="fb01b-129">This tool is located in the **bin** directory of the Windows SDK install path on your computer, for example: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="fb01b-130">手順の要約</span><span class="sxs-lookup"><span data-stu-id="fb01b-130">Summary of Steps</span></span>  
  
-   <span data-ttu-id="fb01b-131">手順 1 – 簡単な ASP.NET Web フォーム アプリケーションの作成とトレースの有効化</span><span class="sxs-lookup"><span data-stu-id="fb01b-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="fb01b-132">手順 2 – ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="fb01b-132">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a><span data-ttu-id="fb01b-133">手順 1 – 簡単な ASP.NET Web フォーム アプリケーションの作成とトレースの有効化</span><span class="sxs-lookup"><span data-stu-id="fb01b-133">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
 <span data-ttu-id="fb01b-134">この手順では、新しい ASP.NET Web フォーム アプリケーションを作成し、トレースを有効にするために *Web.config* ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-134">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable tracing.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="fb01b-135">簡単な ASP.NET アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="fb01b-135">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="fb01b-136">Visual Studio を起動し、**[ファイル]**、**[新規作成]**、**[プロジェクト]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb01b-136">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="fb01b-137">**[新しいプロジェクト]** ウィンドウで、**[ASP.NET Web フォーム アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb01b-137">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="fb01b-138">**[名前]** で、「`TestApp`」と入力し、**[OK]** を押します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-138">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="fb01b-139">**ソリューション エクスプローラー**で **[TestApp]** プロジェクトを右クリックし、**[Identity and Access]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-139">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5.  <span data-ttu-id="fb01b-140">**[Identity and Access]** ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb01b-140">The **Identity and Access** window appears.</span></span> <span data-ttu-id="fb01b-141">**[Providers]** で **[Test your application with the Local Development STS]** を選択し、**[Apply]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb01b-141">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6.  <span data-ttu-id="fb01b-142">表示されている例 (**C:\logs**) のように、**C:** ドライブのルートに **logs** という名前の新しいフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-142">Create a new folder in named **logs** in the root of the **C:** drive, like shown: **C:\logs**</span></span>  
  
7.  <span data-ttu-id="fb01b-143">表示されている例のように、終了要素 **\</configSections>** の直後に、以下の **\<system.diagnostics>** 要素を *Web.config* 構成ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-143">Add the following **\<system.diagnostics>** element to the *Web.config* configuration file immediately following the closing **\</configSections>** element, like shown:</span></span>  
  
    ```xml  
    <configuration>  
        <configSections>  
        …  
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fb01b-144">**initializeData** 属性で指定されたディレクトリの場所は、ログが開始される前に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb01b-144">The directory location specified in the **initializeData** attribute must exist before logging can begin.</span></span> <span data-ttu-id="fb01b-145">この場所が存在しない場合、ログは作成されません。</span><span class="sxs-lookup"><span data-stu-id="fb01b-145">If the location does not exist, no logs will be created.</span></span>  
  
     <span data-ttu-id="fb01b-146">上記の構成設定では、**詳細**な WIF トレースが有効になり、**C:logsWIF.xml** ファイルに結果のログが保存されます。</span><span class="sxs-lookup"><span data-stu-id="fb01b-146">The configuration settings above will enable **Verbose** tracing for WIF and save the resulting log to the **C:logsWIF.xml** file.</span></span>  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="fb01b-147">手順 2 – ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="fb01b-147">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="fb01b-148">この手順では、WIF 対応 ASP.NET アプリケーションをテストし、ログが記録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-148">In this step, you will test your WIF-enabled ASP.NET application to verify that logs are being recorded.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a><span data-ttu-id="fb01b-149">正常なトレースのために WIF 対応 ASP.NET アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="fb01b-149">To test your WIF-enabled ASP.NET application for successful tracing</span></span>  
  
1.  <span data-ttu-id="fb01b-150">**F5** キーを押して、ソリューションを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-150">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="fb01b-151">既定の ASP.NET ホーム ページが開き、ユーザー名 *Terry* (開発用 STS によって返される既定のユーザー) で自動的に認証されます。</span><span class="sxs-lookup"><span data-stu-id="fb01b-151">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2.  <span data-ttu-id="fb01b-152">ブラウザー ウィンドウを閉じ、**C:\logs** フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-152">Close the browser window and then navigate to the **C:\logs** folder.</span></span> <span data-ttu-id="fb01b-153">テキスト エディターを使用して **C:\logs\WIF.xml** ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb01b-153">Open the **C:\logs\WIF.xml** file using a text editor.</span></span>  
  
3.  <span data-ttu-id="fb01b-154">**WIF.xml** ファイルを調べ、**\<E2ETraceEvent>** で始まるエントリが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb01b-154">Inspect the **WIF.xml** file and verify that it contains entries starting with **\<E2ETraceEvent>**.</span></span> <span data-ttu-id="fb01b-155">これらのトレースには、**\<TraceRecord>** 要素と、トレースされるアクティビティ (**Validating SecurityToken** など) の説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fb01b-155">These traces will contain **\<TraceRecord>** elements with descriptions for the traced activity, such as **Validating SecurityToken**.</span></span>
