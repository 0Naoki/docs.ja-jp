---
title: タスク 3:ツールボックス ペインと PropertyGrid ペインの作成
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 402a25c1cb82c245afa94f58cefc180515622ea9
ms.sourcegitcommit: 992f80328b51b165051c42ff5330788627abe973
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "72275864"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>タスク 3:ツールボックス ペインと PropertyGrid ペインの作成

このタスクでは、**ツールボックス**ペインと**PropertyGrid**ウィンドウを作成し、再ホストされた [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] に追加します。

参考として、このトピックの最後に、ワークフローデザイナーシリーズのトピックの再[ホスト](rehosting-the-workflow-designer.md)に関する3つのタスクを完了した後に MainWindow.xaml.cs ファイルに含まれている必要があるコードについて説明します。

## <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>ツールボックスを作成し、グリッドに追加するには

1. 「@No__t-0Task 2:」で説明されている手順に従って、取得した HostingApplication プロジェクトを開きます。ワークフローデザイナー @ no__t-0 をホストします。

2. **ソリューションエクスプローラー**ペインで、 *mainwindow.xaml*ファイルを右クリックし、 **[コードの表示]** を選択します。

3. @No__t-2 を作成し、新しい**ツールボックス**カテゴリを**ツールボックス**に追加して、<xref:System.Activities.Statements.Assign> および <xref:System.Activities.Statements.Sequence> アクティビティの種類をそのカテゴリに割り当てる、`MainWindow` クラスに `GetToolboxControl` メソッドを追加します。

    ```csharp
    private ToolboxControl GetToolboxControl()
    {
        // Create the ToolBoxControl.
        var ctrl = new ToolboxControl();

        // Create a category.
        var category = new ToolboxCategory("category1");

        // Create Toolbox items.
        var tool1 =
            new ToolboxItemWrapper("System.Activities.Statements.Assign",
            typeof(Assign).Assembly.FullName, null, "Assign");

        var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
            typeof(Sequence).Assembly.FullName, null, "Sequence");

        // Add the Toolbox items to the category.
        category.Add(tool1);
        category.Add(tool2);

        // Add the category to the ToolBox control.
        ctrl.Categories.Add(category);
        return ctrl;
    }
    ```

4. グリッドの左側の列に**ツールボックス**を配置する `MainWindow` クラスにプライベート `AddToolbox` メソッドを追加します。

    ```csharp
    private void AddToolBox()
    {
        ToolboxControl tc = GetToolboxControl();
        Grid.SetColumn(tc, 0);
        grid1.Children.Add(tc);
    }
    ```

5. 次のコードに示すように、`MainWindow()` クラスコンストラクターに `AddToolBox` メソッドの呼び出しを追加します。

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();

        this.AddToolBox();
    }
    ```

6. <kbd>F5</kbd>キーを押して、ソリューションをビルドして実行します。 @No__t-1 と @no__t 2 つのアクティビティを含む**ツールボックス**が表示されます。

## <a name="to-create-the-propertygrid"></a>PropertyGrid を作成するには

1. **ソリューションエクスプローラー**ペインで、 *mainwindow.xaml*ファイルを右クリックし、 **[コードの表示]** を選択します。

2. @No__t-0 メソッドを `MainWindow` クラスに追加して、グリッドの右端の列に **[PropertyGrid]** ペインを配置します。

    ```csharp
    private void AddPropertyInspector()
    {
        Grid.SetColumn(wd.PropertyInspectorView, 2);
        grid1.Children.Add(wd.PropertyInspectorView);
    }
    ```

3. 次のコードに示すように、`MainWindow()` クラスコンストラクターに `AddPropertyInspector` メソッドの呼び出しを追加します。

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

4. <kbd>F5</kbd>キーを押して、ソリューションをビルドして実行します。 **[ツールボックス]** 、ワークフローデザインキャンバス、および  **[PropertyGrid]** の各ウィンドウがすべて表示されます。また、@no__t 2 アクティビティまたは @no__t 3 アクティビティをデザインキャンバスにドラッグすると、強調表示されたアクティビティに応じてプロパティグリッドが更新されます。

## <a name="example"></a>例

*MainWindow.xaml.cs*ファイルには、次のコードが含まれています。

```csharp
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
// dlls added.
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
            // Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            // Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            // Load a new Sequence as default.
            this.wd.Load(new Sequence());

            // Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }

        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }

        private ToolboxControl GetToolboxControl()
        {
            // Create the ToolBoxControl.
            var ctrl = new ToolboxControl();

            // Create a category.
            var category = new ToolboxCategory("category1");

            // Create Toolbox items.
            var tool1 =
                new ToolboxItemWrapper("System.Activities.Statements.Assign",
                typeof(Assign).Assembly.FullName, null, "Assign");

            var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
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

- [ワークフロー デザイナーのホスト変更](rehosting-the-workflow-designer.md)
- [Task 1:新しい Windows Presentation Foundation アプリケーションの作成 @ no__t-0
- [Task 2:ワークフローデザイナー @ no__t をホストします。
