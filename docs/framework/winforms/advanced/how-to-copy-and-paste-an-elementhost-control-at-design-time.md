---
title: '方法 : デザイン時に ElementHost コントロールをコピーして貼り付ける'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 43ebe50497df97511925bd2e413ab5b5988b7f57
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210920"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>方法 : デザイン時に ElementHost コントロールをコピーして貼り付ける
この手順では、Windows フォーム上の Windows Presentation Foundation (WPF) コントロールをコピーする方法を示します。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a>コピーしてデザイン時に ElementHost コントロールを貼り付ける  
  
1.  新しい WPF 追加<xref:System.Windows.Controls.UserControl>を Windows フォーム プロジェクトにします。 コントロール型の既定の名前である `UserControl1.xaml` を使用します。 詳細については、次を参照してください。[チュートリアル: 新しい WPF コンテンツの作成には、デザイン時に Windows フォーム](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)します。  
  
2.  **プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティの`UserControl1`に`200`します。  
  
3.  <xref:System.Windows.Controls.Control.Background%2A> プロパティの値を `Blue` に設定します。  
  
4.  プロジェクトをビルドします。  
  
5.  Windows フォーム デザイナーで `Form1` を開きます。  
  
6.  **ツールボックス**のインスタンスをドラッグ`UserControl1`フォーム上にします。  
  
     `UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。  
  
7.  `elementHost1` を選択して、CTRL + C キーを押してクリップボードにコピーします。  
  
8.  コピーしたコントロールをフォームに貼り付けるには、CTRL + V キーを押します。  
  
     新しい<xref:System.Windows.Forms.Integration.ElementHost>という名前のコントロール`elementHost2`フォーム上に作成されます。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [チュートリアル: ElementHost コントロールの別の Windows フォームへのコピーと貼り付け](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [移行と相互運用性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [WPF コントロールの使用](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [Visual Studio で XAML をデザインする](/visualstudio/designers/designing-xaml-in-visual-studio)
