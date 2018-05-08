---
title: 'チュートリアル: WPF コンテンツへのスタイルの適用'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: d02e48daad705b29cb7e179417f665c34857896e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-styling-wpf-content"></a>チュートリアル: WPF コンテンツへのスタイルの適用
このチュートリアルでは、Windows フォームでホストされている Windows Presentation Foundation (WPF) コントロールにスタイルを適用する方法について説明します。  
  
 このチュートリアルでは次のタスクを行います。  
  
-   プロジェクトを作成します。  
  
-   WPF コントロール型を作成します。  
  
-   WPF コントロールにスタイルを適用します。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを実行するには、次のコンポーネントが必要です。  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]。  
  
## <a name="creating-the-project"></a>プロジェクトの作成  
 まず、Windows フォーム プロジェクトを作成します。  
  
> [!NOTE]
>  WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。  
  
#### <a name="to-create-the-project"></a>プロジェクトを作成するには  
  
-   Visual Basic または Visual c# のという名前で新しい Windows フォーム アプリケーション プロジェクトを作成`StylingWpfContent`です。  
  
## <a name="creating-the-wpf-control-types"></a>WPF コントロール型の作成  
 プロジェクトに追加した WPF コントロール型は、<xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストできます。  
  
#### <a name="to-create-wpf-control-types"></a>WPF コントロール型を作成するには  
  
1.  新しい WPF <xref:System.Windows.Controls.UserControl> プロジェクトをソリューションに追加します。 コントロール型の既定の名前である `UserControl1.xaml` を使用します。 詳細については、次を参照してください。[チュートリアル: 新しい WPF コンテンツの作成デザイン時に Windows フォームで](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)です。  
  
2.  デザイン ビューで `UserControl1` が選択されていることを確認します。 詳細については、次を参照してください。[する方法: Select およびデザイン サーフェイス上の要素の移動](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)です。  
  
3.  **プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ`200`です。  
  
4.  追加、<xref:System.Windows.Controls.Button?displayProperty=nameWithType>コントロールを<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.ContentControl.Content%2A>プロパティを**キャンセル**です。  
  
5.  1 秒あたりの追加<xref:System.Windows.Controls.Button?displayProperty=nameWithType>に制御を<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.ContentControl.Content%2A>プロパティを**OK**です。  
  
6.  プロジェクトをビルドします。  
  
## <a name="applying-a-style-to-a-wpf-control"></a>WPF コントロールへのスタイルの適用  
 さまざまなスタイルを WPF コントロールに適用することで、外観や動作を変えることができます。  
  
#### <a name="to-apply-a-style-to-a-wpf-control"></a>WPF コントロールにスタイルを適用するには  
  
1.  Windows フォーム デザイナーで `Form1` を開きます。  
  
2.  **ツールボックス**をダブルクリックして`UserControl1`のインスタンスを作成する`UserControl1`フォームにします。  
  
     `UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。  
  
3.  スマート タグ パネルで`elementHost1`をクリックして**ホストされているコンテンツの編集**ドロップダウン リストからです。  
  
     `UserControl1` が [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] で開きます。  
  
4.  XAML ビューで、次の XAML を `<UserControl>` の開始タグの後に挿入します。  
  
     この XAML は、明暗のあるグラデーション境界を持つグラデーションを作成します。 このコントロールをクリックすると、グラデーションが変わり、ボタンを押したような外観が生成されます。 詳しくは、「 [スタイルとテンプレート](../../../../docs/framework/wpf/controls/styling-and-templating.md)」をご覧ください。  
  
```xaml  
<UserControl.Resources>  
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#FFF" Offset="0.0"/>  
        <GradientStop Color="#CCC" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#BBB" Offset="0.0"/>  
        <GradientStop Color="#EEE" Offset="0.1"/>  
        <GradientStop Color="#EEE" Offset="0.9"/>  
        <GradientStop Color="#FFF" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#444" Offset="0.0"/>  
        <GradientStop Color="#888" Offset="1.0"/>  
    </LinearGradientBrush>  
  
    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>  
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>  
        <Setter Property="Template">  
            <Setter.Value>  
                <ControlTemplate TargetType="{x:Type Button}">  
                    <Grid x:Name="Grid">  
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>  
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>  
                    </Grid>  
                    <ControlTemplate.Triggers>  
                        <Trigger Property="IsPressed" Value="true">  
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>  
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>  
                        </Trigger>  
                    </ControlTemplate.Triggers>  
                </ControlTemplate>  
            </Setter.Value>  
        </Setter>  
    </Style>  
</UserControl.Resources>  
```  
  
1.  [Cancel] ボタンの `<Button>` タグに次の XAML を挿入することで、前の手順で定義した `SimpleButton` スタイルを [Cancel] ボタンに適用します。  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     ボタン宣言は次の XAML のようになります。  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1.  プロジェクトをビルドします。  
  
2.  Windows フォーム デザイナーで `Form1` を開きます。  
  
3.  新しいスタイルが Button コントロールに適用されます。  
  
4.  **デバッグ**メニューの [**デバッグの開始]** アプリケーションを実行します。  
  
5.  [OK] ボタンと [Cancel] ボタンをクリックして、違いを確認します。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [移行と相互運用性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [WPF コントロールの使用](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF デザイナー](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [XAML の概要 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [スタイルとテンプレート](../../../../docs/framework/wpf/controls/styling-and-templating.md)
