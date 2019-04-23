---
title: DataReader の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 8932f393af58f2014f643c5b6ebd6dc7a127b7eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122006"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="e05ea-102">DataReader の作成</span><span class="sxs-lookup"><span data-stu-id="e05ea-102">Creating a DataReader</span></span>
<span data-ttu-id="e05ea-103"><xref:System.Data.DataTable> クラスおよび <xref:System.Data.DataSet> クラスには、<xref:System.Data.DataTable.CreateDataReader%2A> の内容または <xref:System.Data.DataTable> オブジェクトの <xref:System.Data.DataSet> コレクションの内容を、読み取り専用で前方参照専用の 1 つ以上の結果セットとして返す <xref:System.Data.DataSet.Tables%2A> メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="e05ea-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e05ea-104">例</span><span class="sxs-lookup"><span data-stu-id="e05ea-104">Example</span></span>  
 <span data-ttu-id="e05ea-105"><xref:System.Data.DataTable> インスタンスを作成するコンソール アプリケーションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e05ea-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="e05ea-106">例は、塗りつぶされた<xref:System.Data.DataTable>を呼び出すプロシージャに、<xref:System.Data.DataTable.CreateDataReader%2A>内に含まれる結果を反復処理するメソッド、<xref:System.Data.DataTableReader>します。</span><span class="sxs-lookup"><span data-stu-id="e05ea-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="e05ea-107">この例では、次の出力がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e05ea-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="e05ea-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="e05ea-108">See also</span></span>

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [<span data-ttu-id="e05ea-109">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="e05ea-109">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [<span data-ttu-id="e05ea-110">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="e05ea-110">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
