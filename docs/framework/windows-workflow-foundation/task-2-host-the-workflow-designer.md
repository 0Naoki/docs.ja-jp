---
title: タスク 2:ワークフロー デザイナーのホスティング
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 553a02732e08fa148ffdee250df0305deb8e63b7
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169994"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="d153f-102">タスク 2:ワークフロー デザイナーのホスティング</span><span class="sxs-lookup"><span data-stu-id="d153f-102">Task 2: Host the Workflow Designer</span></span>
<span data-ttu-id="d153f-103">このトピックでは、のインスタンスをホストするための手順を説明します、 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] Windows Presentation Foundation (WPF) アプリケーションでします。</span><span class="sxs-lookup"><span data-stu-id="d153f-103">This topic describes the procedure for hosting an instance of the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="d153f-104">プロシージャを構成、**グリッド**、デザイナーを格納しているコントロールのインスタンスをプログラムで作成する、 <xref:System.Activities.Presentation.WorkflowDesigner> 、既定値を格納している<xref:System.Activities.Statements.Sequence>アクティビティを提供する、デザイナーのメタデータを登録しますすべての組み込みのアクティビティ、およびホストのデザイナー サポート、 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] WPF アプリケーションでします。</span><span class="sxs-lookup"><span data-stu-id="d153f-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in the WPF application.</span></span>  
  
### <a name="to-host-the-workflow-designer"></a><span data-ttu-id="d153f-105">ワークフロー デザイナーをホストするには</span><span class="sxs-lookup"><span data-stu-id="d153f-105">To host the workflow designer</span></span>  
  
1. <span data-ttu-id="d153f-106">HostingApplication プロジェクトを開きますで作成した[タスク 1。新しい Windows Presentation Foundation アプリケーションを作成する](task-1-create-a-new-wpf-app.md)します。</span><span class="sxs-lookup"><span data-stu-id="d153f-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>  
  
2. <span data-ttu-id="d153f-107">[!INCLUDE[wfd2](../../../includes/wfd2-md.md)] が見やすくなるように、ウィンドウのサイズを調整します。</span><span class="sxs-lookup"><span data-stu-id="d153f-107">Adjust the size of the window to make it easier to use the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="d153f-108">これを行うには、次のように選択します**MainWindow**デザイナーで表示 f4 キーを押して、**プロパティ**ウィンドウで、し、、**レイアウト**ありますセクションで、設定、**幅。** 600 の値に、**高さ**350 の値にします。</span><span class="sxs-lookup"><span data-stu-id="d153f-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>  
  
3. <span data-ttu-id="d153f-109">選択して、グリッド名を設定、**グリッド**デザイナー内のパネル (内のボックスをクリックして、 **MainWindow**) と設定、**名前**の上部にあるプロパティ、 **プロパティ**ウィンドウを「grid1」.</span><span class="sxs-lookup"><span data-stu-id="d153f-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>  
  
4. <span data-ttu-id="d153f-110">**プロパティ**ウィンドウで、省略記号をクリックします ( **.** ) 横に、`ColumnDefinitions`プロパティを開き、**コレクション エディター**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d153f-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>  
  
5. <span data-ttu-id="d153f-111">**コレクション エディター**ダイアログ ボックスで、をクリックして、**追加**ボタンを 3 回、レイアウトに 3 つの列を挿入します。</span><span class="sxs-lookup"><span data-stu-id="d153f-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="d153f-112">最初の列には、**ツールボックス**、2 番目の列をホストする、 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]、プロパティ インスペクターの 3 番目の列が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d153f-112">The first column will contain the **Toolbox**, the second column will host the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], and the third column will be used for the property inspector.</span></span>  
  
6. <span data-ttu-id="d153f-113">設定、`Width`プロパティの値に、中央の列の"4 \*"。</span><span class="sxs-lookup"><span data-stu-id="d153f-113">Set the `Width` property of the middle column to the value "4\*".</span></span>  
  
