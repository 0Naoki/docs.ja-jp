---
title: 'チュートリアル: デザイン時のホストされている WPF 要素のプロパティの変更'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: 15cab9266af5840aa4b37a62b71bd5010b7a859a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741021"
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a>チュートリアル: デザイン時のホストされている WPF 要素のプロパティの変更
このチュートリアルでは、Windows フォームでホストされている Windows Presentation Foundation (WPF) コントロールのプロパティ値を変更する方法について説明します。  
  
 このチュートリアルでは次のタスクを実行します。  
  
-   プロジェクトを作成する。  
  
-   WPF コントロールを作成する。  
  
-   Windows フォームで WPF コントロールをホストする。  
  
-   Visual Studio の WPF デザイナーを使用してプロパティの値を変更する。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを実行するには、次のコンポーネントが必要です。  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]。  
  
## <a name="creating-the-project"></a>プロジェクトの作成  
 まず、Windows フォーム プロジェクトを作成します。  
  
> [!NOTE]
>  WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。  
  
#### <a name="to-create-the-project"></a>プロジェクトを作成するには  
  
-   Visual Basic または Visual c# のという名前で新しい Windows フォーム アプリケーション プロジェクトを作成する`WpfHost`します。  
  
## <a name="creating-the-wpf-control"></a>WPF コントロールの作成  
 プロジェクトに WPF コントロール型を追加したら、フォーム状に配置できます。  
  
#### <a name="to-create-wpf-controls"></a>WPF コントロールを作成するには  
  
1.  新しい WPF <xref:System.Windows.Controls.UserControl> をプロジェクトに追加します。 コントロール型の既定の名前である `UserControl1.xaml` を使用します。 詳細については、次を参照してください。[チュートリアル: 新しい WPF コンテンツの作成には、デザイン時に Windows フォーム](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)します。  
  
2.  **プロパティ**ウィンドウで、設定の値、<xref:System.Windows.Controls.Control.Background%2A>プロパティを`Blue`します。  
  
3.  プロジェクトをビルドします。  
  
## <a name="changing-property-values-on-the-wpf-control"></a>WPF コントロールのプロパティの値を変更する  
 <xref:System.Windows.Forms.Integration.ElementHost> スマート タグにより、WPF デザイナーを使用して、ホストされている WPF の内容のプロパティを簡単に変更できます。  
  
#### <a name="to-host-a-wpf-control"></a>WPF コントロールをホストするには  
  
1.  Windows フォーム デザイナーで `Form1` を開きます。  
  
2.  **ツールボックス**で、 **WPF ユーザー コントロール** タブで、ダブルクリックして`UserControl1`のインスタンスを作成する`UserControl1`フォームにします。  
  
     `UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。  
  
3.  **ElementHost タスク**スマート タグ パネルで、**ホストされているコンテンツの編集**します。  
  
     UserControl1.xaml が WPF デザイナーで開きます。  
  
4.  **プロパティ**ウィンドウで、設定の値、<xref:System.Windows.Controls.Control.Background%2A>プロパティを`Red`します。  
  
5.  プロジェクトをリビルドします。  
  
6.  Windows フォーム デザイナーで `Form1` を開きます。  
  
     `UserControl1` のインスタンスが赤の背景になります。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [方法: TableLayoutPanel コントロールで子コントロールを固定およびドッキングする](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [方法: デザイン時にフォームの端に合わせてコントロールを配置する](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [チュートリアル: スナップ線を使用した Windows フォーム上のコントロールの配置](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [移行と相互運用性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [WPF コントロールの使用](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [Visual Studio で XAML をデザインする](/visualstudio/designers/designing-xaml-in-visual-studio)
