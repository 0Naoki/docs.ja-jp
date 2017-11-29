---
title: "方法 : 影付きテキストを作成する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31bbc3da54c10304e52f93d38365a8d9ed005505
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-text-with-a-shadow"></a>方法 : 影付きテキストを作成する
このセクションの例で、表示されるテキストに影を付ける方法を紹介します。  
  
## <a name="example"></a>例  
 <xref:System.Windows.Media.Effects.DropShadowEffect>オブジェクトでは、さまざまなドロップ シャドウ効果を作成することができます[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]オブジェクト。 テキストにドロップ シャドウ効果を適用した例を次に示します。 この場合、影はソフト シャドウです。つまり、影の色がぼやけています。  
  
 ![テキストの影のぼかし &#61;です。0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
ソフト シャドウが付いたテキストの例  
  
 設定して影の幅を制御することができます、<xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>プロパティです。 値`4.0`シャドウ幅 4 ピクセルを示します。 ぼかしを制御する、または変更することで影のぼかし、<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>プロパティです。 値`0.0`ないことを示しますぼかしが強くなります。 ソフト シャドウを付ける方法を次のコード例に示します。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  これらのシャドウ効果を通過しない、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]テキスト レンダリング パイプライン。 結果として、これらの効果の利用時、ClearType が無効になります。  
  
 テキストにハード シャドウ効果を適用した例を次に示します。 この場合、影はぼかされません。  
  
 ![テキストの影のぼかし &#61;です。0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")  
ハード シャドウが付いたテキストの例  
  
 設定してハード シャドウを作成することができます、<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>プロパティを`0.0`、ぼかし効果が使用されていないことを示します。 影の方向を制御するには変更することによって、<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>プロパティです。 ある程度の間にこのプロパティの方向性のある値を設定`0`と`360`です。 次の図は、方向性のある値の<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>プロパティの設定。  
  
 ![シャドウの DropShadow 度の設定](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
DropShadow 方向の図  
  
 ハード シャドウを付ける方法を次のコード例に示します。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>ぼかし効果を使用する  
 A<xref:System.Windows.Media.Effects.BlurBitmapEffect>テキスト オブジェクトの内側に配置可能なシャドウのような効果を作成するために使用できます。 テキストに適用されたぼかしビットマップ効果は、全方向に均等にテキストをぼかします。  
  
 テキストにぼかし効果が適用されている例を次に示します。  
  
 ![BlurBitmapEffect を使用するテキスト シャドウ](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
ぼかし効果が適用されたテキストの例  
  
 ぼかし効果を付ける方法を次のコード例に示します。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>TranslateTransform を使用する  
 A<xref:System.Windows.Media.TranslateTransform>テキスト オブジェクトの内側に配置可能なシャドウのような効果を作成するために使用できます。  
  
 次のコード例では、<xref:System.Windows.Media.TranslateTransform>テキストのオフセット。 この例では、メインのテキストの下にわずかに中心をずらしたコピーが付き、影のような効果を作っています。  
  
 ![TranslateTransform を使用するテキスト シャドウ](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")  
TranslateTransform を使用して影のような効果を付けたテキストの例  
  
 TranslateTransform を利用して影のような効果を付ける方法を次のコード例に示します。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
