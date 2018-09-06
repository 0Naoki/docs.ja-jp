---
title: .NET Framework クライアント アプリケーションの作成 (WCF Data Services クイック スタート)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 86ded7351d435b3a7077f0354d8a923b33a3f2b6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43854958"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a><span data-ttu-id="c5cc9-102">.NET Framework クライアント アプリケーションの作成 (WCF Data Services クイック スタート)</span><span class="sxs-lookup"><span data-stu-id="c5cc9-102">Creating the .NET Framework Client Application (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="c5cc9-103">これは、WCF Data Services クイック スタートの最後のタスクです。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-103">This is the final task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="c5cc9-104">このタスクでは、ソリューションにコンソール アプリケーションを追加への参照を追加、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]この新しいクライアント アプリケーションにフィードおよびフィードの生成されたクライアント データ サービス クラスおよびクライアント ライブラリを使用して、クライアント アプリケーションから OData へのアクセス.</span><span class="sxs-lookup"><span data-stu-id="c5cc9-104">In this task, you will add a console application to the solution, add a reference to the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed into this new client application, and access the OData feed from the client application by using the generated client data service classes and client libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="c5cc9-105">データ フィードへのアクセスには .NET Framework ベースのクライアント アプリケーションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-105">A .NET Framework-based client application is not required to access a data feed.</span></span> <span data-ttu-id="c5cc9-106">データ サービスは、OData フィードを使用する任意のアプリケーション コンポーネントによってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-106">The data service can be accessed by any application component that consumes an OData feed.</span></span> <span data-ttu-id="c5cc9-107">詳細については、次を参照してください。[クライアント アプリケーションでデータ サービスを使用して](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-107">For more information, see [Using a Data Service in a Client Application](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>

## <a name="to-create-the-client-application-by-using-visual-studio"></a><span data-ttu-id="c5cc9-108">Visual Studio を使用してクライアント アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="c5cc9-108">To create the client application by using Visual Studio</span></span>

1.  <span data-ttu-id="c5cc9-109">**ソリューション エクスプ ローラー**は、ソリューションを右クリックし、[**追加**、] をクリックし、**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-109">In **Solution Explorer**, right-click the solution, click **Add**, and then click **New Project**.</span></span>

2.  <span data-ttu-id="c5cc9-110">左側のウィンドウで次のように選択します**インストール済み**> [**Visual c#** または**Visual Basic**] > **Windows デスクトップ**、を選び、 **。WPF アプリ**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-110">In the left pane, select **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, and then select the **WPF App** template.</span></span>

3.  <span data-ttu-id="c5cc9-111">入力`NorthwindClient`プロジェクト名、およびクリックの**OK**。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-111">Enter `NorthwindClient` for the project name, and then click **OK**.</span></span>

4.  <span data-ttu-id="c5cc9-112">ファイル MainWindow.xaml を開き、XAML コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-112">Open the file MainWindow.xaml and replace the XAML code with the following code:</span></span>

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a><span data-ttu-id="c5cc9-113">データ サービス参照をプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="c5cc9-113">To add a data service reference to the project</span></span>

1.  <span data-ttu-id="c5cc9-114">**ソリューション エクスプ ローラー**NorthwindClient プロジェクトを右クリックをクリックし、**追加** > **サービス参照の**、 をクリックし、**検出**.</span><span class="sxs-lookup"><span data-stu-id="c5cc9-114">In **Solution Explorer**, right-click the NorthwindClient project, click **Add** > **Service Reference**, and then click **Discover**.</span></span>

     <span data-ttu-id="c5cc9-115">最初のタスクで作成した Northwind データ サービスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-115">This displays the Northwind data service that you created in the first task.</span></span>

2.  <span data-ttu-id="c5cc9-116">**Namespace**テキスト ボックスに「 `Northwind`、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-116">In the **Namespace** text box, type `Northwind`, and then click **OK**.</span></span>

     <span data-ttu-id="c5cc9-117">プロジェクトに新しいコード ファイルが追加されます。このコード ファイルには、データ サービス リソースにアクセスし、オブジェクトとしてデータ サービス リソースと対話するデータ クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-117">This adds a new code file to the project, which contains the data classes that are used to access and interact with data service resources as objects.</span></span> <span data-ttu-id="c5cc9-118">データ クラスは、名前空間 `NorthwindClient.Northwind` で作成されます。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-118">The data classes are created in the namespace `NorthwindClient.Northwind`.</span></span>

## <a name="to-access-data-service-data-in-the-wpf-application"></a><span data-ttu-id="c5cc9-119">WPF アプリケーションのデータ サービスにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="c5cc9-119">To access data service data in the WPF application</span></span>

1.  <span data-ttu-id="c5cc9-120">**ソリューション エクスプ ローラー**  **NorthwindClient**プロジェクトを右クリックし、クリックして、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-120">In **Solution Explorer** under **NorthwindClient**, right-click the project and click **Add Reference**.</span></span>

2.  <span data-ttu-id="c5cc9-121">**参照の追加**ダイアログ ボックスで、をクリックして、 **.NET**  タブで、System.Data.Services.Client.dll アセンブリを選択し、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-121">In the **Add Reference** dialog box, click the **.NET** tab, select the System.Data.Services.Client.dll assembly, and then click **OK**.</span></span>

3. <span data-ttu-id="c5cc9-122">**ソリューション エクスプ ローラー**  **NorthwindClient**、MainWindow.xaml ファイルのコード ページを開き、次の追加`using`ステートメント (`Imports` Visual Basic で)。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-122">In **Solution Explorer** under **NorthwindClient**, open the code page for the MainWindow.xaml file, and add the following `using` statement (`Imports` in Visual Basic).</span></span>

     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]

3.  <span data-ttu-id="c5cc9-123">次のコードを挿入します。このコードは、データ サービスをクエリし、<xref:System.Data.Services.Client.DataServiceCollection%601> に対する結果を `MainWindow` クラスにバインドします。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-123">Insert the following code that queries that data service and binds the result to a <xref:System.Data.Services.Client.DataServiceCollection%601> into the `MainWindow` class:</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5cc9-124">ホスト名 `localhost:12345` を Northwind データ サービスのインスタンスをホストするサーバーとポートで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-124">You must replace the host name `localhost:12345` with the server and port that is hosting your instance of the Northwind data service.</span></span>

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]

