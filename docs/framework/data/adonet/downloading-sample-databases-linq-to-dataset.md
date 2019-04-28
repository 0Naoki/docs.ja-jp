---
title: サンプル データベースのダウンロード (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: 1ef5a5ceac6a7f819551f6221b63197786ab4f09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606887"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a><span data-ttu-id="baa25-102">サンプル データベースのダウンロード (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="baa25-102">Downloading Sample Databases (LINQ to DataSet)</span></span>
<span data-ttu-id="baa25-103">サンプルおよびチュートリアルで、[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]ドキュメントは、AdventureWorks サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="baa25-103">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use the AdventureWorks sample database.</span></span> <span data-ttu-id="baa25-104">この製品は、Microsoft のダウンロード サイトから無償でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="baa25-104">You can download this product free of charge from the Microsoft download site.</span></span> <span data-ttu-id="baa25-105">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] のドキュメントで取り上げられているサンプルおよびチュートリアルでは、データ ストアとして SQL Server が使用されています。</span><span class="sxs-lookup"><span data-stu-id="baa25-105">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use SQL Server as the data store.</span></span> <span data-ttu-id="baa25-106">SQL Server の代わりに、無償で提供されている SQL Server Express Edition をデータ ストアとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="baa25-106">SQL Server Express Edition, which is available without charge, can also be used as the data store instead of SQL Server.</span></span>  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a><span data-ttu-id="baa25-107">AdventureWorks データベースのダウンロードとインストール</span><span class="sxs-lookup"><span data-stu-id="baa25-107">Downloading and Installing the AdventureWorks Database</span></span>  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="baa25-108">SQL Server の AdventureWorks サンプル データベースをダウンロードおよびインストールするには</span><span class="sxs-lookup"><span data-stu-id="baa25-108">To download and install the AdventureWorks sample database for SQL Server</span></span>  
  
1. <span data-ttu-id="baa25-109">Internet Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="baa25-109">Open Internet Explorer.</span></span>  
  
