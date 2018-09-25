---
title: '方法 : LINQ を使用してストアド プロシージャを呼び出す (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 50a4dff90dc1ce02869978f1da147e530cefc3e1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079741"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="12f80-102">方法 : LINQ を使用してストアド プロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12f80-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="12f80-103">統合言語クエリ (LINQ) を簡単にデータベースなどに格納されているオブジェクトの手順も含め、データベースの情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="12f80-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="12f80-104">次の例では、SQL Server データベースでストアド プロシージャを呼び出すアプリケーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12f80-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="12f80-105">データベースの 2 つの異なるストアド プロシージャを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12f80-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="12f80-106">各手順では、クエリの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="12f80-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="12f80-107">1 つのプロシージャは、入力パラメーターを受け取り、その他のプロシージャはパラメーターを取りません。</span><span class="sxs-lookup"><span data-stu-id="12f80-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="12f80-108">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="12f80-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="12f80-109">開発用コンピューターにこのデータベースがいない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="12f80-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="12f80-110">手順については、次を参照してください。[サンプル データベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="12f80-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="12f80-111">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="12f80-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="12f80-112">Visual Studio で開く**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**をクリックして**サーバー エクスプ ローラー**/**データベースエクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="12f80-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="12f80-113">右クリック**データ接続**で**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**  をクリックし、**接続の追加**します。</span><span class="sxs-lookup"><span data-stu-id="12f80-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="12f80-114">Northwind サンプル データベースへの接続を有効なを指定します。</span><span class="sxs-lookup"><span data-stu-id="12f80-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="12f80-115">LINQ to SQL ファイルを格納しているプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="12f80-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="12f80-116">Visual Studio で、**[ファイル]** メニューの **[新規作成]** をポイントし、**[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f80-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="12f80-117">Visual Basic を選択**Windows フォーム アプリケーション**プロジェクトの種類として。</span><span class="sxs-lookup"><span data-stu-id="12f80-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="12f80-118">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f80-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="12f80-119">選択、 **LINQ to SQL クラス**項目テンプレート。</span><span class="sxs-lookup"><span data-stu-id="12f80-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="12f80-120">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="12f80-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="12f80-121">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f80-121">Click **Add**.</span></span> <span data-ttu-id="12f80-122">Northwind.dbml ファイル用には、オブジェクト リレーショナル デザイナー (O/R デザイナー) を開きます。</span><span class="sxs-lookup"><span data-stu-id="12f80-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="12f80-123">ストアド プロシージャを O/R デザイナーに追加するには</span><span class="sxs-lookup"><span data-stu-id="12f80-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="12f80-124">**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="12f80-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="12f80-125">展開、 **Stored Procedures**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="12f80-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="12f80-126">O/R デザイナーを閉じた場合は、先ほど追加した northwind.dbml ファイルをダブルクリックして開くことができます。</span><span class="sxs-lookup"><span data-stu-id="12f80-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="12f80-127">をクリックして、 **Sales by Year**ストアド プロシージャと、デザイナーの右ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="12f80-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="12f80-128">をクリックして、 **10 最も高価な製品**ストアド プロシージャは、デザイナーの右側のペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="12f80-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="12f80-129">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="12f80-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="12f80-130">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="12f80-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="12f80-131">ストアド プロシージャの結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="12f80-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="12f80-132">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.DataGridView>に、プロジェクトの Form1 の既定の Windows フォーム コントロール。</span><span class="sxs-lookup"><span data-stu-id="12f80-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="12f80-133">コードを追加する Form1 をダブルクリックしてその`Load`イベント。</span><span class="sxs-lookup"><span data-stu-id="12f80-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="12f80-134">デザイナーが追加されたストアド プロシージャを O/R デザイナーに追加したときに、<xref:System.Data.Linq.DataContext>プロジェクトのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="12f80-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="12f80-135">このオブジェクトには、これらのプロシージャにアクセスするに必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="12f80-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="12f80-136"><xref:System.Data.Linq.DataContext>オブジェクトの名前は、プロジェクトに基づく .dbml ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="12f80-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="12f80-137">このプロジェクトで、<xref:System.Data.Linq.DataContext>オブジェクトの名前は`northwindDataContext`します。</span><span class="sxs-lookup"><span data-stu-id="12f80-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="12f80-138">インスタンスを作成することができます、 <xref:System.Data.Linq.DataContext> O/R デザイナーによって、コードの呼び出しでストアド プロシージャのメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="12f80-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="12f80-139">バインドする、<xref:System.Windows.Forms.DataGridView>オブジェクト、クエリを強制的に呼び出すことによってすぐに実行する必要があります、<xref:System.Linq.Enumerable.ToList%2A>メソッドでは、ストアド プロシージャの結果。</span><span class="sxs-lookup"><span data-stu-id="12f80-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="12f80-140">次のコードを追加、`Load`データ コンテキストのメソッドとして公開されたストアド プロシージャのいずれかを呼び出すイベントです。</span><span class="sxs-lookup"><span data-stu-id="12f80-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  <span data-ttu-id="12f80-141">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="12f80-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f80-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="12f80-142">See Also</span></span>  
 [<span data-ttu-id="12f80-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="12f80-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="12f80-144">クエリ</span><span class="sxs-lookup"><span data-stu-id="12f80-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="12f80-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="12f80-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="12f80-146">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="12f80-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="12f80-147">方法: 更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="12f80-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](https://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
