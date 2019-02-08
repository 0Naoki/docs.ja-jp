---
title: LINQ to DataSet の例
ms.date: 03/30/2017
ms.assetid: dfd91658-8d8a-45a4-a356-e327e809f21d
ms.openlocfilehash: ae43111a5b56e1edf3e1b4089902a8ca1d822d0d
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903797"
---
# <a name="linq-to-dataset-examples"></a><span data-ttu-id="7ac15-102">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="7ac15-102">LINQ to DataSet Examples</span></span>
<span data-ttu-id="7ac15-103">ここでは、LINQ を標準クエリ演算子を使用するデータセットのプログラミングの例に示します。</span><span class="sxs-lookup"><span data-stu-id="7ac15-103">This section provides LINQ to DataSet programming examples that use the standard query operators.</span></span> <span data-ttu-id="7ac15-104"><xref:System.Data.DataSet>これらの例で使用されるを使用して設定されますが、`FillDataSet`メソッドで指定されている[をデータセットにデータを読み込む](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac15-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="7ac15-105">詳細については、次を参照してください。[標準クエリ演算子の概要 (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)または[標準クエリ演算子の概要 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="7ac15-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ac15-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7ac15-106">In This Section</span></span>  
 [<span data-ttu-id="7ac15-107">クエリ式の例</span><span class="sxs-lookup"><span data-stu-id="7ac15-107">Query Expression Examples</span></span>](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 <span data-ttu-id="7ac15-108">次の例があります。</span><span class="sxs-lookup"><span data-stu-id="7ac15-108">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="7ac15-109">射影</span><span class="sxs-lookup"><span data-stu-id="7ac15-109">Projection</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-projection-linq-to-dataset.md)  
  
-   [<span data-ttu-id="7ac15-110">制限</span><span class="sxs-lookup"><span data-stu-id="7ac15-110">Restriction</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-restriction-linq-to-dataset.md)  
  
-   [<span data-ttu-id="7ac15-111">パーティション分割</span><span class="sxs-lookup"><span data-stu-id="7ac15-111">Partitioning</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-partitioning.md)  
  
-   [<span data-ttu-id="7ac15-112">順序付け</span><span class="sxs-lookup"><span data-stu-id="7ac15-112">Ordering</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="7ac15-113">要素演算子</span><span class="sxs-lookup"><span data-stu-id="7ac15-113">Element Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="7ac15-114">集計演算子</span><span class="sxs-lookup"><span data-stu-id="7ac15-114">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="7ac15-115">結合演算子</span><span class="sxs-lookup"><span data-stu-id="7ac15-115">Join Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-join-operators.md)  
  
 [<span data-ttu-id="7ac15-116">メソッド ベースのクエリ例</span><span class="sxs-lookup"><span data-stu-id="7ac15-116">Method-Based Query Examples</span></span>](../../../../docs/framework/data/adonet/method-based-query-examples-linq-to-dataset.md)  
 <span data-ttu-id="7ac15-117">次の例があります。</span><span class="sxs-lookup"><span data-stu-id="7ac15-117">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="7ac15-118">射影</span><span class="sxs-lookup"><span data-stu-id="7ac15-118">Projection</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
  
-   [<span data-ttu-id="7ac15-119">パーティション分割</span><span class="sxs-lookup"><span data-stu-id="7ac15-119">Partitioning</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
  
-   [<span data-ttu-id="7ac15-120">順序付け</span><span class="sxs-lookup"><span data-stu-id="7ac15-120">Ordering</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="7ac15-121">集合演算子</span><span class="sxs-lookup"><span data-stu-id="7ac15-121">Set Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
  
-   [<span data-ttu-id="7ac15-122">変換演算子</span><span class="sxs-lookup"><span data-stu-id="7ac15-122">Conversion Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
  
-   [<span data-ttu-id="7ac15-123">要素演算子</span><span class="sxs-lookup"><span data-stu-id="7ac15-123">Element Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="7ac15-124">集計演算子</span><span class="sxs-lookup"><span data-stu-id="7ac15-124">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="7ac15-125">Join</span><span class="sxs-lookup"><span data-stu-id="7ac15-125">Join</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
  
 [<span data-ttu-id="7ac15-126">DataSet 固有の演算子の例</span><span class="sxs-lookup"><span data-stu-id="7ac15-126">DataSet-Specific Operator Examples</span></span>](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 <span data-ttu-id="7ac15-127"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドおよび <xref:System.Data.DataRowComparer> クラスの使用例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="7ac15-127">Contains examples that demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac15-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ac15-128">See also</span></span>
- [<span data-ttu-id="7ac15-129">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7ac15-129">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
- [<span data-ttu-id="7ac15-130">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="7ac15-130">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
