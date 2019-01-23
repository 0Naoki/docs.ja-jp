---
title: GDI+ でのイメージの描画、配置、およびクローン作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: afd5be1fd56382ba0dcbb2938a7e466d1584ae7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548220"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>GDI+ でのイメージの描画、配置、およびクローン作成
使用することができます、<xref:System.Drawing.Bitmap>読み込みし、ラスター イメージを表示するクラスを使用できます、<xref:System.Drawing.Imaging.Metafile>クラスを読み込み、ベクター イメージを表示します。 <xref:System.Drawing.Bitmap>と<xref:System.Drawing.Imaging.Metafile>クラスから継承、<xref:System.Drawing.Image>クラス。 インスタンスが必要なベクター画像を表示する、<xref:System.Drawing.Graphics>クラスと<xref:System.Drawing.Imaging.Metafile>します。 インスタンスが必要なラスター イメージを表示する、<xref:System.Drawing.Graphics>クラスと<xref:System.Drawing.Bitmap>します。 インスタンス、<xref:System.Drawing.Graphics>クラスには、<xref:System.Drawing.Graphics.DrawImage%2A>メソッドで、受信、<xref:System.Drawing.Imaging.Metafile>または<xref:System.Drawing.Bitmap>を引数として。  
  
## <a name="file-types-and-cloning"></a>ファイルの種類と複製  
 次のコード例を作成する方法を示しています、 <xref:System.Drawing.Bitmap> Climber.jpg ファイルからビットマップを表示します。 イメージの左上隅の終点 (10, 10) が 2 番目と 3 番目のパラメーターで指定されています。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 次の図は、イメージを示します。  
  
 ![サンプル イメージ](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 構築できます<xref:System.Drawing.Bitmap>グラフィックスのさまざまなオブジェクト ファイル形式。BMP、GIF、JPEG、EXIF、PNG、TIFF、およびアイコン。  
  
 次のコード例は、作成する方法を示しています。<xref:System.Drawing.Bitmap>さまざまな種類のファイルからオブジェクトとし、ビットマップが表示されます。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <xref:System.Drawing.Bitmap>クラスには、 <xref:System.Drawing.Bitmap.Clone%2A> 、既存のコピーを作成するために使用できるメソッド<xref:System.Drawing.Bitmap>します。 <xref:System.Drawing.Bitmap.Clone%2A>メソッドにコピーする元のビットマップの部分を指定するのに使用できるソース四角形のパラメーター。 次のコード例を作成する方法を示しています、 <xref:System.Drawing.Bitmap> 、既存の上半分を複製することにより<xref:System.Drawing.Bitmap>します。 次に、両方のイメージが描画します。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 次の図は、2 つのイメージを示します。  
  
 ![トリミング](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>関連項目
- [イメージ、ビットマップ、メタファイル](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [方法: 描画の Graphics オブジェクトを作成します。](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
