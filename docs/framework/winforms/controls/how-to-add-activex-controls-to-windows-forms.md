---
title: '方法 : Windows フォームに ActiveX コントロールを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 7d6514c679187e9ec193f6dda8336c8bd56fac81
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078422"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>方法 : Windows フォームに ActiveX コントロールを追加する
Windows フォーム コントロールをホストするには、Windows フォーム デザイナーが最適化され、中には、Windows フォームで ActiveX コントロールも記述できます。  
  
> [!CAUTION]
>  ActiveX コントロールを追加することがある場合に、Windows フォームのパフォーマンスの制限があります。  
  
 ActiveX コントロールをフォームに追加する前に、ツールボックスに追加する必要があります。 詳細については、次を参照してください。 [COM コンポーネント、ツールボックスのカスタマイズ ダイアログ ボックス](https://msdn.microsoft.com/library/171333f3-f207-4e02-bbdc-17862556212c)します。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Windows フォームに ActiveX コントロールを追加するには  
  
-   ツールボックスにコントロールをダブルクリックします。  
  
     Visual Studio では、プロジェクトのコントロールにすべての参照を追加します。 Windows フォームで ActiveX コントロールを使用する場合に留意すべき点の詳細については、次を参照してください。 [Windows フォームで ActiveX コントロールをホストしている場合の考慮事項](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md)します。  
  
    > [!NOTE]
    >  Windows フォーム ActiveX コントロール インポーター (AxImp.exe) は、ActiveX のダイナミック リンク ライブラリのインポート時に予想よりも、別の種類のイベント引数を作成します。 AxImp.exe によって作成された引数は、次のような: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`、`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`が必要です。 この不規則性から正常に機能して、コードが回避しないことに注意します。 詳細については、次を参照してください。 [Windows フォーム ActiveX コントロール インポーター (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)します。  
  
## <a name="see-also"></a>関連項目  
 [Windows フォーム コントロール](../../../../docs/framework/winforms/controls/index.md)  
 [各言語およびライブラリにおける、コントロールとプログラミング可能オブジェクトの比較](https://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [方法: Windows フォームにコントロールを追加する](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Windows フォームでのコントロールの配置](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [各 Windows フォーム コントロールのラベル設定とショートカットの作成](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows フォームで使用するコントロール](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows フォーム コントロールの機能別一覧](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
