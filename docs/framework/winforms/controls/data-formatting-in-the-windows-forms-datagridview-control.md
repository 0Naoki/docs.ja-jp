---
title: Windows フォーム DataGridView コントロールでのデータの書式設定
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: 0016b87add6f20223bdeda72f10ac94b74ec9fcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737859"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールでのデータの書式設定
<xref:System.Windows.Forms.DataGridView>コントロールがセルの値と、親列に表示するデータ型間の自動変換を提供します。 たとえば、テキスト ボックスの列は、日付、時刻、数、および列挙の値の文字列形式を表示し、ユーザーが入力した文字列値をデータ ストアに必要な種類に変換します。  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>DataGridViewCellStyle クラスを使用して書式設定  
 <xref:System.Windows.Forms.DataGridView>によってセル値の基本的なデータの書式設定コントロールを提供します、<xref:System.Windows.Forms.DataGridViewCellStyle>クラス。 使用することができます、<xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>プロパティで説明されている書式指定子を使用して現在の既定のカルチャの形式の日付、時刻、数、および列挙値を[型の書式設定](../../../../docs/standard/base-types/formatting-types.md)します。 これらの値を使用して特定のカルチャの書式を設定することもできます、<xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>プロパティ。 指定した形式は、データを表示して、ユーザーが指定された形式で入力したデータの解析に使用されます。  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>クラス wordwrap、テキストの配置、およびデータベースの null 値のカスタム表示の追加の書式設定プロパティを提供します。 詳細については、「[方法 :書式設定データの Windows フォーム DataGridView コントロール](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)します。  
  
## <a name="formatting-with-the-cellformatting-event"></a>CellFormatting イベントに書式設定  
 基本的な書式設定しても、ニーズが満たしていない場合は、カスタムのデータのハンドラーで書式設定を行うことができます、<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>イベント。 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>ハンドラーに渡されますが、<xref:System.Windows.Forms.ConvertEventArgs.Value%2A>最初に、セルの値を格納するプロパティ。 通常、この値は自動的に、表示型に変換します。 値を自分で変換するには、設定、<xref:System.Windows.Forms.ConvertEventArgs.Value%2A>プロパティを表示型の値。  
  
> [!NOTE]
>  セルの書式指定文字列が有効な場合、オーバーライドの変更、<xref:System.Windows.Forms.ConvertEventArgs.Value%2A>プロパティ値を設定しない限り、<xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A>プロパティを`true`します。  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>イベントを設定する際にも役立ちます<xref:System.Windows.Forms.DataGridViewCellStyle>値に基づいて、個々 のセルのプロパティ。 詳細については、「[方法 :Windows フォーム DataGridView コントロールでデータの書式設定をカスタマイズ](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)します。  
  
 ユーザーが指定した値の既定の解析もニーズを満たしていない場合を処理できます、<xref:System.Windows.Forms.DataGridView.CellParsing>のイベント、<xref:System.Windows.Forms.DataGridView>カスタム解析を提供するコントロール。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Windows フォーム DataGridView コントロールでのデータの表示](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでのセルのスタイル](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [方法: 書式設定データの Windows フォーム DataGridView コントロール](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールでデータの書式設定をカスタマイズします。](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
