---
title: '方法: Toolstrippanel を結合します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
ms.openlocfilehash: cebfcb417dc011ed8990e9d536cd165c2a92cb68
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260739"
---
# <a name="how-to-join-toolstrippanels"></a>方法: Toolstrippanel を結合します。
実行時に <xref:System.Windows.Forms.ToolStrip> コントロールを <xref:System.Windows.Forms.ToolStripPanel> に結合でき、これによりマルチ ドキュメント インターフェイス (MDI) アプリケーションの柔軟性を提供します。  
  
## <a name="example"></a>例  
 次のコード例は、<xref:System.Windows.Forms.ToolStrip> コントロールを <xref:System.Windows.Forms.ToolStripPanel> に結合する方法を示します。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
-   System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。  
  
 コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。 新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- [Toolstrippanel を MDI で使用します。](../../../../docs/framework/winforms/controls/how-to-use-toolstrippanels-for-mdi.md)
