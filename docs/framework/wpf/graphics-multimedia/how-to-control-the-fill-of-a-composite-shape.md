---
title: '方法 : 複合図形の塗りつぶしを制御する'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: a9a17434f11f432f6446e09bd853ed0d2f23fbe8
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2018
ms.locfileid: "33563044"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a>方法 : 複合図形の塗りつぶしを制御する
<xref:System.Windows.Media.GeometryGroup.FillRule%2A>のプロパティを<xref:System.Windows.Media.GeometryGroup>または<xref:System.Windows.Media.PathGeometry>、複合図形を使用して、指定された点がジオメトリの一部であるかどうかを確認する「規則」を指定します。 2 つの値がある<xref:System.Windows.Media.FillRule>:<xref:System.Windows.Media.FillRule.EvenOdd>と<xref:System.Windows.Media.FillRule.Nonzero>します。 以下のセクションでは、これら 2 つの規則の使用方法を説明します。  
  
 **EvenOdd:** この規則では、ある点から任意の方向に無限に伸びる射線を描画し、その射線が横断する指定した図形のパス セグメントの数をカウントすることにより、その点が塗りつぶし領域の内側にあるかどうかを判断します。 この数値が偶数の場合は、ポイントは内側にあります。偶数の場合は、ポイントは外側にあります。  
  
 たとえば、次の XAML での一連の同心リング (ターゲット) から成る複合図形を作成します.、<xref:System.Windows.Media.GeometryGroup.FillRule%2A>設定<xref:System.Windows.Media.FillRule.EvenOdd>します。  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]  
  
 前の例で作成した図を次に示します。  
  
 ![スクリーンショット: EvenOdd の FillRule プロパティ](../../../../docs/framework/wpf/graphics-multimedia/media/fillruleevenoddfirstone.png "FillRuleEvenOddFirstOne")  
  
 上の図で、中央と 3 番目のリングは塗りつぶされていないことに注意してください。 これは、これら 2 つのリングの任意の点から描画された射線が、偶数個のセグメントを通過するためです。 次の図を参照してください。  
  
 ![ダイアグラム: EvenOdd の FillRule プロパティ値](../../../../docs/framework/wpf/graphics-multimedia/media/fillruleevenodd2.png "FillRuleEvenOdd2")  
  
 **NonZero:** この規則では、ある点から任意の方向に無限に伸びる射線を描画し、図形のセグメントがこの射線と交わる場所を調べることにより、その点がパスの塗りつぶし領域の内側にあるかどうかを判断します。 0 からカウントを開始し、パス セグメントが左から右に射線と交わるたびに 1 を加算し、パス セグメントが右から左に射線と交わるたびに 1 を減算します。 交差のカウント後、結果が 0 の場合は、ポイントは、パスの外側にあります。 それ以外の場合は、内側にあります。  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]  
  
 上記の値の例を使用して<xref:System.Windows.Media.FillRule.Nonzero>の<xref:System.Windows.Media.GeometryGroup.FillRule%2A>次の図は、その結果。  
  
 ![スクリーンショット: 0 以外の FillRule 値](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero1.png "FillRuleNonZero1")  
  
 上の図からわかるように、すべてのリングが塗りつぶされます。 これは、すべてのセグメントが同じ方向で、任意の点から描画された射線は 1 つ以上のセグメントと交わり、交差の合計が 0 にならないためです。 たとえば、次の図で、赤い矢印はセグメントが描画されている方向を表し、白い矢印は最も内側のリング内にある点から伸びる任意の射線を表しています。 値 0 から開始し、セグメントは左から右に射線と交わるため、射線が交わるセグメントごとに値 1 が加算されます。  
  
 ![ダイアグラム: 0 以外と等しい FillRule プロパティ値](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero2.png "FillRuleNonZero2")  
  
 動作をわかりやすく示すために<xref:System.Windows.Media.FillRule.Nonzero>規則セグメントがさまざまな方向で実行されているより複雑な図形が必要です。 次の XAML コードで作成する点を除いて前の例と類似した図形を作成、<xref:System.Windows.Media.PathGeometry>ではなく、<xref:System.Windows.Media.EllipseGeometry>同心円を完全に終了ではなく 4 つの同心の円弧を作成します。  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]  
  
 前の例で作成した図を次に示します。  
  
 ![スクリーンショット: 0 以外の FillRule プロパティ値](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero3.png "FillRuleNonZero3")  
  
 中央から 3 番目の円弧が塗りつぶされていないことに注意してください。 その理由を次の図に示します。 この図で、赤い矢印はセグメントが描画されている方向を表しています。 2 つの白い矢印は、"塗りつぶされていない" 領域内の点から外に向かって伸びる、2 本の任意の射線を表しています。 この図からわかるように、指定された射線がパス内でセグメントと交わることによる値の合計は 0 です。 前に定義したように、合計が 0 となるのは、その点がジオメトリの一部でない (塗りつぶしに含まれない) ことを意味し、合計が 0 で*ない*場合 (負の値を含む) は、その点がジオメトリの一部であることを意味しています。  
  
 ![ダイアグラム: 0 以外の FillRule プロパティ値](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero4.png "FillRuleNonZero4")  
  
 **注:** の目的で<xref:System.Windows.Media.FillRule>、すべての図形が終了と見なされます。 セグメントにすき間がある場合は、架空の線を描画して、そのすき間を閉じます。 上の例では、リングに小さなすき間があります。 この場合、このすき間を通る射線は、別の方向に伸びる射線とは異なる結果を生じると思えるかもしれません。 このようなギャップと「架空のセグメント」のいずれかを拡大した図を次に示します (適用するために描画されるセグメント、 <xref:System.Windows.Media.FillRule>) そのすき間を閉じる。  
  
 ![ダイアグラム: FillRule の場合、セグメントは常に閉じられる](../../../../docs/framework/wpf/graphics-multimedia/media/fillruleclosedshapes.png "FillRuleClosedShapes")  
  
## <a name="example"></a>例  
  
## <a name="see-also"></a>関連項目  
 [複合図形を作成する](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [ジオメトリの概要](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
