---
title: DataRelation の移動
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 1819d468d12c03ce0c4faac11f4b20b8fe0f9c33
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482007"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="8a5fe-102">DataRelation の移動</span><span class="sxs-lookup"><span data-stu-id="8a5fe-102">Navigating DataRelations</span></span>
<span data-ttu-id="8a5fe-103"><xref:System.Data.DataRelation> の主な機能の 1 つは、<xref:System.Data.DataTable> の 1 つの <xref:System.Data.DataSet> から別の  を移動できることです。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="8a5fe-104">すべてを取得することができます、関連する<xref:System.Data.DataRow>にあるオブジェクトの**DataTable**指定されると、1 つ**DataRow**関連から**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="8a5fe-105">確立した後など、 **DataRelation**を使用して特定の顧客行のすべての注文行を取得する顧客のテーブルと orders のテーブルでは、間**GetChildRows**。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="8a5fe-106">次のコード例を作成、 **DataRelation**間、**顧客**テーブルおよび**注文**のテーブルを**データセット**を返します各顧客のすべての注文します。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="8a5fe-107">上記の例に基づいて、4 つのテーブルを相互に関連付け、そのテーブルのリレーションシップ間を移動する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="8a5fe-108">前の例のように**CustomerID**関連、**顧客**テーブル、**注文**テーブル。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="8a5fe-109">顧客ごとに、**顧客**テーブル内のすべての子行、**注文**特定の顧客が注文の数を返すために、テーブルが決定され、その**OrderID**値。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="8a5fe-110">展開された例もから値を返します、 **OrderDetails**と**製品**テーブル。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="8a5fe-111">**注文**テーブルに関連する、 **OrderDetails**テーブルを使用して**OrderID**を決める際に、各顧客の注文、どのような製品と数量を注文しました。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="8a5fe-112">**OrderDetails**テーブルにはのみが含まれています、 **ProductID**注文の製品の**OrderDetails**に関連する**製品**使用して**ProductID**を返すために、 **ProductName**します。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="8a5fe-113">このリレーションで、**製品**テーブルが親と**Order Details**テーブルが子。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="8a5fe-114">その結果、反復処理時、 **OrderDetails**テーブル**GetParentRow**取得、関連するために呼び出される**ProductName**値。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="8a5fe-115">された場合、 **DataRelation**用に作成、**顧客**と**注文**テーブル、値が指定されていない、 **createConstraints**フラグ (既定値は**true**)。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="8a5fe-116">これですべての行、**注文**テーブルが、 **CustomerID** 、親が存在する値**顧客**テーブル。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="8a5fe-117">場合、 **CustomerID**内に存在する、**注文**テーブルに存在しない、**顧客**、テーブル、<xref:System.Data.ForeignKeyConstraint>例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="8a5fe-118">子の列には、親列を含まない値が含まれます、設定、 **createConstraints**フラグを**false**を追加するとき、 **DataRelation**します。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="8a5fe-119">例では、 **createConstraints**にフラグが設定されている**false**の**DataRelation**間、**注文**テーブルと、 **OrderDetails**テーブル。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="8a5fe-120">これにより、アプリケーションからのすべてのレコードを返す、 **OrderDetails**テーブルとレコードのサブセットのみ、**注文**せず、実行時に例外を生成するテーブル。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="8a5fe-121">展開された例では、次の形式で出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-121">The expanded sample generates output in the following format.</span></span>  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 <span data-ttu-id="8a5fe-122">次のコード例は、展開された例場所からの値、 **OrderDetails**と**製品**内のレコードのサブセットのみをテーブルが返されます、**注文**返されるテーブル。</span><span class="sxs-lookup"><span data-stu-id="8a5fe-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8a5fe-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a5fe-123">See Also</span></span>  
 [<span data-ttu-id="8a5fe-124">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="8a5fe-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="8a5fe-125">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="8a5fe-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
