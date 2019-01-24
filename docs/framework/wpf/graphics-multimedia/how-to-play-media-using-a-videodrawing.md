---
title: '方法: VideoDrawing を使用してメディアを再生する'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 81f8dfc46dad07f34e50aac39e6cfde16de608a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644873"
---
# <a name="how-to-play-media-using-a-videodrawing"></a>方法: VideoDrawing を使用してメディアを再生する
使用するオーディオまたはビデオ ファイルを再生するには<xref:System.Windows.Media.VideoDrawing>と<xref:System.Windows.Media.MediaPlayer>します。 メディアを読み込んで再生するには、2 つの方法があります。 1 つ目は、使用する、<xref:System.Windows.Media.MediaPlayer>と<xref:System.Windows.Media.VideoDrawing>自体を 2 番目の方法は、独自に作成する<xref:System.Windows.Media.MediaTimeline>で使用する、<xref:System.Windows.Media.MediaPlayer>と<xref:System.Windows.Media.VideoDrawing>します。  
  
> [!NOTE]
>  アプリケーションでメディアを配布するときは、イメージのようにプロジェクト リソースとしてメディア ファイルを使うことはできません。 プロジェクト ファイルで、メディアの種類を `Content` に設定し、`CopyToOutputDirectory` を `PreserveNewest` または `Always` に設定する必要があります。  
  
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.Media.VideoDrawing>と<xref:System.Windows.Media.MediaPlayer>をビデオ ファイルを 1 回再生します。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 使用して、メディアを介した追加のタイミングを制御する、<xref:System.Windows.Media.MediaTimeline>で、<xref:System.Windows.Media.MediaPlayer>と<xref:System.Windows.Media.VideoDrawing>オブジェクト。 <xref:System.Windows.Media.MediaTimeline>ビデオを繰り返す必要があるかどうかを指定することができます。  
  
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.Media.MediaTimeline>で、<xref:System.Windows.Media.MediaPlayer>と<xref:System.Windows.Media.VideoDrawing>ビデオを繰り返し再生するオブジェクト。  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 使用すると、 <xref:System.Windows.Media.MediaTimeline>、対話型を使用する<xref:System.Windows.Media.Animation.ClockController>から返される、<xref:System.Windows.Media.Animation.Clock.Controller%2A>のプロパティ、<xref:System.Windows.Media.MediaClock>の対話型のメソッドではなくメディア再生を制御する<xref:System.Windows.Media.MediaPlayer>。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Media.VideoDrawing>
- [Drawing オブジェクトの概要](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
