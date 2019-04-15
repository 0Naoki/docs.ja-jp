---
title: '方法: IIS 上で実行する WCF Data Service を開発する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: 78e8c3cacd89f88cbfa062cb30e5b3474c2614ca
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517839"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="9b686-102">方法: IIS で実行されている WCF データ サービスを開発します。</span><span class="sxs-lookup"><span data-stu-id="9b686-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="9b686-103">このトピックでは、WCF Data Services を使用して、インターネット インフォメーション サービス (IIS) を実行している ASP.NET Web アプリケーションによってホストされる Northwind サンプル データベースに基づくデータ サービスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9b686-103">This topic shows how to use WCF Data Services to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="9b686-104">ASP.NET 開発サーバーで実行されている ASP.NET Web アプリケーションとして同じ Northwind データ サービスを作成する方法の例は、次を参照してください。、 [WCF Data Services クイック スタート](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b686-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9b686-105">Northwind データ サービスを作成するには、ローカル コンピューターに Northwind サンプル データベースをインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b686-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="9b686-106">このサンプル データベースをダウンロードするには、ダウンロード ページ「 [SQL Server 用サンプル データベース](https://go.microsoft.com/fwlink/?linkid=24758)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b686-106">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

 <span data-ttu-id="9b686-107">このトピックでは、Entity Framework プロバイダーを使用してデータ サービスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9b686-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="9b686-108">その他のデータ サービス プロバイダーを利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9b686-108">Other data services providers are available.</span></span> <span data-ttu-id="9b686-109">詳細については、次を参照してください。[データ サービス プロバイダー](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b686-109">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>

 <span data-ttu-id="9b686-110">サービスを作成した後に、データ サービス リソースへのアクセスを明示的に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b686-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="9b686-111">詳細については、「[方法 :データ サービスへのアクセスを有効にする](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b686-111">For more information, see [How to: Enable Access to the Data Service](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="9b686-112">IIS で実行されている ASP.NET web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b686-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="9b686-113">Visual Studio での**ファイル**メニューの **新規** > **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="9b686-114">**新しいプロジェクト**ダイアログ ボックスで、**インストール済み**> [**Visual C#** または**Visual Basic**] > **Web**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="9b686-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="9b686-115">選択、 **ASP.NET Web アプリケーション**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="9b686-115">Select the **ASP.NET Web Application** template.</span></span>

1. <span data-ttu-id="9b686-116">入力`NorthwindService`としてプロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="9b686-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="9b686-117">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b686-117">Click **OK**.</span></span>

6. <span data-ttu-id="9b686-118">**プロジェクト**メニューの  **NorthwindService プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="9b686-119">選択、 **Web** 、タブを選び**ローカル IIS Web サーバーを使用**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="9b686-120">クリックして**仮想ディレクトリの作成**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="9b686-121">管理特権を持つコマンド プロンプトから、次のコマンドを実行します (オペレーティング システムによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="9b686-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    -   <span data-ttu-id="9b686-122">32 ビット システム: </span><span class="sxs-lookup"><span data-stu-id="9b686-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    -   <span data-ttu-id="9b686-123">64 ビット システム: </span><span class="sxs-lookup"><span data-stu-id="9b686-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="9b686-124">これにより、コンピューターに Windows Communication Foundation (WCF) が登録されます。</span><span class="sxs-lookup"><span data-stu-id="9b686-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="9b686-125">管理特権を持つコマンド プロンプトから、次のコマンドを実行します (オペレーティング システムによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="9b686-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    -   <span data-ttu-id="9b686-126">32 ビット システム: </span><span class="sxs-lookup"><span data-stu-id="9b686-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    -   <span data-ttu-id="9b686-127">64 ビット システム: </span><span class="sxs-lookup"><span data-stu-id="9b686-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="9b686-128">これにより、WCF がコンピューターにインストールされた後、IIS は正常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="9b686-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="9b686-129">IIS の再起動が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9b686-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="9b686-130">ASP.NET アプリケーションが IIS7 で実行されると、次の手順も実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b686-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="9b686-131">IIS マネージャーを開き、下にある PhotoService アプリケーションに移動します**既定の Web サイト**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="9b686-132">**機能ビュー**、ダブルクリックして**認証**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="9b686-133">**認証**] ページで、[**匿名認証**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="9b686-134">**アクション**ウィンドウで、をクリックして**編集**を設定するセキュリティ プリンシパルを匿名ユーザー で、サイトに接続します。</span><span class="sxs-lookup"><span data-stu-id="9b686-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="9b686-135">**匿名認証資格情報の編集**ダイアログ ボックスで、**アプリケーション プール id**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9b686-136">ネットワーク サービス アカウントを使用する際、そのアカウントに関連するすべての内部ネットワーク アクセス権を匿名ユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="9b686-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="9b686-137">SQL Server Management Studio、sqlcmd.exe ユーティリティ、または Visual Studio の Transact-SQL エディターを使用して、Northwind データベースがアタッチされた SQL Server のインスタンスに対して次の Transact-SQL コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b686-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="9b686-138">これにより、IIS の実行に使用される Windows アカウントに対して、SQL Server インスタンスのログインが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9b686-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="9b686-139">IIS は、これを使用して SQL Server インスタンスに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9b686-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="9b686-140">Northwind データベースをアタッチして、次の Transact-SQL コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b686-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    <span data-ttu-id="9b686-141">これにより、新しいログインに権限が付与され、IIS は Northwind データベースに対してデータの読み取りおよび書き込みを行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="9b686-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="9b686-142">データ モデルを定義する</span><span class="sxs-lookup"><span data-stu-id="9b686-142">Define the data model</span></span>

1. <span data-ttu-id="9b686-143">**ソリューション エクスプ ローラー**ASP.NET プロジェクトの名前を右クリックし、クリックして**追加** > **新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="9b686-144">**新しい項目の追加**ダイアログ ボックスで、 **ADO.NET Entity Data Model**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="9b686-145">データ モデルの名前を入力`Northwind.edmx`します。</span><span class="sxs-lookup"><span data-stu-id="9b686-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="9b686-146">Entity Data Model ウィザード、選択**データベースから生成**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="9b686-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="9b686-147">次の手順のいずれかの手順を実行して、データ モデルをデータベースに接続し、**次**:</span><span class="sxs-lookup"><span data-stu-id="9b686-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    -   <span data-ttu-id="9b686-148">データベース接続が既に構成されていない場合は、クリックして**新しい接続**し、新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="9b686-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="9b686-149">詳細については、「[方法 :SQL Server データベースへの接続を作成する](https://go.microsoft.com/fwlink/?LinkId=123631)します。</span><span class="sxs-lookup"><span data-stu-id="9b686-149">For more information, see [How to: Create Connections to SQL Server Databases](https://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="9b686-150">この SQL Server インスタンスには、Northwind サンプル データベースがアタッチされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b686-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="9b686-151">\- または -</span><span class="sxs-lookup"><span data-stu-id="9b686-151">\- or -</span></span>

    -   <span data-ttu-id="9b686-152">Northwind データベースに接続するようにデータベース接続が既に構成されている場合は、一覧からその接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b686-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="9b686-153">ウィザードの最終ページで、データベース内のすべてのテーブルのチェック ボックスをオンにし、ビューおよびストアド プロシージャのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9b686-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="9b686-154">クリックして**完了**ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9b686-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="9b686-155">データ サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="9b686-155">Create the data service</span></span>

1. <span data-ttu-id="9b686-156">**ソリューション エクスプ ローラー**、ASP.NET プロジェクトの名前を右クリックし、クリックして**追加** > **新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="9b686-157">**新しい項目の追加**ダイアログ ボックスで、 **WCF Data Service**します。</span><span class="sxs-lookup"><span data-stu-id="9b686-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![Visual Studio 2015 での WCF データ サービス項目テンプレート](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="9b686-159">**WCF Data Service**テンプレートは、Visual Studio 2015 ではなく Visual Studio 2017 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b686-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="9b686-160">サービスの名前を入力`Northwind`します。</span><span class="sxs-lookup"><span data-stu-id="9b686-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="9b686-161">Visual Studio で新しいサービスの XML マークアップおよびコード ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9b686-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="9b686-162">既定では、コード エディターのウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="9b686-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="9b686-163">**ソリューション エクスプ ローラー**サービスが、名前、Northwind、および拡張機能。 は.svc.cs または.svc.vb になります。</span><span class="sxs-lookup"><span data-stu-id="9b686-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="9b686-164">データ サービスのコードで、データ サービスを定義するクラスの定義にあるコメント `/* TODO: put your data source class name here */` をデータ モデルのエンティティ コンテナーである型 (この場合は `NorthwindEntities`) で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9b686-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="9b686-165">クラス定義は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9b686-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="9b686-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b686-166">See also</span></span>

- [<span data-ttu-id="9b686-167">サービスとしてのデータの公開</span><span class="sxs-lookup"><span data-stu-id="9b686-167">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
