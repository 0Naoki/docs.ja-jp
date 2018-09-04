---
title: '方法 : パスに沿ってオブジェクトをアニメーション化する (オフセット累積による行列アニメーション)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 1d3b74ede9cde1928138d4d8625e8625354f5748
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522757"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>方法 : パスに沿ってオブジェクトをアニメーション化する (オフセット累積による行列アニメーション)
この例は、使用する方法を示します、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>クラス パスに沿ってオブジェクトをアニメーション化して、そのオフセットを蓄積するアニメーションを繰り返すたびの値します。  
  
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>アニメーション化するオブジェクト、<xref:System.Windows.Media.MatrixTransform.Matrix%2A>のプロパティを<xref:System.Windows.Media.MatrixTransform>ボタンに適用します。 その結果、ボタンは曲線状のパスに沿って移動します。  
  
 さらに、例では、設定、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>プロパティを`true`、蓄積、アニメーションを繰り返すたびにアニメーション化された行列のオフセットします。 オフセットが累積されるので、アニメーションが繰り返されたとき、ボタンは開始位置にリセットされるのではなく、画面を横切ってさらに移動します。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>プロパティを繰り返しで累積する値をオフセットすると、累積する回転の値が原因です。 回転値を累積するために、設定、アニメーションの<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>と<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A>プロパティ`true`します。  
  
 サンプル全体については、次を参照してください。[パス アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160028)します。 アニメーション化する方法を示す例については、<xref:System.Windows.Media.Matrix>値のオフセットを蓄積せず、パスに沿ってを参照してください[、オブジェクト パスに沿って (行列アニメーション) をアニメーション化する](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)します。  
  
## <a name="see-also"></a>関連項目  
 [アニメーションの概要](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [パス アニメーションに関する「方法」トピック](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
