---
title: '方法: 成型された Windows フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
ms.openlocfilehash: 03fcbb97db180e71283810e2daeab9be272b9d5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004381"
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="fa4e5-102">方法: 成型された Windows フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="fa4e5-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="fa4e5-103">この例では、フォームのサイズを変更する楕円形フォームを示します。</span><span class="sxs-lookup"><span data-stu-id="fa4e5-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa4e5-104">例</span><span class="sxs-lookup"><span data-stu-id="fa4e5-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa4e5-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="fa4e5-105">Compiling the Code</span></span>  
 <span data-ttu-id="fa4e5-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fa4e5-106">This example requires:</span></span>  
  
- <span data-ttu-id="fa4e5-107"><xref:System.Windows.Forms> 名前空間と <xref:System.Drawing> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="fa4e5-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="fa4e5-108">この例は、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドは、フォームの形状を変更します。</span><span class="sxs-lookup"><span data-stu-id="fa4e5-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="fa4e5-109">このコードを使用するには、メソッドの宣言とメソッドの内部の描画コードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="fa4e5-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa4e5-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa4e5-110">See also</span></span>

- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Region>
- <xref:System.Drawing>
- <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>
- <xref:System.Windows.Forms.Control.Region%2A>
- [<span data-ttu-id="fa4e5-111">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="fa4e5-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
