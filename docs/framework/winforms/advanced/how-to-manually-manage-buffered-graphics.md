---
title: '方法: バッファリングされたグラフィックスを手動で管理します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: b27a013d2cf66fb12365bffc35a07ed32bc25a2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554492"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="3d067-102">方法: バッファリングされたグラフィックスを手動で管理します。</span><span class="sxs-lookup"><span data-stu-id="3d067-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="3d067-103">高度なダブル バッファリングのシナリオで使用することができます、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]ダブル バッファリング ロジックを実装するクラス。</span><span class="sxs-lookup"><span data-stu-id="3d067-103">For more advanced double buffering scenarios, you can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="3d067-104">割り当てと管理、個々 のグラフィックス バッファーを担当するクラスは、<xref:System.Drawing.BufferedGraphicsContext>クラス。</span><span class="sxs-lookup"><span data-stu-id="3d067-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="3d067-105">すべてのアプリケーションが独自の既定<xref:System.Drawing.BufferedGraphicsContext>ダブル バッファリングをそのアプリケーション用の既定のすべてを管理します。</span><span class="sxs-lookup"><span data-stu-id="3d067-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="3d067-106">このインスタンスへの参照を取得するには呼び出すことによって、<xref:System.Drawing.BufferedGraphicsManager.Current%2A>します。</span><span class="sxs-lookup"><span data-stu-id="3d067-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="3d067-107">既定 BufferedGraphicsContext への参照を取得するには</span><span class="sxs-lookup"><span data-stu-id="3d067-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="3d067-108">設定、<xref:System.Drawing.BufferedGraphicsManager.Current%2A>プロパティは、次のコード例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="3d067-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <span data-ttu-id="3d067-109">呼び出す必要はありません、`Dispose`メソッドを<xref:System.Drawing.BufferedGraphicsContext>から受信する参照、<xref:System.Drawing.BufferedGraphicsManager>クラス。</span><span class="sxs-lookup"><span data-stu-id="3d067-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="3d067-110"><xref:System.Drawing.BufferedGraphicsManager>すべてのメモリの割り当てと既定の配布処理<xref:System.Drawing.BufferedGraphicsContext>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="3d067-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="3d067-111">アニメーションなどの画像を多用するアプリケーションは、場合によってパフォーマンスを向上できます専用を使用して<xref:System.Drawing.BufferedGraphicsContext>の代わりに、<xref:System.Drawing.BufferedGraphicsContext>によって提供される、<xref:System.Drawing.BufferedGraphicsManager>します。</span><span class="sxs-lookup"><span data-stu-id="3d067-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="3d067-112">これにより、作成してグラフィックス バッファーをすべて、その他のバッファリングされたグラフィックス管理、アプリケーションに関連付けられているアプリケーションによって消費されるメモリが大きい場合のパフォーマンスのオーバーヘッドを発生させずに、個別に管理できます。</span><span class="sxs-lookup"><span data-stu-id="3d067-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="3d067-113">専用 BufferedGraphicsContext を作成するには</span><span class="sxs-lookup"><span data-stu-id="3d067-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="3d067-114">宣言しの新しいインスタンスを作成、<xref:System.Drawing.BufferedGraphicsContext>クラスに、次のコード例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="3d067-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="3d067-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d067-115">See also</span></span>
- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="3d067-116">ダブル バッファリングされたグラフィックス</span><span class="sxs-lookup"><span data-stu-id="3d067-116">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)
- [<span data-ttu-id="3d067-117">方法: バッファリングされたグラフィックスを手動で描画します。</span><span class="sxs-lookup"><span data-stu-id="3d067-117">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