7. <span data-ttu-id="d153f-114">**[OK]** をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="d153f-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="d153f-115">次の XAML が MainWindow.xaml ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d153f-115">The following XAML is added to your MainWindow.xaml file:</span></span>  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8. <span data-ttu-id="d153f-116">**ソリューション エクスプ ローラー**で MainWindow.xaml を右クリックし、選択**コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="d153f-116">In **Solution Explorer**, right-click MainWindow.xaml and select **View Code**.</span></span> <span data-ttu-id="d153f-117">次の手順に従ってコードを修正します。</span><span class="sxs-lookup"><span data-stu-id="d153f-117">Modify the code by following these steps:</span></span>  
  
    1. <span data-ttu-id="d153f-118">次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="d153f-118">Add the following namespaces:</span></span>  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2. <span data-ttu-id="d153f-119"><xref:System.Activities.Presentation.WorkflowDesigner> のインスタンスを保持するプライベート メンバー フィールドを宣言するには、次のコードを `MainWindow` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="d153f-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class.</span></span>  
  
        ```csharp  
        public partial class MainWindow : Window  
        {  
            private WorkflowDesigner wd;  
  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
        }  
        ```  
  
    3. <span data-ttu-id="d153f-120">次の `AddDesigner` メソッドを `MainWindow` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="d153f-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="d153f-121">実装のインスタンスを作成する、 <xref:System.Activities.Presentation.WorkflowDesigner>、追加、 <xref:System.Activities.Statements.Sequence> 、アクティビティ、grid1 の中央の列に配置**グリッド**します。</span><span class="sxs-lookup"><span data-stu-id="d153f-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>  
  
        ```csharp  
        private void AddDesigner()  
        {  
            //Create an instance of WorkflowDesigner class.  
            this.wd = new WorkflowDesigner();  
  
            //Place the designer canvas in the middle column of the grid.  
            Grid.SetColumn(this.wd.View, 1);  
  
            //Load a new Sequence as default.  
            this.wd.Load(new Sequence());  
  
            //Add the designer canvas to the grid.  
            grid1.Children.Add(this.wd.View);  
        }  
        ```  
  
    4. <span data-ttu-id="d153f-122">デザイナーのメタデータを登録して、すべてのビルトイン アクティビティにデザイナー サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="d153f-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="d153f-123">こうすることにより、ツールボックスから<xref:System.Activities.Statements.Sequence>の元の [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] アクティビティに、アクティビティをドロップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d153f-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="d153f-124">この操作を行うには、`RegisterMetadata` メソッドを `MainWindow` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="d153f-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class.</span></span>  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         <span data-ttu-id="d153f-125">アクティビティ デザイナーの登録の詳細については、次を参照してください。[方法。カスタム アクティビティ デザイナーを作成](how-to-create-a-custom-activity-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="d153f-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>  
  
    5. <span data-ttu-id="d153f-126">`MainWindow` クラス コンストラクターで、前に宣言したメソッドへの呼び出しを追加して、デザイナー サポートのメタデータを登録し、<xref:System.Activities.Presentation.WorkflowDesigner> を作成します。</span><span class="sxs-lookup"><span data-stu-id="d153f-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>  
  
        ```csharp  
        public MainWindow()  
        {  
            InitializeComponent();  
  
            // Register the metadata  
            RegisterMetadata();  
  
            // Add the WFF Designer  
            AddDesigner();  
        }  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="d153f-127">`RegisterMetadata` メソッドは、<xref:System.Activities.Statements.Sequence> アクティビティを含むビルトイン アクティビティのデザイナーのメタデータを登録します。</span><span class="sxs-lookup"><span data-stu-id="d153f-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="d153f-128">`AddDesigner` メソッドは <xref:System.Activities.Statements.Sequence> アクティビティを使用するので、`RegisterMetadata` メソッドを先に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d153f-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>  
  
9. <span data-ttu-id="d153f-129">F5 キーを押して、ソリューションをビルドおよび実行します。</span><span class="sxs-lookup"><span data-stu-id="d153f-129">Press F5 to build and run the solution.</span></span>  
  
10. <span data-ttu-id="d153f-130">参照してください[タスク 3。ツールボックス ペインと PropertyGrid ペインの作成](task-3-create-the-toolbox-and-propertygrid-panes.md)を追加する方法について**ツールボックス**と**PropertyGrid**を再ホストされたワークフロー デザイナーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d153f-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d153f-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d153f-131">See also</span></span>

- [<span data-ttu-id="d153f-132">ワークフロー デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="d153f-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="d153f-133">タスク 1:新しい Windows Presentation Foundation アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d153f-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="d153f-134">タスク 3:ツールボックス ペインと PropertyGrid ペインを作成します。</span><span class="sxs-lookup"><span data-stu-id="d153f-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)
