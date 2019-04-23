---
title: 'チュートリアル: ストアド プロシージャのみの使用 (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 1527e3b4b614d4e700ae0c2c0fc555e14c7bc8d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314829"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a><span data-ttu-id="e8eed-102">チュートリアル: ストアド プロシージャのみの使用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8eed-102">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>
<span data-ttu-id="e8eed-103">このチュートリアルでは、ストアド プロシージャのみを使用してデータにアクセスする、基本の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] シナリオ全体を示します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by using stored procedures only.</span></span> <span data-ttu-id="e8eed-104">この方法は、データ ストアへのアクセス方法を制限する目的で、データベース管理者によってよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8eed-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションでストアド プロシージャを使用して、既定の動作をオーバーライドすることもできます。これは、`Create`、`Update`、および `Delete` の各プロセスで特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="e8eed-106">詳細については、次を参照してください。[のカスタマイズを挿入、更新、および削除を行う](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="e8eed-107">このチュートリアルの目的は、Northwind サンプル データベース内のストアド プロシージャにマップされている 2 つのメソッドを使用します。CustOrdersDetail および CustOrderHist します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="e8eed-108">マッピングは、Visual Basic ファイルを生成する SqlMetal コマンド ライン ツールを実行するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-108">The mapping occurs when you run the SqlMetal command-line tool to generate a Visual Basic file.</span></span> <span data-ttu-id="e8eed-109">詳細については、このチュートリアルの「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8eed-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="e8eed-110">このチュートリアルは、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]には依存しません。</span><span class="sxs-lookup"><span data-stu-id="e8eed-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="e8eed-111">Visual Studio を使用している開発者が使用することも、[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]ストアド プロシージャの機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-111">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="e8eed-112">参照してください[LINQ to Visual Studio での SQL ツール](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="e8eed-113">このチュートリアルは、Visual Basic 開発設定を使用して記述されています。</span><span class="sxs-lookup"><span data-stu-id="e8eed-113">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e8eed-114">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8eed-114">Prerequisites</span></span>  
 <span data-ttu-id="e8eed-115">このチュートリアルの前提条件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8eed-115">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="e8eed-116">このチュートリアルでは、専用フォルダー ("c:\linqtest3") を使用してファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-116">This walkthrough uses a dedicated folder ("c:\linqtest3") to hold files.</span></span> <span data-ttu-id="e8eed-117">チュートリアルを開始する前に、このフォルダーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="e8eed-117">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="e8eed-118">Northwind サンプル データベース。</span><span class="sxs-lookup"><span data-stu-id="e8eed-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="e8eed-119">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード サイトからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="e8eed-120">手順については、次を参照してください。[サンプル データベースのダウンロード](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="e8eed-121">データベースをダウンロードしたら、northwnd.mdf ファイルを c:\linqtest3 フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest3 folder.</span></span>  
  
-   <span data-ttu-id="e8eed-122">Northwind データベースから生成された Visual Basic コード ファイル。</span><span class="sxs-lookup"><span data-stu-id="e8eed-122">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="e8eed-123">このチュートリアルは、SqlMetal ツールを使用して次のコマンド ラインで作成されています。</span><span class="sxs-lookup"><span data-stu-id="e8eed-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="e8eed-124">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="e8eed-124">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="e8eed-125">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8eed-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="e8eed-126">概要</span><span class="sxs-lookup"><span data-stu-id="e8eed-126">Overview</span></span>  
 <span data-ttu-id="e8eed-127">このチュートリアルは、主に次の 6 つのタスクで構成されています。</span><span class="sxs-lookup"><span data-stu-id="e8eed-127">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="e8eed-128">設定する、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Visual Studio でソリューション。</span><span class="sxs-lookup"><span data-stu-id="e8eed-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="e8eed-129">プロジェクトに System.Data.Linq アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
-   <span data-ttu-id="e8eed-130">プロジェクトにデータベース コード ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-130">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="e8eed-131">データベースへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-131">Creating a connection to the database.</span></span>  
  
-   <span data-ttu-id="e8eed-132">ユーザー インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-132">Setting up the user interface.</span></span>  
  
-   <span data-ttu-id="e8eed-133">アプリケーションを実行およびテストします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="e8eed-134">LINQ to SQL ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="e8eed-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="e8eed-135">この最初のタスクでは、ビルドおよび実行するために必要な参照を含む Visual Studio ソリューションを作成、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="e8eed-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="e8eed-136">LINQ to SQL ソリューションを作成するには</span><span class="sxs-lookup"><span data-stu-id="e8eed-136">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="e8eed-137">Visual Studio で **[ファイル]** メニューの **[新しいプロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-137">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="e8eed-138">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、 **[Visual Basic]** を展開し、 **[Windows]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-138">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3. <span data-ttu-id="e8eed-139">**[テンプレート]** ペインの **[Windows フォーム アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4. <span data-ttu-id="e8eed-140">**名前**ボックスに「 **SprocOnlyApp**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5. <span data-ttu-id="e8eed-141">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-141">Click **OK**.</span></span>  
  
     <span data-ttu-id="e8eed-142">Windows フォーム デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-142">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="e8eed-143">LINQ to SQL アセンブリ参照を追加する</span><span class="sxs-lookup"><span data-stu-id="e8eed-143">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="e8eed-144">標準の Windows フォーム アプリケーション テンプレートには、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アセンブリは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="e8eed-144">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="e8eed-145">次の手順に従って、アセンブリを自分で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8eed-145">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="e8eed-146">System.Data.Linq.dll を追加するには</span><span class="sxs-lookup"><span data-stu-id="e8eed-146">To add System.Data.Linq.dll</span></span>  
  
1. <span data-ttu-id="e8eed-147">**ソリューション エクスプ ローラー**、] をクリックして **[すべてのファイル**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-147">In **Solution Explorer**, click **Show All Files**.</span></span>  
  
2. <span data-ttu-id="e8eed-148">**ソリューション エクスプ ローラー**を右クリックして**参照**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
3. <span data-ttu-id="e8eed-149">**参照の追加**ダイアログ ボックスで、をクリックして **.NET**、System.Data.Linq アセンブリをクリックし、順にクリックして、 **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e8eed-150">アセンブリがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="e8eed-151">プロジェクトに Northwind コード ファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="e8eed-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="e8eed-152">この手順では、事前に SqlMetal ツールを使用して、Northwind サンプル データベースからコード ファイルを生成していることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="e8eed-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="e8eed-153">詳細については、このチュートリアルの「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8eed-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="e8eed-154">プロジェクトに Northwind コード ファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="e8eed-154">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="e8eed-155">**[プロジェクト]** メニューの **[既存項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="e8eed-156">**既存項目の追加**ダイアログ ボックスが c:\linqtest3\northwind.vb に移動し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-156">In the **Add Existing Item** dialog box, move to c:\linqtest3\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="e8eed-157">プロジェクトに northwind.vb ファイルが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-157">The northwind.vb file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="e8eed-158">データベース接続を作成する</span><span class="sxs-lookup"><span data-stu-id="e8eed-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="e8eed-159">この手順では、Northwind サンプル データベースへの接続を定義します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="e8eed-160">このチュートリアルでは、パスとして "c:\linqtest3\northwnd.mdf" を使用します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-160">This walkthrough uses "c:\linqtest3\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="e8eed-161">データベース接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="e8eed-161">To create the database connection</span></span>  
  
1. <span data-ttu-id="e8eed-162">**ソリューション エクスプ ローラー**、右クリック**Form1.vb**、 をクリックし、**コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-162">In **Solution Explorer**, right-click **Form1.vb**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="e8eed-163">コード エディターに `Class Form1` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-163">`Class Form1` appears in the code editor.</span></span>  
  
2. <span data-ttu-id="e8eed-164">`Form1` コード ブロックに次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-164">Type the following code into the `Form1` code block:</span></span>  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="e8eed-165">ユーザー インターフェイスを設定する</span><span class="sxs-lookup"><span data-stu-id="e8eed-165">Setting up the User Interface</span></span>  
 <span data-ttu-id="e8eed-166">この手順では、ユーザーがストアド プロシージャを実行してデータベース内のデータにアクセスできるように、インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-166">In this task you create an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="e8eed-167">このチュートリアルで作成するアプリケーションでは、ユーザーはアプリケーションに埋め込まれているストアド プロシージャを使用してのみ、データベース内のデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-167">In the application that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="e8eed-168">ユーザー インターフェイスを設定するには</span><span class="sxs-lookup"><span data-stu-id="e8eed-168">To set up the user interface</span></span>  
  
1. <span data-ttu-id="e8eed-169">戻り値を Windows フォーム デザイナー (**form1.vb [デザイン]**)。</span><span class="sxs-lookup"><span data-stu-id="e8eed-169">Return to the Windows Forms Designer (**Form1.vb[Design]**).</span></span>  
  
2. <span data-ttu-id="e8eed-170">**[表示]** メニューの **[ツールボックス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-170">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="e8eed-171">ツールボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-171">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8eed-172">をクリックして、**自動的に隠す**このセクションの手順を残りの実行中に、ツールボックスを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-172">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3. <span data-ttu-id="e8eed-173">2 つのボタン、2 つのテキスト ボックス、および 2 つのラベルをツールボックスからドラッグ**Form1**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-173">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="e8eed-174">図のようにコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-174">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="e8eed-175">展開**Form1**コントロールを簡単に適合するようにします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-175">Expand **Form1** so that the controls fit easily.</span></span>  
  
4. <span data-ttu-id="e8eed-176">右クリックして**Label1**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-176">Right-click **Label1**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="e8eed-177">変更、**テキスト**プロパティから**Label1**に**Enter OrderID:** します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-177">Change the **Text** property from **Label1** to **Enter OrderID:**.</span></span>  
  
6. <span data-ttu-id="e8eed-178">に対して同じ方法で**Label2**、変更、**テキスト**プロパティから**Label2**に**Enter CustomerID:** します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-178">In the same way for **Label2**, change the **Text** property from **Label2** to **Enter CustomerID:**.</span></span>  
  
7. <span data-ttu-id="e8eed-179">同様に、変更、**テキスト**プロパティを**Button1**に**Order Details**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-179">In the same way, change the **Text** property for **Button1** to **Order Details**.</span></span>  
  
8. <span data-ttu-id="e8eed-180">変更、**テキスト**プロパティ**Button2**に**注文履歴**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-180">Change the **Text** property for **Button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="e8eed-181">すべてのテキストが表示されるように、ボタン コントロールの幅を広げます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-181">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="e8eed-182">ボタン クリックを処理するには</span><span class="sxs-lookup"><span data-stu-id="e8eed-182">To handle button clicks</span></span>  
  
1. <span data-ttu-id="e8eed-183">ダブルクリック**Order Details**で**Form1**を作成する、`Button1`イベント ハンドラーと、コード エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-183">Double-click **Order Details** on **Form1** to create the `Button1` event handler and open the code editor.</span></span>  
  
2. <span data-ttu-id="e8eed-184">`Button1` のハンドラーに次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-184">Type the following code into the `Button1` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. <span data-ttu-id="e8eed-185">ダブルクリック**Button2** Form1 を作成する上で、`Button2`イベント ハンドラーと、コード エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-185">Now double-click **Button2** on Form1 to create the `Button2` event handler and open the code editor.</span></span>  
  
4. <span data-ttu-id="e8eed-186">`Button2` のハンドラーに次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-186">Type the following code into the `Button2` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="e8eed-187">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="e8eed-187">Testing the Application</span></span>  
 <span data-ttu-id="e8eed-188">次に、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="e8eed-188">Now it is time to test your application.</span></span> <span data-ttu-id="e8eed-189">データ ストアに対する操作は、2 つのストアド プロシージャで実行できる処理に制限されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8eed-189">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="e8eed-190">つまり、入力した orderID に含まれている製品を返す処理と、入力した CustomerID の注文製品の履歴を返す処理のみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-190">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="e8eed-191">アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="e8eed-191">To test the application</span></span>  
  
1. <span data-ttu-id="e8eed-192">F5 キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-192">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="e8eed-193">Form1 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-193">Form1 appears.</span></span>  
  
2. <span data-ttu-id="e8eed-194">**Enter OrderID**ボックスに「 **10249**  をクリックし、 **Order Details**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-194">In the **Enter OrderID** box, type **10249** and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="e8eed-195">注文 10249 に含まれている製品がメッセージ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-195">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="e8eed-196">クリックして**OK**メッセージ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-196">Click **OK** to close the message box.</span></span>  
  
3. <span data-ttu-id="e8eed-197">**Enter CustomerID**ボックスに「 `ALFKI`、 をクリックし、**注文履歴**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-197">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="e8eed-198">メッセージ ボックスに、顧客 ALFKI の注文履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-198">A message box lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="e8eed-199">クリックして**OK**メッセージ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-199">Click **OK** to close the message box.</span></span>  
  
4. <span data-ttu-id="e8eed-200">**Enter OrderID**ボックスに「 `123`、 をクリックし、 **Order Details**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-200">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="e8eed-201">メッセージ ボックスに "No results" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-201">A message box displays "No results."</span></span>  
  
     <span data-ttu-id="e8eed-202">クリックして**OK**メッセージ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-202">Click **OK** to close the message box.</span></span>  
  
5. <span data-ttu-id="e8eed-203">**デバッグ** メニューのをクリックして**デバッグを停止**します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-203">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="e8eed-204">デバッグ セッションが終了します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-204">The debug session closes.</span></span>  
  
6. <span data-ttu-id="e8eed-205">クリックすることができる場合、実験が完了したら、**プロジェクトを閉じる**で、**ファイル**] メニューの [されたら、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="e8eed-205">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e8eed-206">次の手順</span><span class="sxs-lookup"><span data-stu-id="e8eed-206">Next Steps</span></span>  
 <span data-ttu-id="e8eed-207">いくつかの変更を加えることによって、このプロジェクトを強化できます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-207">You can enhance this project by making some changes.</span></span> <span data-ttu-id="e8eed-208">たとえば、使用できるストアド プロシージャの一覧をリスト ボックスに表示し、実行するプロシージャをユーザーに選択させることができます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-208">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="e8eed-209">レポートの出力をテキスト ファイルに送ることもできます。</span><span class="sxs-lookup"><span data-stu-id="e8eed-209">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8eed-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8eed-210">See also</span></span>

- [<span data-ttu-id="e8eed-211">チュートリアルによる学習</span><span class="sxs-lookup"><span data-stu-id="e8eed-211">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [<span data-ttu-id="e8eed-212">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="e8eed-212">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
