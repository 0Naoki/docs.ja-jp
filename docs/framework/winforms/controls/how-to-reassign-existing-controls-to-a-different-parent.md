---
title: "方法 : 既存のコントロールを別の親に再配置する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26998c002591850c0af3c265ae88b10657343787
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>方法 : 既存のコントロールを別の親に再配置する
フォームに存在するコントロールを新しいコンテナー コントロールに割り当てることができます。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a>既存のコントロールを別の親に再配置するには  
  
1.  <xref:System.Windows.Forms.Button> [ツールボックス] **から 3 つの** コントロールをフォームにドラッグします。  
  
     これらを互いに近づけて配置しますが、整列はさせません。  
  
2.  **[ツールボックス]**で <xref:System.Windows.Forms.FlowLayoutPanel> コントロール アイコンをクリックします。  
  
     アイコンはフォームにドラッグしないでください。  
  
3.  マウス ポインターを 3 つの <xref:System.Windows.Forms.Button> コントロールに近づけます。  
  
     ポインターが <xref:System.Windows.Forms.FlowLayoutPanel> コントロール アイコンが付いた十字カーソルに変わります。  
  
4.  マウス ボタンを押したままにします。  
  
5.  マウス ポインターをドラッグして、 <xref:System.Windows.Forms.FlowLayoutPanel> コントロールのアウトラインを描画します。  
  
6.  3 つの <xref:System.Windows.Forms.Button> コントロールを囲むようにアウトラインを描画します。  
  
7.  マウスのボタンを離します。  
  
     これで、3 つの <xref:System.Windows.Forms.Button> コントロールが <xref:System.Windows.Forms.FlowLayoutPanel> コントロールに挿入されました。  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Windows フォームでのコントロールの配置](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [チュートリアル: スナップ線を使用した Windows フォーム上のコントロールの配置](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
