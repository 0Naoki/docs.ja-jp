---
title: '方法 : LINQ を使用してクエリ結果をフィルター処理する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: f9854650b1f89a2330cfa81910187e3fb01c54b4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43424439"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="67fc6-102">方法 : LINQ を使用してクエリ結果をフィルター処理する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67fc6-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="67fc6-103">統合言語クエリ (LINQ) により、簡単にデータベース情報にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="67fc6-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="67fc6-104">次の例は、SQL Server データベースに対してクエリを実行し、特定の値で結果をフィルター処理を使用して新しいアプリケーションを作成する方法を示します、`Where`句。</span><span class="sxs-lookup"><span data-stu-id="67fc6-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="67fc6-105">詳細については、次を参照してください。 [Where 句](../../../../visual-basic/language-reference/queries/where-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="67fc6-106">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="67fc6-107">開発用コンピューターにこのデータベースがいない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="67fc6-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="67fc6-108">手順については、次を参照してください。[サンプル データベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="67fc6-109">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="67fc6-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="67fc6-110">Visual Studio で開く**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**をクリックして**サーバー エクスプ ローラー**/**データベースエクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="67fc6-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="67fc6-111">右クリック**データ接続**で**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**  をクリックし、**接続の追加**します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="67fc6-112">Northwind サンプル データベースへの接続を有効なを指定します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="67fc6-113">LINQ to SQL ファイルを格納しているプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="67fc6-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="67fc6-114">Visual Studio で、**[ファイル]** メニューの **[新規作成]** をポイントし、**[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67fc6-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="67fc6-115">Visual Basic を選択**Windows フォーム アプリケーション**プロジェクトの種類として。</span><span class="sxs-lookup"><span data-stu-id="67fc6-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="67fc6-116">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67fc6-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="67fc6-117">選択、 **LINQ to SQL クラス**項目テンプレート。</span><span class="sxs-lookup"><span data-stu-id="67fc6-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="67fc6-118">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="67fc6-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="67fc6-119">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67fc6-119">Click **Add**.</span></span> <span data-ttu-id="67fc6-120">オブジェクト リレーショナル デザイナー (O/R デザイナー) は、northwind.dbml ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="67fc6-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="67fc6-121">O/R デザイナーをクエリにテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="67fc6-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="67fc6-122">**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="67fc6-123">展開、**テーブル**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="67fc6-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="67fc6-124">O/R デザイナーを閉じた場合は、先ほど追加した northwind.dbml ファイルをダブルクリックして開くことができます。</span><span class="sxs-lookup"><span data-stu-id="67fc6-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="67fc6-125">Customers テーブルをクリックし、デザイナーの左側のペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="67fc6-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="67fc6-126">Orders テーブルをクリックし、デザイナーの左側のペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="67fc6-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="67fc6-127">デザイナーを新規作成`Customer`と`Order`プロジェクトのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="67fc6-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="67fc6-128">デザイナーが自動的にテーブル間のリレーションシップを検出し、関連オブジェクトのプロパティの子を作成することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="67fc6-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="67fc6-129">たとえば、IntelliSense が表示されますが、`Customer`オブジェクトには、`Orders`その顧客に関連するすべての注文のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="67fc6-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="67fc6-130">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="67fc6-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="67fc6-131">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="67fc6-132">データベース クエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="67fc6-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="67fc6-133">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.DataGridView>に、プロジェクトの Form1 の既定の Windows フォーム コントロール。</span><span class="sxs-lookup"><span data-stu-id="67fc6-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="67fc6-134">コードを追加する Form1 をダブルクリックして、`Load`フォームのイベント。</span><span class="sxs-lookup"><span data-stu-id="67fc6-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="67fc6-135">O/R デザイナーにテーブルを追加したときに、デザイナーが追加、<xref:System.Data.Linq.DataContext>プロジェクトのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="67fc6-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="67fc6-136">このオブジェクトには、個々 のオブジェクトと各テーブルのコレクションだけでなく、それらのテーブルにアクセスするに必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67fc6-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="67fc6-137"><xref:System.Data.Linq.DataContext>オブジェクトの名前は、プロジェクトに基づく .dbml ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="67fc6-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="67fc6-138">このプロジェクトで、<xref:System.Data.Linq.DataContext>オブジェクトの名前は`northwindDataContext`します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="67fc6-139">インスタンスを作成することができます、 <xref:System.Data.Linq.DataContext> O/R デザイナーによって、コードとクエリにテーブルが指定されています。</span><span class="sxs-lookup"><span data-stu-id="67fc6-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="67fc6-140">次のコードを追加、`Load`データ コンテキストのプロパティとして公開されるテーブルを照会するイベントです。</span><span class="sxs-lookup"><span data-stu-id="67fc6-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="67fc6-141">クエリの結果をフィルター処理し、内にある顧客のみを返す`London`します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="67fc6-142">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-142">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="67fc6-143">試用できるその他のいくつかのフィルターを次に示します。</span><span class="sxs-lookup"><span data-stu-id="67fc6-143">Following are some other filters that you can try.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="67fc6-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="67fc6-144">See Also</span></span>  
 [<span data-ttu-id="67fc6-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="67fc6-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="67fc6-146">クエリ</span><span class="sxs-lookup"><span data-stu-id="67fc6-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="67fc6-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="67fc6-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="67fc6-148">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="67fc6-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
