---
title: "方法 : 複雑なグリッドを作成する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c0008a7379feefd9b3fe719f85b3205a72fb51d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-complex-grid"></a>方法 : 複雑なグリッドを作成する
この例を使用する方法を示しています、<xref:System.Windows.Controls.Grid>月間予定表のようなレイアウトを作成します。  
  
## <a name="example"></a>例  
 次の例を使用して 8 つの行と 8 つの列の定義、<xref:System.Windows.Controls.RowDefinition>と<xref:System.Windows.Controls.ColumnDefinition>クラスです。 使用して、<xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType>と<xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType>と共にアタッチされるプロパティ、<xref:System.Windows.Shapes.Rectangle>要素で、さまざまな列と行の背景色を入力します。 この設計は、複数の要素が内の各セル内に存在できるため、可能な<xref:System.Windows.Controls.Grid>、原則違い<xref:System.Windows.Controls.Grid>と<xref:System.Windows.Documents.Table>です。  
  
 例では、使用する垂直グラデーション<xref:System.Windows.Shapes.Shape.Fill%2A>ビジュアルのプレゼンテーションや予定表の読みやすさを向上するために行と列。 スタイルの<xref:System.Windows.Controls.TextBlock>要素は、日付と曜日を表します。 <xref:System.Windows.Controls.TextBlock>要素は、セル内を使用して絶対位置、<xref:System.Windows.FrameworkElement.Margin%2A>プロパティと、アプリケーションのスタイル内で定義されている配置プロパティです。  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [純色およびグラデーションによる塗りつぶしの概要](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [パネルの概要](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [テーブルの概要](../../../../docs/framework/wpf/advanced/table-overview.md)
