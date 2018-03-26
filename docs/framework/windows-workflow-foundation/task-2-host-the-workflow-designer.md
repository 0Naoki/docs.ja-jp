---
title: 'タスク 2: ワークフロー デザイナーのホスティング'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 991f3d25a81e90ab779936c993ec7dd09a71b794
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2018
---
# <a name="task-2-host-the-workflow-designer"></a>タスク 2: ワークフロー デザイナーのホスティング
このトピックでは、[!INCLUDE[wfd1](../../../includes/wfd1-md.md)] アプリケーションで [!INCLUDE[avalon1](../../../includes/avalon1-md.md)]のインスタンスをホストする手順について説明します。  
  
 プロシージャを構成、**グリッド**、デザイナーが含まれるコントロールのインスタンスをプログラムで作成する、 <xref:System.Activities.Presentation.WorkflowDesigner> 、既定値を格納している<xref:System.Activities.Statements.Sequence>活動が提供するデザイナーのメタデータを登録すべての組み込みのアクティビティとホスト用のデザイナーのサポート、[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]で、[!INCLUDE[avalon2](../../../includes/avalon2-md.md)]アプリケーションです。  
  
### <a name="to-host-the-workflow-designer"></a>ワークフロー デザイナーをホストするには  
  
1.  開く、HostingApplication プロジェクトので作成した[タスク 1: 新しい Windows Presentation Foundation アプリケーションを作成する](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)です。  
  
2.  [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] が見やすくなるように、ウィンドウのサイズを調整します。 これを行うには、次のように選択します**MainWindow**デザイナーで、f4 キーを表示、**プロパティ**ウィンドウ、および、、**レイアウト**ありますセクションで、設定、**幅。** 600 の値を**高さ**350 の値にします。  
  
3.  選択すると、グリッド名を設定、**グリッド**デザイナーでのパネル (内のボックスをクリックして、 **MainWindow**) と設定、**名前**の上部にあるプロパティ、 **プロパティ**を「grid1」ウィンドウです。  
  
4.  **プロパティ**ウィンドウで、省略記号ボタン (**.**) の横に、`ColumnDefinitions`プロパティを開くには、**コレクション エディター**  ダイアログ ボックス。  
  
5.  **コレクション エディター**  ダイアログ ボックスをクリックして、**追加**ボタンを 3 回、レイアウトに 3 つの列を挿入します。 最初の列に格納される、**ツールボックス**、2 番目の列をホストする、 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]、プロパティ インスペクターの 3 番目の列に使用されます。  
  
6.  設定、`Width`プロパティ値を中央の列の"4 *"です。  
  
7.  **[OK]** をクリックして変更を保存します。 次の XAML が MainWindow.xaml ファイルに追加されます。  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8.  **ソリューション エクスプ ローラー**、MainWindow.xaml を右クリックし **コードの表示**です。 次の手順に従ってコードを修正します。  
  
    1.  次の名前空間を追加します。  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2.  <xref:System.Activities.Presentation.WorkflowDesigner> のインスタンスを保持するプライベート メンバー フィールドを宣言するには、次のコードを `MainWindow` クラスに追加します。  
  
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
  
    3.  次の `AddDesigner` メソッドを `MainWindow` クラスに追加します。 実装のインスタンスを作成する、 <xref:System.Activities.Presentation.WorkflowDesigner>、追加、 <xref:System.Activities.Statements.Sequence> 、活動して、grid1 の中央の列に配置**グリッド**です。  
  
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
  
    4.  デザイナーのメタデータを登録して、すべてのビルトイン アクティビティにデザイナー サポートを追加します。 こうすることにより、ツールボックスから<xref:System.Activities.Statements.Sequence>の元の [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] アクティビティに、アクティビティをドロップできるようになります。 この操作を行うには、`RegisterMetadata` メソッドを `MainWindow` クラスに追加します。  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         [!INCLUDE[crabout](../../../includes/crabout-md.md)] アクティビティ デザイナーを登録するを参照してください[する方法: カスタム アクティビティ デザイナーを作成](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md)です。  
  
    5.  `MainWindow` クラス コンストラクターで、前に宣言したメソッドへの呼び出しを追加して、デザイナー サポートのメタデータを登録し、<xref:System.Activities.Presentation.WorkflowDesigner> を作成します。  
  
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
        >  `RegisterMetadata` メソッドは、<xref:System.Activities.Statements.Sequence> アクティビティを含むビルトイン アクティビティのデザイナーのメタデータを登録します。 `AddDesigner` メソッドは <xref:System.Activities.Statements.Sequence> アクティビティを使用するので、`RegisterMetadata` メソッドを先に呼び出す必要があります。  
  
9. F5 キーを押して、ソリューションをビルドおよび実行します。  
  
10. 参照してください[タスク 3: ツールボックス ペインと PropertyGrid ペインを作成する](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)を追加する方法について**ツールボックス**と**PropertyGrid**再ホストされたワークフロー デザイナーにサポートします。  
  
## <a name="see-also"></a>関連項目  
 [ワークフロー デザイナーのホスト変更](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [タスク 1: 新しい Windows Presentation Foundation アプリケーションの作成](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
 [タスク 3: ツールボックス ペインと PropertyGrid ペインの作成](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)
