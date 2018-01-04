---
title: "方法 : 純色で図形を塗りつぶす"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f016404feeac47c5f77527b8baa68d70742d4763
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>方法 : 純色で図形を塗りつぶす
純色で図形を塗りつぶす、作成、<xref:System.Drawing.SolidBrush>オブジェクト、およびをパススルーする<xref:System.Drawing.SolidBrush>オブジェクトへの fill メソッドのいずれかの引数として、<xref:System.Drawing.Graphics>クラスです。 次の例では、色が赤に楕円を設定する方法を示します。  
  
## <a name="example"></a>例  
 次のコードで、<xref:System.Drawing.SolidBrush.%23ctor%2A>コンス トラクター、<xref:System.Drawing.Color>唯一の引数としてオブジェクト。 によって使用される値、<xref:System.Drawing.Color.FromArgb%2A>メソッドは、色のアルファ、赤、緑、および青の要素を表します。 これらの各値は、0 ~ 255 の範囲でなければなりません。 最初の 255 は、色は完全に不透明で、ある 2 つ目の 255 赤の要素が、最大の輝度を示します。 2 つの 0 は、緑、青のコンポーネントは、両方が 0 の輝度を持つことを示すです。  
  
 渡される 4 つの数字 (0, 0、100, 60)、<xref:System.Drawing.Graphics.FillEllipse%2A>メソッドは、楕円の外接する四角形のサイズと場所を指定します。 四角形は、左上隅の (0, 0)、100 の幅と高さが 60 です。  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。  
  
## <a name="see-also"></a>参照  
 [ブラシを使用した図形の塗りつぶし](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
