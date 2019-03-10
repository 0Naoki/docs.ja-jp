---
title: '方法: Windows フォームの周りに罫線を作成するパディングを使用して制御'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 66748eef299c9175814fb130a7eda359c5de0546
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720307"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="1f5b3-102">方法: Windows フォームの周りに罫線を作成するパディングを使用して制御</span><span class="sxs-lookup"><span data-stu-id="1f5b3-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="1f5b3-103">次のコード例に境界線を作成またはに関する概要を説明する方法を示します、<xref:System.Windows.Forms.RichTextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="1f5b3-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="1f5b3-104">例では、設定の値を<xref:System.Windows.Forms.Panel>コントロールの<xref:System.Windows.Forms.Padding>プロパティを 5 に設定、<xref:System.Windows.Forms.Control.Dock%2A>子のプロパティ<xref:System.Windows.Forms.RichTextBox>に制御を<xref:System.Windows.Forms.DockStyle.Fill>します。</span><span class="sxs-lookup"><span data-stu-id="1f5b3-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="1f5b3-105"><xref:System.Windows.Forms.Control.BackColor%2A>の<xref:System.Windows.Forms.Panel>に設定されているコントロール<xref:System.Drawing.Color.Blue%2A>、青い境界線を作成する<xref:System.Windows.Forms.RichTextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="1f5b3-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f5b3-106">例</span><span class="sxs-lookup"><span data-stu-id="1f5b3-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1f5b3-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f5b3-107">See also</span></span>
- <xref:System.Windows.Forms.Padding>
- [<span data-ttu-id="1f5b3-108">Windows フォーム コントロールでのマージンと埋め込み</span><span class="sxs-lookup"><span data-stu-id="1f5b3-108">Margin and Padding in Windows Forms Controls</span></span>](margin-and-padding-in-windows-forms-controls.md)
