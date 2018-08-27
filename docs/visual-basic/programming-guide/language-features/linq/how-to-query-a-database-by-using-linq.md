---
title: '方法 : LINQ を使用してデータベースを照会する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: 75f3d71e76c81a016a4e2c6fac754b91db31873e
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924878"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="0785a-102">方法 : LINQ を使用してデータベースを照会する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0785a-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="0785a-103">統合言語クエリ (LINQ) により、簡単にデータベース情報にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0785a-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="0785a-104">次の例では、SQL Server データベースに対してクエリを実行する新しいアプリケーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0785a-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="0785a-105">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="0785a-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="0785a-106">開発用コンピューターにこのデータベースがいない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0785a-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="0785a-107">手順については、次を参照してください。[サンプル データベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="0785a-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="0785a-108">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="0785a-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="0785a-109">Visual Studio で開く**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**をクリックして**サーバー エクスプ ローラー**/**データベースエクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="0785a-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="0785a-110">右クリック**データ接続**で**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**  をクリックし、**接続の追加**します。</span><span class="sxs-lookup"><span data-stu-id="0785a-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="0785a-111">Northwind サンプル データベースへの接続を有効なを指定します。</span><span class="sxs-lookup"><span data-stu-id="0785a-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="0785a-112">LINQ to SQL ファイルを格納しているプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="0785a-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="0785a-113">Visual Studio で、**[ファイル]** メニューの **[新規作成]** をポイントし、**[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0785a-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="0785a-114">Visual Basic を選択**Windows フォーム アプリケーション**プロジェクトの種類として。</span><span class="sxs-lookup"><span data-stu-id="0785a-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="0785a-115">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0785a-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="0785a-116">選択、 **LINQ to SQL クラス**項目テンプレート。</span><span class="sxs-lookup"><span data-stu-id="0785a-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="0785a-117">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="0785a-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="0785a-118">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0785a-118">Click **Add**.</span></span> <span data-ttu-id="0785a-119">Northwind.dbml ファイル用には、オブジェクト リレーショナル デザイナー (O/R デザイナー) を開きます。</span><span class="sxs-lookup"><span data-stu-id="0785a-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="0785a-120">O/R デザイナーをクエリにテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="0785a-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="0785a-121">**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="0785a-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="0785a-122">展開、**テーブル**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="0785a-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="0785a-123">O/R デザイナーを閉じた場合は、先ほど追加した northwind.dbml ファイルをダブルクリックして開くことができます。</span><span class="sxs-lookup"><span data-stu-id="0785a-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="0785a-124">Customers テーブルをクリックし、デザイナーの左側のペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="0785a-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="0785a-125">Orders テーブルをクリックし、デザイナーの左側のペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="0785a-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="0785a-126">デザイナーを新規作成`Customer`と`Order`プロジェクトのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0785a-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="0785a-127">デザイナーが自動的にテーブル間のリレーションシップを検出し、関連オブジェクトのプロパティの子を作成することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0785a-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="0785a-128">たとえば、IntelliSense が表示されますが、`Customer`オブジェクトには、`Orders`その顧客に関連するすべての注文のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="0785a-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="0785a-129">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0785a-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="0785a-130">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="0785a-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="0785a-131">データベース クエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="0785a-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="0785a-132">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.DataGridView>に、プロジェクトの Form1 の既定の Windows フォーム コントロール。</span><span class="sxs-lookup"><span data-stu-id="0785a-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="0785a-133">コードを追加する Form1 をダブルクリックして、`Load`フォームのイベント。</span><span class="sxs-lookup"><span data-stu-id="0785a-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="0785a-134">O/R デザイナーにテーブルを追加したときに、デザイナーが追加、<xref:System.Data.Linq.DataContext>プロジェクトのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0785a-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="0785a-135">このオブジェクトには、個々 のオブジェクトと各テーブルのコレクションだけでなく、それらのテーブルにアクセスするに必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0785a-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="0785a-136"><xref:System.Data.Linq.DataContext>オブジェクトの名前は、プロジェクトに基づく .dbml ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="0785a-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="0785a-137">このプロジェクトで、<xref:System.Data.Linq.DataContext>オブジェクトの名前は`northwindDataContext`します。</span><span class="sxs-lookup"><span data-stu-id="0785a-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="0785a-138">インスタンスを作成することができます、 <xref:System.Data.Linq.DataContext> O/R デザイナーによって、コードとクエリにテーブルが指定されています。</span><span class="sxs-lookup"><span data-stu-id="0785a-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="0785a-139">次のコードを追加、`Load`データ コンテキストのプロパティとして公開されるテーブルを照会するイベントです。</span><span class="sxs-lookup"><span data-stu-id="0785a-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="0785a-140">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="0785a-140">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="0785a-141">次に、いくつか追加のクエリを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="0785a-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]  
    [!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0785a-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="0785a-142">See Also</span></span>  
 [<span data-ttu-id="0785a-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="0785a-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="0785a-144">クエリ</span><span class="sxs-lookup"><span data-stu-id="0785a-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="0785a-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0785a-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="0785a-146">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="0785a-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
