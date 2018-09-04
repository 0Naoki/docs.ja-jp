---
title: 式列の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 9c7a656e82198568c39b9bb58f8708f563d6caa2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520828"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="e0ecb-102">式列の作成</span><span class="sxs-lookup"><span data-stu-id="e0ecb-102">Creating Expression Columns</span></span>
<span data-ttu-id="e0ecb-103">列の式を定義すると、同じ行の他の列値またはテーブル内の複数の行の列値に基づいて計算した値を、その列に格納できます。</span><span class="sxs-lookup"><span data-stu-id="e0ecb-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="e0ecb-104">評価する式を定義するには、対象の列の <xref:System.Data.DataColumn.Expression%2A> プロパティを使用し、その式で <xref:System.Data.DataColumn.ColumnName%2A> プロパティを使用して他の列を参照します。</span><span class="sxs-lookup"><span data-stu-id="e0ecb-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="e0ecb-105">式列の <xref:System.Data.DataColumn.DataType%2A> は、その式が返す値に適した型であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0ecb-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="e0ecb-106">テーブル内の式列で使用できるいくつかの式の種類を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e0ecb-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="e0ecb-107">式の種類</span><span class="sxs-lookup"><span data-stu-id="e0ecb-107">Expression type</span></span>|<span data-ttu-id="e0ecb-108">例</span><span class="sxs-lookup"><span data-stu-id="e0ecb-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="e0ecb-109">比較</span><span class="sxs-lookup"><span data-stu-id="e0ecb-109">Comparison</span></span>|<span data-ttu-id="e0ecb-110">"Total >= 500"</span><span class="sxs-lookup"><span data-stu-id="e0ecb-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="e0ecb-111">計算</span><span class="sxs-lookup"><span data-stu-id="e0ecb-111">Computation</span></span>|<span data-ttu-id="e0ecb-112">"UnitPrice \* Quantity"</span><span class="sxs-lookup"><span data-stu-id="e0ecb-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="e0ecb-113">集約</span><span class="sxs-lookup"><span data-stu-id="e0ecb-113">Aggregation</span></span>|<span data-ttu-id="e0ecb-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="e0ecb-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="e0ecb-115">設定することができます、**式**プロパティ、既存の**DataColumn**オブジェクト、またはを含めることが、プロパティに渡される 3 番目の引数として、<xref:System.Data.DataColumn>コンス トラクターは、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="e0ecb-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="e0ecb-116">式は他の式列を参照できます。ただし、2 つの式が相互に参照し合う循環参照の場合は、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e0ecb-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="e0ecb-117">式の作成に関する規則は、次を参照してください。、<xref:System.Data.DataColumn.Expression%2A>のプロパティ、 **DataColumn**クラス。</span><span class="sxs-lookup"><span data-stu-id="e0ecb-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ecb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0ecb-118">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="e0ecb-119">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="e0ecb-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="e0ecb-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="e0ecb-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="e0ecb-121">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="e0ecb-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
