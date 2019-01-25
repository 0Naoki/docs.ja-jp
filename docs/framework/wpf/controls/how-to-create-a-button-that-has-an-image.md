---
title: '方法: イメージを持つ Button を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: cfebe53047531ecddde42a3a0596dfd949629ecd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682063"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="fcaf8-102">方法: イメージを持つ Button を作成する</span><span class="sxs-lookup"><span data-stu-id="fcaf8-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="fcaf8-103">この例の画像を含める方法を示しています、<xref:System.Windows.Controls.Button>します。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcaf8-104">例</span><span class="sxs-lookup"><span data-stu-id="fcaf8-104">Example</span></span>  
 <span data-ttu-id="fcaf8-105">次の例では、2 つ作成されます<xref:System.Windows.Controls.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="fcaf8-106">1 つ<xref:System.Windows.Controls.Button>テキストを含む、他のイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="fcaf8-107">イメージは、例のプロジェクト フォルダーのサブフォルダーであるデータをという名前のフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="fcaf8-108">ユーザーがクリックすると、<xref:System.Windows.Controls.Button>イメージ、バック グラウンド、およびその他のテキストを持つ<xref:System.Windows.Controls.Button>を変更します。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="fcaf8-109">この例で作成<xref:System.Windows.Controls.Button>マークアップを使用して制御しますが、コードを使用して書き込む、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="fcaf8-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcaf8-110">See also</span></span>
- [<span data-ttu-id="fcaf8-111">コントロール</span><span class="sxs-lookup"><span data-stu-id="fcaf8-111">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)
- [<span data-ttu-id="fcaf8-112">コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="fcaf8-112">Control Library</span></span>](../../../../docs/framework/wpf/controls/control-library.md)
