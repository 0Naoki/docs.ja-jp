---
title: '方法: データ サービス メッセージ (WCF Data Services) をインターセプトします。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: ad0673f72b1a81d6bcfaf0704ccd698eda7bb20c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517835"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="2d0f4-102">方法: データ サービス メッセージ (WCF Data Services) をインターセプトします。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-102">How to: Intercept Data Service Messages (WCF Data Services)</span></span>
<span data-ttu-id="2d0f4-103">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] では、要求メッセージを先に取得して、操作にカスタム ロジックを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-103">With [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="2d0f4-104">メッセージをインターセプトするには、データ サービスで特別なメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-104">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="2d0f4-105">詳細については、次を参照してください。[インターセプター](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-105">For more information, see [Interceptors](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="2d0f4-106">このトピックの例では、Northwind サンプル データ サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-106">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="2d0f4-107">このサービスの作成を完了すると、 [WCF Data Services クイック スタート](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-107">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="2d0f4-108">Orders エンティティ セットのクエリ インターセプターを定義するには</span><span class="sxs-lookup"><span data-stu-id="2d0f4-108">To define a query interceptor for the Orders entity set</span></span>  
  
1. <span data-ttu-id="2d0f4-109">Northwind データ サービス プロジェクトで Northwind.svc ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-109">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="2d0f4-110">`Northwind` クラスのコード ページで次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-110">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. <span data-ttu-id="2d0f4-111">`Northwind` クラスで、次に示すように `OnQueryOrders` というサービス操作メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-111">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="2d0f4-112">Products エンティティ セットの変更インターセプターを定義するには</span><span class="sxs-lookup"><span data-stu-id="2d0f4-112">To define a change interceptor for the Products entity set</span></span>  
  
1. <span data-ttu-id="2d0f4-113">Northwind データ サービス プロジェクトで Northwind.svc ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="2d0f4-114">`Northwind` クラスで、次に示すように `OnChangeProducts` というサービス操作メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-114">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="2d0f4-115">例</span><span class="sxs-lookup"><span data-stu-id="2d0f4-115">Example</span></span>  
 <span data-ttu-id="2d0f4-116">この例では、ラムダ式を返す `Orders` エンティティ セットのクエリ インターセプター メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-116">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="2d0f4-117">この式には、要求された `Orders` を特定の連絡先名が付けられた関連 `Customers` に基づいてフィルターするデリゲートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-117">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="2d0f4-118">この名前は、要求ユーザーに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-118">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="2d0f4-119">この例では、認証が有効化され、WCF を使用する ASP.NET Web アプリケーション内でデータ サービスがホストされていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-119">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="2d0f4-120"><xref:System.Web.HttpContext> クラスは、現在の要求の原則を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-120">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="2d0f4-121">例</span><span class="sxs-lookup"><span data-stu-id="2d0f4-121">Example</span></span>  
 <span data-ttu-id="2d0f4-122">この例は、`Products` エンティティ セットの変更インターセプター メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-122">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="2d0f4-123">このメソッドは、<xref:System.Data.Services.UpdateOperations.Add> 操作または <xref:System.Data.Services.UpdateOperations.Change> 操作に関するサービスへの入力を検証し、生産が中止されている製品への変更が行われた場合に例外を発生させます。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-123">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="2d0f4-124">また、サポートされない操作として製品の削除をブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-124">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="2d0f4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d0f4-125">See also</span></span>

- [<span data-ttu-id="2d0f4-126">方法: サービス操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="2d0f4-126">How to: Define a Service Operation</span></span>](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)
- [<span data-ttu-id="2d0f4-127">WCF Data Services の定義</span><span class="sxs-lookup"><span data-stu-id="2d0f4-127">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
