---
title: '方法 : ジオメトリック パスを使用してオブジェクトを回転させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 6d6d21f3f7b609cb2933093a6990425deb39d4a6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398149"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>方法 : ジオメトリック パスを使用してオブジェクトを回転させる
この例では回転 (ピボット) 方法によって定義されたジオメトリック パスに沿ってオブジェクトを<xref:System.Windows.Media.PathGeometry>オブジェクト。  
  
## <a name="example"></a>例  
 次の例は、3 つ<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>四角形をジオメトリ パスに沿って移動するオブジェクト。  
  
-   最初の<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>をアニメーション化、<xref:System.Windows.Media.RotateTransform>いる四角形に適用されます。 アニメーションは、角度の値を生成します。 これにより、四角形がパスの輪郭に沿って回転 (ピボット) します。  
  
-   その他の 2 つのオブジェクトをアニメーション化する、<xref:System.Windows.Media.TranslateTransform.X%2A>と<xref:System.Windows.Media.TranslateTransform.Y%2A>の値を<xref:System.Windows.Media.TranslateTransform>いる四角形に適用されます。 これにより、四角形が、パスに沿って水平方向と垂直方向に移動します。  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 ジオメトリック パスを使用してオブジェクトを回転することもできますが、使用する、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>オブジェクトし、設定、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>プロパティを`true`します。 詳細と例では、次を参照してください。[ジオメトリック パス (行列アニメーション) を使用してオブジェクトを回転させる](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)します。  
  
 サンプル全体については、次を参照してください。[パス アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160028)します。  
  
## <a name="see-also"></a>関連項目  
 [アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [パス アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160028)  
 [パス アニメーションに関する「方法」トピック](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
