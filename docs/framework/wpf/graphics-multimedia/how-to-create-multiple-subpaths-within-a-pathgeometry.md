---
title: '方法: PathGeometry 内に複数のサブパスを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: d7b3d24f8d947d342a2af5484a6620c8379ac664
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638354"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>方法: PathGeometry 内に複数のサブパスを作成する
この例で複数のサブパスを作成する方法を示しています、<xref:System.Windows.Media.PathGeometry>します。 作成する複数のサブパスを作成する、<xref:System.Windows.Media.PathFigure>各サブパスにします。  
  
## <a name="example"></a>例  
 次の例は、三角形が 1 つずつ、2 つのサブパスを作成します。  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 次の例を使用して複数のサブパスを作成する方法を示しています、<xref:System.Windows.Shapes.Path>と[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性構文。 各`M`例は、各三角形を描画しないこと、2 つのサブパスを作成できるように、新しいサブパスを作成します。  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (この属性の構文が実際に作成するメモを<xref:System.Windows.Media.StreamGeometry>の軽量バージョンを<xref:System.Windows.Media.PathGeometry>します。 詳細については、「[パス マークアップ構文](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)」のページを参照してください。)  
  
## <a name="see-also"></a>関連項目
- [ジオメトリの概要](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
