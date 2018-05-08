---
title: アルファ ブレンドの直線と塗りつぶし
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: f58fa2d105492c6c72d3d6906c3c35f89130fe91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="alpha-blending-lines-and-fills"></a>アルファ ブレンドの直線と塗りつぶし
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]色がそれぞれ 8 ビットでアルファ、赤、緑、および青の 32 ビット値。 アルファ値は、色の透明度を示します: 範囲の色から背景色とブレンドされます。 アルファ値の範囲は 0 ~ 255, 0 が完全に透明色を表すおよび 255 は、完全に不透明な色を表します。  
  
 アルファ ブレンドは、ソースと背景色データのピクセルごとの組み合わせです。 指定したソースの色の 3 つのコンポーネント (赤、緑、青) は、次の数式に従って背景色の対応するコンポーネントとブレンドされます。  
  
 displayColor sourceColor × アルファを = 255/+ backgroundColor × (255 – alpha)/255  
  
 たとえば、元の色の赤の要素があるとします 150 と背景色の赤の要素は 100 です。 アルファ値が 200 の場合は、生成される色の赤の要素は次のように計算されます。  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: 不透明な直線および半透明な直線を描画する](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 アルファ ブレンドの直線を描画する方法を示します。  
  
 [方法: 不透明ブラシおよび半透明ブラシを使用して描画する](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 アルファ ブレンド (ブラシと共に) する方法をについて説明します。  
  
 [方法: 複合モードを使用してアルファ ブレンドを制御する](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 使用してアルファ ブレンドを制御する方法について説明<xref:System.Drawing.Drawing2D.CompositingMode>です。  
  
 [方法: カラー行列を使用してイメージのアルファ値を設定する](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 使用する方法について説明します、<xref:System.Drawing.Imaging.ColorMatrix>アルファ ブレンドを制御するオブジェクト。
