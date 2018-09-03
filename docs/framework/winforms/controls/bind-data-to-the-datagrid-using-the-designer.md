---
title: '方法 : デザイナーを使用してデータを Windows フォーム DataGridView コントロールにバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 1c2b3d9cb9664fccc28ce32889491363807a6560
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485756"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>方法 : デザイナーを使用してデータを Windows フォーム DataGridView コントロールにバインドする
デザイナーを使用して、接続、<xref:System.Windows.Forms.DataGridView>データベース、ビジネス オブジェクト、Web サービスなど、いくつかの異なる種類のデータ ソースへのコントロール。 デザイナーを使用してデータ ソースにコントロールをバインドすると、コントロールに自動的にバインドを<xref:System.Windows.Forms.BindingSource>コンポーネントをデータ ソースを表します。 さらに、データ ソースによって提供されるスキーマ情報に対応するように、このコントロールの列が自動的に生成されます。  
  
 列が生成された後に、ニーズに合わせて列を変更できます。 たとえば、表示に関係のない列を削除または非表示にしたり、列の順序を変更したり、列の型を変更したりすることができます。 列の変更の詳細については、「関連項目」セクションの各トピックを参照してください。  
  
 複数をバインドすることもできます。<xref:System.Windows.Forms.DataGridView>関連テーブルのマスター/詳細リレーションシップを作成するコントロール。 この構成では、1 つのコントロールに親テーブルが表示され、別のコントロールには親テーブルの現在の行に関連する子テーブルの行のみが表示されます。 詳細については、「[方法: 関連するデータを Windows フォーム アプリケーションに表示する](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)」を参照してください。  
  
 次の手順が必要です、 **Windows アプリケーション**を含むフォームを使用してプロジェクトを<xref:System.Windows.Forms.DataGridView>コントロールまたはマスター/詳細リレーションシップの 2 つのコントロール。 このようなプロジェクトを開始する方法については、「[方法 : Windows アプリケーション プロジェクトを作成する](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)」と「[方法 : Windows フォームにコントロールを追加する](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)」を参照してください。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。  
  
### <a name="to-bind-the-control-to-a-data-source"></a>コントロールをデータ ソースにバインドするには  
  
1.  スマート タグ グリフをクリックします (![スマート タグ グリフ](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) の右上隅で、<xref:System.Windows.Forms.DataGridView>コントロール。  
  
2.  **[データ ソースの選択]** オプションのドロップダウン矢印をクリックします。  
  
3.  プロジェクトにまだデータ ソースがない場合は、**[プロジェクト データ ソースの追加]** をクリックし、ウィザードに示される手順に従います。  
  
     詳細については、「[データ ソース構成ウィザード](https://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)」を参照してください。 **[データ ソースの選択]** ドロップダウン ウィンドウに新しいデータ ソースが表示されます。 新しいデータ ソースに含まれるのが単一データベース テーブルなど、1 つのメンバーのみの場合、コントロールはそのメンバーに自動的にバインドされます。 それ以外の場合は、次の手順に進みます。  
  
4.  展開されていない場合は **[他のデータ ソース]** ノードと **[プロジェクト データ ソース]** ノードを展開し、コントロールをバインドするデータ ソースを選択します。  
  
5.  データ ソースには、複数のメンバーが含まれている場合などを作成した場合、<xref:System.Data.DataSet?displayProperty=nameWithType>複数のテーブルを格納している、データ ソースを展開し、特定のメンバーにバインドします。  
  
6.  マスター/詳細リレーションシップを作成する、**データ ソースの選択**を 2 番目のドロップダウン ウィンドウ<xref:System.Windows.Forms.DataGridView>コントロールを展開し、<xref:System.Windows.Forms.BindingSource>親テーブルの作成し、一覧から関連する子テーブルを選択表示されます。  
  
    > [!NOTE]
    >  プロジェクトにデータ ソースが既にある場合は、**[データソース]** ウィンドウを使用してデータ フォームを作成することもできます。 詳細については、「[[データ ソース] ウィンドウ](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [方法 : データベース内のデータに接続する](https://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の順序を変更する](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [方法: デザイナーを使用して Windows フォーム DataGridView 列の種類を変更する](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を固定する](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を非表示にする](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [方法: デザイナーを使用して Windows フォームの DataGridView コントロールで列を読み取り専用にする](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [方法: Windows アプリケーション プロジェクトを作成](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [方法: Windows フォームにコントロールを追加する](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [データ ソース ウィンドウ](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [方法: 関連するデータを Windows フォーム アプリケーションに表示する](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
