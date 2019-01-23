---
title: '方法: によって表示されるテキストを設定、Windows フォーム デザイナーを使用してコントロール'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: cea2bcdb973e1deb5e0e6cf7fcc31b7c084dc446
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510586"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a>方法: によって表示されるテキストを設定、Windows フォーム デザイナーを使用してコントロール
Windows フォーム コントロールは、通常、コントロールの主な機能に関連するいくつかのテキストを表示します。 たとえば、<xref:System.Windows.Forms.Button>コントロールには、通常、ボタンがクリックされたときに実行するアクションを示すキャプションが表示されます。 すべてのコントロールに対して、<xref:System.Windows.Forms.Control.Text%2A> プロパティを使用してテキストを設定または返すことができます。 <xref:System.Windows.Forms.Control.Font%2A> プロパティを使用して、フォントを変更することができます。  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a>テキストとデザイナーを使用したフォントを設定するには  
  
1.  [プロパティ] ウィンドウで次のように設定します。、<xref:System.Windows.Forms.Control.Text%2A>適切な文字列をコントロールのプロパティ。  
  
     下線付きのショートカット キーを作成するアンパサンドが含まれています (&) は、ショートカット キーとなる文字の前にします。  
  
2.  [プロパティ] ウィンドウで、省略記号ボタンをクリックします。 (![VisualStudioEllipsesButton スクリーン ショット](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 横に、<xref:System.Windows.Forms.Control.Font%2A>プロパティ。  
  
     標準的なフォント ダイアログ ボックスで、フォント、フォント スタイル、サイズ、(取り消し線、下線) などの効果とスクリプトを選択します。  
  
## <a name="see-also"></a>関連項目
- [方法: によって表示されるテキストを設定、Windows フォーム コントロール](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [フォントとテキストの使用](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [各 Windows フォーム コントロールのラベル設定とショートカットの作成](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
