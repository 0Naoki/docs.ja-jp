---
title: '方法 : データを Windows フォーム DataGridView コントロールにバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 4064ef26ee550c02ac8825ac4c1a417472b64de6
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45508212"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="3e03f-102">方法 : データを Windows フォーム DataGridView コントロールにバインドする</span><span class="sxs-lookup"><span data-stu-id="3e03f-102">How to: Bind Data to the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3e03f-103"><xref:System.Windows.Forms.DataGridView> コントロールは標準 Windows フォームのデータ バインディング モデルをサポートするため、各種のデータ ソースにバインドします。</span><span class="sxs-lookup"><span data-stu-id="3e03f-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to a variety of data sources.</span></span> <span data-ttu-id="3e03f-104">ただし、ほとんどの状況では、データ ソースとの対話の詳細を管理する <xref:System.Windows.Forms.BindingSource> コンポーネントにバインドします。</span><span class="sxs-lookup"><span data-stu-id="3e03f-104">In most circumstances, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component which will manage the details of interacting with the data source.</span></span> <span data-ttu-id="3e03f-105"><xref:System.Windows.Forms.BindingSource> コンポーネントは Windows フォームのデータ ソースを表すことができ、データの場所を選択または変更するときに、優れた柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="3e03f-105">The <xref:System.Windows.Forms.BindingSource> component can represent any Windows Forms data source and gives you great flexibility when choosing or modifying the location of your data.</span></span> <span data-ttu-id="3e03f-106">サポートされるデータ ソースの詳細については、<xref:System.Windows.Forms.DataGridView>コントロールを参照してください[DataGridView コントロールの概要](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="3e03f-106">For more information about the data sources supported by the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="3e03f-107">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3e03f-107">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="3e03f-108">「[方法 : デザイナーを使用してデータを Windows フォーム DataGridView コントロールにバインドする](https://msdn.microsoft.com/library/33w255ac\(v=vs.110\))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e03f-108">Also see [How to: Bind Data to the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/33w255ac\(v=vs.110\)).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="3e03f-109">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="3e03f-109">Procedure</span></span>  
  
#### <a name="to-connect-a-datagridview-control-to-data"></a><span data-ttu-id="3e03f-110">DataGridView コントロールをデータに接続するには</span><span class="sxs-lookup"><span data-stu-id="3e03f-110">To connect a DataGridView control to data</span></span>  
  
1.  <span data-ttu-id="3e03f-111">データベースからデータを取得する操作の詳細を処理するメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="3e03f-111">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="3e03f-112">次のコード例では、<xref:System.Data.SqlClient.SqlDataAdapter> コンポーネントを初期化する `GetData` メソッドを実装し、これを使用して <xref:System.Data.DataTable> に値を設定します。</span><span class="sxs-lookup"><span data-stu-id="3e03f-112">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="3e03f-113">次に、<xref:System.Data.DataTable> が <xref:System.Windows.Forms.BindingSource> コンポーネントにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="3e03f-113">The <xref:System.Data.DataTable> is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="3e03f-114">`connectionString` 変数は、使用しているデータベースに合った値に設定してください。</span><span class="sxs-lookup"><span data-stu-id="3e03f-114">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="3e03f-115">Northwind SQL Server サンプル データベースがインストールされているサーバーにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e03f-115">You will need access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#20)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#20)]  
  
2.  <span data-ttu-id="3e03f-116">フォームの <xref:System.Windows.Forms.Form.Load> イベント ハンドラーで、<xref:System.Windows.Forms.DataGridView> コントロールを <xref:System.Windows.Forms.BindingSource> コンポーネントにバインドし、`GetData` メソッドを呼び出してデータベースからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="3e03f-116">In your form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#10)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="3e03f-117">例</span><span class="sxs-lookup"><span data-stu-id="3e03f-117">Example</span></span>  
 <span data-ttu-id="3e03f-118">次の完全なコード例では、データベースからデータを再読み込みし、データベースに変更を送信するためのボタンを提供します。</span><span class="sxs-lookup"><span data-stu-id="3e03f-118">The following complete code example provides buttons for reloading data from the database and submitting changes to the database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#00)]
 [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3e03f-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3e03f-119">Compiling the Code</span></span>  
 <span data-ttu-id="3e03f-120">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3e03f-120">This example requires:</span></span>  
  
-   <span data-ttu-id="3e03f-121">System、System.Windows.Forms、System.Data、および System.XML の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="3e03f-121">References to the System, System.Windows.Forms, System.Data, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="3e03f-122">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="3e03f-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="3e03f-123">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e03f-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="3e03f-124">「[方法: 完成した Windows フォーム コードの例を Visual Studio を使ってコンパイルして実行する](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e03f-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3e03f-125">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3e03f-125">.NET Framework Security</span></span>  
 <span data-ttu-id="3e03f-126">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="3e03f-126">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="3e03f-127">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="3e03f-127">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="3e03f-128">詳細については、「[接続情報の保護](../../../../docs/framework/data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e03f-128">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e03f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e03f-129">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="3e03f-130">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="3e03f-130">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="3e03f-131">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="3e03f-131">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
