---
title: Windows フォームにおけるグラフィックスと描画
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e6d3c395a2d5b8ae885114a53b230d7265102bc8
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "56441165"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Windows フォームにおけるグラフィックスと描画
共通言語ランタイムは、[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] と呼ばれる Windows グラフィックス デバイス インターフェイス ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) の高度な実装を使用します。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] を使用して、グラフィックスの作成、テキストの描画や、グラフィカル イメージをオブジェクトとして操作することができます。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] はパフォーマンスと使いやすさを提供するよう設計されています。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] を使用して、Windows フォームとコントロールのグラフィカル イメージを表示できます。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] を Web フォームで直接使用することはできませんが、イメージの Web サーバー コントロールからグラフィカル イメージを表示できます。  
  
 このセクションでは、[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] プログラミングの基礎を紹介するトピックが見つかります。 このセクションは、包括的なリファレンスを意図したものではありませんが、<xref:System.Drawing.Graphics>、<xref:System.Drawing.Pen>、<xref:System.Drawing.Brush>、および <xref:System.Drawing.Color> の各オブジェクトに関する情報が含まれ、図形の描画、テキストの描画、イメージの表示などのタスクを実行する方法について説明します。 詳細については、次を参照してください。 [GDI + の参照](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference)します。  
  
 すぐに開始する場合、「[グラフィックス プログラミングについて](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)」を参照してください。 Windows フォームで線、図形、テキストなどを描画するためのコードの使用方法に関するトピックがあります。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [グラフィックスの概要](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 グラフィックスに関連するマネージド クラスの概要を提供します。  
  
 [GDI+ マネージド コードについて](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 マネージド [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] クラスに関する情報を提供します。  
  
 [マネージド グラフィックス クラスの使用](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] マネージド クラスを使用して、さまざまなタスクを完了する方法を示します。  
  
## <a name="reference"></a>参照  
 <xref:System.Drawing>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] の基本的なグラフィックス機能を使用できるようにします。  
  
 <xref:System.Drawing.Drawing2D>  
 2 次元グラフィックスおよびベクター グラフィックス機能の詳細を提供します。  
  
 <xref:System.Drawing.Imaging>  
 高度な [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] イメージング機能を提供します。  
  
 <xref:System.Drawing.Text>  
 高度な [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] タイポグラフィ機能を提供します。 この名前空間のクラスを使用して、フォントのコレクションを作成して使用することができます。  
  
 <xref:System.Drawing.Printing>  
 印刷機能を提供します。  
  
## <a name="related-sections"></a>関連項目  
 [コントロールのカスタム描画およびレンダリング](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 描画コントロールのコードを提供する方法について詳しく説明します。