2. <span data-ttu-id="baa25-110">移動して、 [SQL Server 2005 サンプルとサンプル データベース](https://go.microsoft.com/fwlink/?linkid=31046)Web サイト。</span><span class="sxs-lookup"><span data-stu-id="baa25-110">Go to the [SQL Server 2005 Samples and Sample Databases](https://go.microsoft.com/fwlink/?linkid=31046) Web site.</span></span>  
  
3. <span data-ttu-id="baa25-111">記載されている手順に従ってプロセッサの種類に応じた AdventureWorks サンプル データベース (AdventureWorksDB.msi など) をダウンロードし、.MSI ファイルをローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="baa25-111">Follow the instructions for downloading the AdventureWorks sample database for your processor type (such as AdventureWorksDB.msi), and save the .MSI file to your local computer.</span></span>  
  
4. <span data-ttu-id="baa25-112">以前のバージョンの AdventureWorks は、単体でダウンロードしたか SQL Server のセットアップ時にインストールしたかに関係なく、AdventureWorks.msi の実行前に削除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="baa25-112">If you have a previous version of AdventureWorks installed from the download or during the SQL Server setup, you must remove it before running AdventureWorks.msi.</span></span>  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a><span data-ttu-id="baa25-113">単体でダウンロードした以前のバージョンの AdventureWorks サンプル データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="baa25-113">To remove a previous download of an AdventureWorks sample database</span></span>  
  
1. <span data-ttu-id="baa25-114">AdventureWorks データベースまたは AdventureWorksDW データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="baa25-114">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2. <span data-ttu-id="baa25-115">**プログラム追加と削除**を選択します**AdventureWorksDB**または **[adventureworksbi]** クリック**削除**します。</span><span class="sxs-lookup"><span data-stu-id="baa25-115">From **Add or Remove Programs**, select **AdventureWorksDB** or **AdventureWorksBI** and click **Remove**.</span></span>  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a><span data-ttu-id="baa25-116">過去にセットアップ プログラムを使用してインストールした AdventureWorks サンプル データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="baa25-116">To remove an AdventureWorks sample database previously installed using Setup</span></span>  
  
1. <span data-ttu-id="baa25-117">AdventureWorks データベースまたは AdventureWorksDW データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="baa25-117">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2. <span data-ttu-id="baa25-118">**プログラム追加と削除**を選択します**Microsoft SQL Server 2005**クリック**変更**します。</span><span class="sxs-lookup"><span data-stu-id="baa25-118">From **Add or Remove Programs**, select **Microsoft SQL Server 2005** and click **Change**.</span></span>  
  
3. <span data-ttu-id="baa25-119">**コンポーネントの選択**を選択します**ワークステーション コンポーネント**順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="baa25-119">From **Component Selection**, select **Workstation Components** and then click **Next**.</span></span>  
  
4. <span data-ttu-id="baa25-120">**、SQL Server インストール ウィザードへようこそ**、 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="baa25-120">From **Welcome to the SQL Server Installation Wizard**, click **Next**.</span></span>  
  
5. <span data-ttu-id="baa25-121">**システム構成チェック**、 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="baa25-121">From **System Configuration Check**, click **Next**.</span></span>  
  
6. <span data-ttu-id="baa25-122">**インスタンスの削除の変更または**、 をクリックして**インストール済みコンポーネントの変更**します。</span><span class="sxs-lookup"><span data-stu-id="baa25-122">From **Change or Remove Instance**, click **Change Installed Components**.</span></span>  
  
7. <span data-ttu-id="baa25-123">**機能の選択**、展開、**ドキュメント、サンプル、およびサンプル データベース**ノード。</span><span class="sxs-lookup"><span data-stu-id="baa25-123">From **Feature Selection**, expand the **Documentation, Samples, and Sample Databases** node.</span></span>  
  
8. <span data-ttu-id="baa25-124">選択**サンプル コードおよびアプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="baa25-124">Select **Sample Code and Applications**.</span></span> <span data-ttu-id="baa25-125">展開**サンプル データベース**、削除して、選択するには、サンプル データベースを選択します。**全体の機能は使用できません**します。</span><span class="sxs-lookup"><span data-stu-id="baa25-125">Expand **Sample Databases**, select the sample database to be removed, and select **Entire feature will be unavailable**.</span></span> <span data-ttu-id="baa25-126">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="baa25-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="baa25-127">クリックして**インストール**インストール ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="baa25-127">Click **Install** and finish the installation wizard.</span></span>  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a><span data-ttu-id="baa25-128">AdventureWorks サンプル データベース ファイルを SQL Server のインスタンスにアタッチするには</span><span class="sxs-lookup"><span data-stu-id="baa25-128">To attach the AdventureWorks sample database files to an instance of SQL Server</span></span>  
  
1. <span data-ttu-id="baa25-129">ファイルのサンプル データベースのインストーラー ファイルがダウンロードされたら、ダブルクリック、 **AdventureWorksDB.msi**ファイル (またはダウンロードしたファイル)、データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="baa25-129">After the file sample database installer file has downloaded, double-click the **AdventureWorksDB.msi** file (or the file you downloaded) to install the database.</span></span> <span data-ttu-id="baa25-130">既定では、データベースは c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="baa25-130">By default, the database is installed at c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span></span>  
  
2. <span data-ttu-id="baa25-131">SQLCMD または SQL Server Management Studio で次のスクリプトを実行し、AdventureWorks データベース ファイルを SQL Server のインスタンスにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="baa25-131">Attach the AdventureWorks database files to an instance of SQL Server by executing the following script SQLCMD or SQL Server Management Studio:</span></span>  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     <span data-ttu-id="baa25-132">これらのファイルが異なるドライブまたはディレクトリにインストールされている場合は、パスを適宜修正してから、`sp_attach_db` ストアド プロシージャを実行してください。</span><span class="sxs-lookup"><span data-stu-id="baa25-132">If you have installed these files to a different drive or directory, you must revise the paths appropriately before you execute the `sp_attach_db` stored procedure.</span></span>  
  
## <a name="downloading-sql-server-express-edition"></a><span data-ttu-id="baa25-133">SQL Server Express Edition のダウンロード</span><span class="sxs-lookup"><span data-stu-id="baa25-133">Downloading SQL Server Express Edition</span></span>  
 <span data-ttu-id="baa25-134">サンプルおよびチュートリアルで、[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]セクションは、データ ストアとして SQL Server 2005 を使用しますが、代わりに SQL Server Express Edition を使用するように変更できます。</span><span class="sxs-lookup"><span data-stu-id="baa25-134">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] section use SQL Server 2005 as the data store but can be modified to use SQL Server Express Edition, instead.</span></span> <span data-ttu-id="baa25-135">SQL Server Express Edition は無料で入手でき、アプリケーションと共に再配布できます。</span><span class="sxs-lookup"><span data-stu-id="baa25-135">SQL Server Express Edition is available without charge, and you can redistribute it with applications.</span></span> <span data-ttu-id="baa25-136">Visual Studio を使用している場合は、Pro 以上のエディションの SQL Server Express Edition が含まれます。</span><span class="sxs-lookup"><span data-stu-id="baa25-136">If you are using Visual Studio, SQL Server Express Edition is included in the Pro and higher editions.</span></span>  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a><span data-ttu-id="baa25-137">SQL Server Express Edition をダウンロードおよびインストールするには</span><span class="sxs-lookup"><span data-stu-id="baa25-137">To download and install SQL Server Express Edition</span></span>  
  
1. <span data-ttu-id="baa25-138">Internet Explorer を開始します。</span><span class="sxs-lookup"><span data-stu-id="baa25-138">Start Internet Explorer.</span></span>  
  
2. <span data-ttu-id="baa25-139">移動して、 [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070)ページをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="baa25-139">Go to the  [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) download page.</span></span>  
  
3. <span data-ttu-id="baa25-140">Web サイトに記載されているインストールの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="baa25-140">Follow the installation instructions on the Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa25-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="baa25-141">See also</span></span>

- [<span data-ttu-id="baa25-142">はじめに</span><span class="sxs-lookup"><span data-stu-id="baa25-142">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
