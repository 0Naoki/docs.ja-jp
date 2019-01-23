---
title: '方法: LINQ クエリの結果を返す特定の型 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 7d281de2005f1ee9227b3e3496125c8af9acba35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500617"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="1febb-102">方法: LINQ クエリの結果を返す特定の型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1febb-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="1febb-103">統合言語クエリ (LINQ) により、簡単にデータベース情報にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1febb-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="1febb-104">既定では、LINQ クエリは、匿名型としてオブジェクトの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="1febb-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="1febb-105">クエリを使用して、特定の種類の一覧を返すことを指定することも、`Select`句。</span><span class="sxs-lookup"><span data-stu-id="1febb-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="1febb-106">次の例では、SQL Server データベースに対するクエリを実行し、特定の名前付きの型として、結果を射影する新しいアプリケーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1febb-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="1febb-107">詳細については、次を参照してください。[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)と[Select 句](../../../../visual-basic/language-reference/queries/select-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="1febb-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="1febb-108">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="1febb-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="1febb-109">開発用コンピューターにこのデータベースがいない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="1febb-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="1febb-110">手順については、次を参照してください。[サンプル データベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="1febb-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="1febb-111">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="1febb-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="1febb-112">Visual Studio で開く**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**をクリックして**サーバー エクスプ ローラー**/**データベースエクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="1febb-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="1febb-113">右クリック**データ接続**で**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**  をクリックし、**接続の追加**します。</span><span class="sxs-lookup"><span data-stu-id="1febb-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="1febb-114">Northwind サンプル データベースへの接続を有効なを指定します。</span><span class="sxs-lookup"><span data-stu-id="1febb-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="1febb-115">LINQ to SQL ファイルを格納しているプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="1febb-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="1febb-116">Visual Studio で、**[ファイル]** メニューの **[新規作成]** をポイントし、**[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1febb-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="1febb-117">Visual Basic を選択**Windows フォーム アプリケーション**プロジェクトの種類として。</span><span class="sxs-lookup"><span data-stu-id="1febb-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="1febb-118">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1febb-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="1febb-119">選択、 **LINQ to SQL クラス**項目テンプレート。</span><span class="sxs-lookup"><span data-stu-id="1febb-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="1febb-120">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1febb-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="1febb-121">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1febb-121">Click **Add**.</span></span> <span data-ttu-id="1febb-122">Northwind.dbml ファイル用には、オブジェクト リレーショナル デザイナー (O/R デザイナー) を開きます。</span><span class="sxs-lookup"><span data-stu-id="1febb-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="1febb-123">O/R デザイナーをクエリにテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="1febb-123">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="1febb-124">**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="1febb-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="1febb-125">展開、**テーブル**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="1febb-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="1febb-126">O/R デザイナーを閉じた場合は、先ほど追加した northwind.dbml ファイルをダブルクリックして開くことができます。</span><span class="sxs-lookup"><span data-stu-id="1febb-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="1febb-127">Customers テーブルをクリックし、デザイナーの左側のペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1febb-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="1febb-128">デザイナーが新たに作成`Customer`プロジェクトのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1febb-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="1febb-129">クエリの結果が射影することができます、`Customer`型または作成する型として。</span><span class="sxs-lookup"><span data-stu-id="1febb-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="1febb-130">このサンプルは後の手順で新しい型を作成し、クエリの結果がその型のプロジェクトします。</span><span class="sxs-lookup"><span data-stu-id="1febb-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3.  <span data-ttu-id="1febb-131">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1febb-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="1febb-132">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="1febb-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="1febb-133">データベース クエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="1febb-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="1febb-134">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.DataGridView>に、プロジェクトの Form1 の既定の Windows フォーム コントロール。</span><span class="sxs-lookup"><span data-stu-id="1febb-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="1febb-135">Form1 クラスを変更する Form1 をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1febb-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3.  <span data-ttu-id="1febb-136">後に、 `End Class` Form1 クラスのステートメントを作成する次のコードを追加する、`CustomerInfo`このサンプルのクエリの結果を保持する型。</span><span class="sxs-lookup"><span data-stu-id="1febb-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]  
  
4.  <span data-ttu-id="1febb-137">O/R デザイナーにテーブルを追加したときに、デザイナーが追加、<xref:System.Data.Linq.DataContext>オブジェクトをプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="1febb-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="1febb-138">このオブジェクトには、これらのテーブルにアクセスして、個々 のオブジェクトと各テーブルのコレクションへのアクセスに必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1febb-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="1febb-139"><xref:System.Data.Linq.DataContext>オブジェクトの名前は、プロジェクトに基づく .dbml ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="1febb-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="1febb-140">このプロジェクトで、<xref:System.Data.Linq.DataContext>オブジェクトの名前は`northwindDataContext`します。</span><span class="sxs-lookup"><span data-stu-id="1febb-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="1febb-141">インスタンスを作成することができます、 <xref:System.Data.Linq.DataContext> O/R デザイナーによって、コードとクエリにテーブルが指定されています。</span><span class="sxs-lookup"><span data-stu-id="1febb-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="1febb-142">`Load` Form1 クラスのイベントは、データ コンテキストのプロパティとして公開されるテーブルを照会する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1febb-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="1febb-143">`Select`新しいクエリの句が作成されます`CustomerInfo`クエリ結果の項目ごとに、匿名型ではなく型です。</span><span class="sxs-lookup"><span data-stu-id="1febb-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]  
  
5.  <span data-ttu-id="1febb-144">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="1febb-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1febb-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="1febb-145">See also</span></span>
- [<span data-ttu-id="1febb-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="1febb-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="1febb-147">クエリ</span><span class="sxs-lookup"><span data-stu-id="1febb-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="1febb-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1febb-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="1febb-149">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="1febb-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
