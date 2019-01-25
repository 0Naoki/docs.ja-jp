---
title: '方法: PrintTickets を検証およびマージする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 0b9f7b101ea4f06c86f66f8e4e16d1ffeabaa9e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671942"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="d3b8f-102">方法: PrintTickets を検証およびマージする</span><span class="sxs-lookup"><span data-stu-id="d3b8f-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="d3b8f-103">[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [印刷スキーマ](https://go.microsoft.com/fwlink/?LinkId=186397)柔軟性と拡張性が含まれています<xref:System.Printing.PrintCapabilities>と<xref:System.Printing.PrintTicket>要素。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="d3b8f-104">印刷デバイスの機能を列記前者と後者の場合、デバイスが特定のシーケンスのドキュメント、個々 のドキュメント、または個々 のページに対してこれらの機能を使用する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="d3b8f-105">印刷をサポートするアプリケーションのタスクの一般的なシーケンスであるようです。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="d3b8f-106">プリンターの機能を決定します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="d3b8f-107">構成、<xref:System.Printing.PrintTicket>それらの機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="d3b8f-108">検証、<xref:System.Printing.PrintTicket>します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="d3b8f-109">この記事では、これを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3b8f-110">例</span><span class="sxs-lookup"><span data-stu-id="d3b8f-110">Example</span></span>  
 <span data-ttu-id="d3b8f-111">次の単純な例でプリンターが両面印刷をサポートするかどうかのみが必要な両面印刷します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="d3b8f-112">主要な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="d3b8f-113">取得、<xref:System.Printing.PrintCapabilities>オブジェクトを<xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="d3b8f-114">必要な機能の有無をテストします。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="d3b8f-115">次の例では、テスト、<xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>のプロパティ、<xref:System.Printing.PrintCapabilities>用紙の長辺に沿って「ページに」用紙の両面に印刷の機能が存在するオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="d3b8f-116"><xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>はコレクションを使用して、`Contains`メソッドの<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3b8f-117">この手順では、厳密には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-117">This step is not strictly necessary.</span></span> <span data-ttu-id="d3b8f-118"><xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>以下で使用方法は、各要求を確認するのには、<xref:System.Printing.PrintTicket>プリンターの機能を比較します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="d3b8f-119">プリンター ドライバーがで別の要求を置き換えて、要求された機能がプリンターでサポートされていない場合、<xref:System.Printing.PrintTicket>メソッドによって返されます。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="d3b8f-120">サンプル コードを作成、プリンターが両面印刷をサポートする場合、<xref:System.Printing.PrintTicket>二重求められます。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="d3b8f-121">アプリケーションでは設定で使用可能なすべての可能なプリンターが指定されていない、<xref:System.Printing.PrintTicket>要素。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="d3b8f-122">プログラマとプログラムの時間の無駄なことです。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="d3b8f-123">代わりに、コードは二重化の要求のみを設定し、これをマージ<xref:System.Printing.PrintTicket>既存の完全に構成され、検証、 <xref:System.Printing.PrintTicket>、ここでは、ユーザーの既定<xref:System.Printing.PrintTicket>します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="d3b8f-124">したがって、サンプルを呼び出す、<xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>メソッドを新しいマージ最小限、 <xref:System.Printing.PrintTicket> 、既定値は、ユーザーの<xref:System.Printing.PrintTicket>します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="d3b8f-125">返されます、<xref:System.Printing.ValidationResult>を含む新しい<xref:System.Printing.PrintTicket>としてそのプロパティのいずれか。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="d3b8f-126">サンプルをテストし、新しい<xref:System.Printing.PrintTicket>二重化を要求します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="d3b8f-127">場合は、サンプルを使用すると、ユーザーの新しい既定の印刷チケット。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="d3b8f-128">上記の手順 2 を省略したかどうかと、プリンターが両面印刷、長辺に沿ってをサポートしていませんでしたし、テスト結果となります`false`します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="d3b8f-129">(上記の注を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="d3b8f-130">最後の重要な手順に変更をコミットするには、<xref:System.Printing.PrintQueue.UserPrintTicket%2A>のプロパティ、<xref:System.Printing.PrintQueue>で、<xref:System.Printing.PrintQueue.Commit%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="d3b8f-131">すぐにこの例をテストするように、残りの部分は次に示します。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="d3b8f-132">プロジェクトと名前空間を作成し、この記事では、名前空間ブロックに両方のコード スニペットを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d3b8f-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="d3b8f-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3b8f-133">See also</span></span>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="d3b8f-134">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="d3b8f-134">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [<span data-ttu-id="d3b8f-135">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="d3b8f-135">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
- [<span data-ttu-id="d3b8f-136">印刷スキーマ</span><span class="sxs-lookup"><span data-stu-id="d3b8f-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