4.  <span data-ttu-id="c5cc9-125">次のコードを挿入します。このコードは、変更内容を `MainWindow` クラスに保存します。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-125">Insert the following code that saves changes into the `MainWindow` class:</span></span>

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a><span data-ttu-id="c5cc9-126">NorthwindClient アプリケーションをビルドして実行するには</span><span class="sxs-lookup"><span data-stu-id="c5cc9-126">To build and run the NorthwindClient application</span></span>

1.  <span data-ttu-id="c5cc9-127">**ソリューション エクスプ ローラー**NorthwindClient プロジェクトを右クリックし、選択、**スタートアップ プロジェクトとして設定**します。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-127">In **Solution Explorer**, right-click the NorthwindClient project and select **Set as startup project**.</span></span>

2.  <span data-ttu-id="c5cc9-128">キーを押して**F5**アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-128">Press **F5** to start the application.</span></span>

     <span data-ttu-id="c5cc9-129">ソリューションがビルドされ、クライアント アプリケーションが起動します。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-129">This builds the solution and starts the client application.</span></span> <span data-ttu-id="c5cc9-130">データがサービスから要求され、コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-130">Data is requested from the service and displayed in the console.</span></span>

3.  <span data-ttu-id="c5cc9-131">値を編集、**数量**列のデータ グリッド、およびクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-131">Edit a value in the **Quantity** column of the data grid, and then click **Save**.</span></span>

     <span data-ttu-id="c5cc9-132">変更内容はデータ サービスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-132">Changes are saved to the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5cc9-133">このバージョンの NorthwindClient アプリケーションでは、エンティティの追加と削除はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-133">This version of the NorthwindClient application does not support adding and deleting of entities.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c5cc9-134">次の手順</span><span class="sxs-lookup"><span data-stu-id="c5cc9-134">Next Steps</span></span>

<span data-ttu-id="c5cc9-135">サンプルの Northwind OData フィードにアクセスするクライアント アプリケーションが正常に作成しました。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-135">You have successfully created the client application that accesses the sample Northwind OData feed.</span></span> <span data-ttu-id="c5cc9-136">WCF Data Services クイック スタートも完了しました。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-136">You've also completed the WCF Data Services quickstart!</span></span>

<span data-ttu-id="c5cc9-137">OData へのアクセスの詳細についてはフィードから、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]アプリケーションを参照してください[WCF Data Services クライアント ライブラリ](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)します。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-137">For more information about accessing an OData feed from a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application, see [WCF Data Services Client Library](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c5cc9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5cc9-138">See Also</span></span>

- [<span data-ttu-id="c5cc9-139">はじめに</span><span class="sxs-lookup"><span data-stu-id="c5cc9-139">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="c5cc9-140">リソース</span><span class="sxs-lookup"><span data-stu-id="c5cc9-140">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
