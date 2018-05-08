---
title: 'タスク 3: ツールボックス ペインと PropertyGrid ペインの作成'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 9bfce22e9de1d6115cb88daddcd2dca355b6bae8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>タスク 3: ツールボックス ペインと PropertyGrid ペインの作成
このタスクでは、作成、**ツールボックス**と**PropertyGrid**ペインに、再ホストされた追加[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]です。  
  
 リファレンスについては、コードを MainWindow.xaml.cs ファイルで、3 つの完了後にする必要がありますのタスクで、[ワークフロー デザイナーを再ホスト](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)一連のトピックは、このトピックの最後で提供されます。  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>ツールボックスを作成し、グリッドに追加するには  
  
1.  説明されている手順に従って、取得した HostingApplication プロジェクトを開く[タスク 2: ワークフロー デザイナーのホスティング](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)です。  
  
2.  **ソリューション エクスプ ローラー**  ウィンドウで、MainWindow.xaml ファイルを右クリックし、選択**コードの表示**です。  
  
3.  追加、`GetToolboxControl`メソッドを`MainWindow`を作成するクラス、 <xref:System.Activities.Presentation.Toolbox.ToolboxControl>、新しく追加**ツールボックス**カテゴリ、**ツールボックス**、し、割り当てます、<xref:System.Activities.Statements.Assign>と<xref:System.Activities.Statements.Sequence>アクティビティの種類をそのカテゴリ。  
  
    ```csharp  
    private ToolboxControl GetToolboxControl()  
    {  
        // Create the ToolBoxControl.  
        ToolboxControl ctrl = new ToolboxControl();  
  
        // Create a category.  
        ToolboxCategory category = new ToolboxCategory("category1");  
  
        // Create Toolbox items.  
        ToolboxItemWrapper tool1 =   
            new ToolboxItemWrapper("System.Activities.Statements.Assign",   
            typeof(Assign).Assembly.FullName, null, "Assign");  
  
        ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",   
            typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
        // Add the Toolbox items to the category.  
        category.Add(tool1);  
        category.Add(tool2);  
  
        // Add the category to the ToolBox control.  
        ctrl.Categories.Add(category);  
        return ctrl;  
    }  
    ```  
  
4.  プライベートの追加`AddToolbox`メソッドを`MainWindow`配置クラス、**ツールボックス**グリッドで左の列にします。  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5.  次のコードのように、`AddToolBox` クラス コンストラクターに `MainWindow()` メソッドへの呼び出しを追加します。  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6.  F5 キーを押して、ソリューションをビルドおよび実行します。 **ツールボックス**を含む、<xref:System.Activities.Statements.Assign>と<xref:System.Activities.Statements.Sequence>アクティビティを表示する必要があります。  
  
### <a name="to-create-the-propertygrid"></a>PropertyGrid を作成するには  
  
1.  **ソリューション エクスプ ローラー**  ウィンドウで、MainWindow.xaml ファイルを右クリックし、選択**コードの表示**です。  
  
2.  追加、`AddPropertyInspector`メソッドを`MainWindow`を配置するクラス、 **PropertyGrid**ウィンドウ、グリッドで一番右の列にします。  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3.  次のコードのように、`AddPropertyInspector` クラス コンストラクターに `MainWindow()` メソッドへの呼び出しを追加します。  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
        this.AddToolBox();  
  
        this.AddPropertyInspector();   
    }  
    ```  
  
4.  F5 キーを押して、ソリューションをビルドおよび実行します。 **ツールボックス**、ワークフロー デザイン キャンバス、および**PropertyGrid**ペインがすべて表示されます、およびドラッグすると、<xref:System.Activities.Statements.Assign>アクティビティまたは<xref:System.Activities.Statements.Sequence>アクティビティをデザイン キャンバスには強調表示されているアクティビティに応じてプロパティ グリッドが更新する必要があります。  
  
## <a name="example"></a>例  
 MainWindow.xaml.cs ファイルに次のコードが含まれます。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
//dlls added  
using System.Activities;  
using System.Activities.Core.Presentation;  
using System.Activities.Presentation;  
using System.Activities.Presentation.Metadata;  
using System.Activities.Presentation.Toolbox;  
using System.Activities.Statements;  
using System.ComponentModel;  
  
namespace HostingApplication  
{  
    /// <summary>  
    /// Interaction logic for MainWindow.xaml  
    /// </summary>  
    public partial class MainWindow : Window  
    {  
        private WorkflowDesigner wd;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
            RegisterMetadata();  
            AddDesigner();  
            this.AddToolBox();  
            this.AddPropertyInspector();  
        }  
  
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
  
        private void RegisterMetadata()  
        {  
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        private ToolboxControl GetToolboxControl()  
        {  
            // Create the ToolBoxControl.  
            ToolboxControl ctrl = new ToolboxControl();  
  
            // Create a category.  
            ToolboxCategory category = new ToolboxCategory("category1");  
  
            // Create Toolbox items.  
            ToolboxItemWrapper tool1 =  
                new ToolboxItemWrapper("System.Activities.Statements.Assign",  
                typeof(Assign).Assembly.FullName, null, "Assign");  
  
            ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",  
                typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
            // Add the Toolbox items to the category.  
            category.Add(tool1);  
            category.Add(tool2);  
  
            // Add the category to the ToolBox control.  
            ctrl.Categories.Add(category);  
            return ctrl;  
        }  
  
        private void AddToolBox()  
        {  
            ToolboxControl tc = GetToolboxControl();  
            Grid.SetColumn(tc, 0);  
            grid1.Children.Add(tc);  
        }  
  
        private void AddPropertyInspector()  
        {  
            Grid.SetColumn(wd.PropertyInspectorView, 2);  
            grid1.Children.Add(wd.PropertyInspectorView);  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ワークフロー デザイナーのホスト変更](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [タスク 1: 新しい Windows Presentation Foundation アプリケーションの作成](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
 [タスク 2: ワークフロー デザイナーのホスティング](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
