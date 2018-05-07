---
title: DataView による並べ替え (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
ms.openlocfilehash: 41f6f56765e1a623f8f2bdc8f2322589125d123e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="sorting-with-dataview-linq-to-dataset"></a>DataView による並べ替え (LINQ to DataSet)
特定の条件に基づいてデータを並べ替え、UI コントロールを介してそのデータをクライアントに提供する機能は、データ バインディングの重要な特徴です。 <xref:System.Data.DataView> には、データを並べ替え、特定の並べ替え条件に従って並べ替えられたデータ行を返す方法がいくつか用意されています。 だけでなく、文字列ベースの並べ替え機能、<xref:System.Data.DataView>を使用することもできます[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]並べ替えの基準の式。 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 式は、文字列ベースの並べ替えよりもはるかに複雑で強力なの並べ替え操作を許可します。 このトピックでは、<xref:System.Data.DataView> を使用して並べ替えを行うこの 2 つの方法について説明します。  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a>並べ替え情報を含むクエリによる DataView の作成  
 <xref:System.Data.DataView> オブジェクトは [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] クエリから作成できます。 そのクエリが含まれている場合、 <xref:System.Linq.Enumerable.OrderBy%2A>、 <xref:System.Linq.Enumerable.OrderByDescending%2A>、 <xref:System.Linq.Enumerable.ThenBy%2A>、または<xref:System.Linq.Enumerable.ThenByDescending%2A>これらの句内の式がデータの並べ替えの基準として使用される句、<xref:System.Data.DataView>です。 たとえば、クエリに含まれる場合、`Order By…`と`Then By…`句、その結果<xref:System.Data.DataView>指定された両方の列によってデータの順序付けはします。  
  
 式ベースの並べ替えは、文字列ベースの並べ替えよりもはるかに強力で複雑な並べ替え機能を提供します。 文字列ベースの並べ替え機能と式ベースの並べ替え機能は、相互に排他的です。 <xref:System.Data.DataView.Sort%2A> をクエリから作成した後に文字列ベースの <xref:System.Data.DataView> を設定した場合、クエリから推論される式ベースの並べ替えはクリアされます (再設定できません)。  
  
 <xref:System.Data.DataView> のインデックスは、<xref:System.Data.DataView> の作成時に構築されるほか、並べ替えまたはフィルター処理の情報が変更されたときにも構築されます。 最高のパフォーマンスを得るには、[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] を作成する <xref:System.Data.DataView> クエリに並べ替え条件を指定し、後で並べ替え情報を変更しないようにします。 詳細については、次を参照してください。 [DataView のパフォーマンス](../../../../docs/framework/data/adonet/dataview-performance.md)です。  
  
> [!NOTE]
>  ほとんどの場合、並べ替えに使用する式は、副作用のない確定的な式である必要があります。 また、並べ替え処理は任意の回数実行されるため、特定の実行回数に依存するロジックが式に含まれないようにしてください。  
  
### <a name="example"></a>例  
 次の例では、SalesOrderHeader テーブルに対してクエリを実行し、返された行を発注日順に並べ替えます。次にこのクエリから <xref:System.Data.DataView> を作成し、<xref:System.Data.DataView> を <xref:System.Windows.Forms.BindingSource> にバインドします。  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### <a name="example"></a>例  
 次の例では、SalesOrderHeader テーブルに対してクエリを実行し、返された行を合計支払額順に並べ替えます。次にこのクエリから <xref:System.Data.DataView> を作成し、<xref:System.Data.DataView> を <xref:System.Windows.Forms.BindingSource> にバインドします。  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### <a name="example"></a>例  
 次の例では、SalesOrderDetail テーブルに対してクエリを実行し、返された行を注文数量順および販売注文 ID 順に並べ替えます。次にこのクエリから <xref:System.Data.DataView> を作成し、<xref:System.Data.DataView> を <xref:System.Windows.Forms.BindingSource> にバインドします。  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## <a name="using-the-string-based-sort-property"></a>文字列ベースの Sort プロパティの使用  
 <xref:System.Data.DataView> の文字列ベースの並べ替え機能は [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] で動作します。 <xref:System.Data.DataView> を [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] クエリから作成した後、<xref:System.Data.DataView.Sort%2A> プロパティを使用して、<xref:System.Data.DataView> の並べ替えを設定できます。  
  
 文字列ベースの並べ替え機能と式ベースの並べ替え機能は、相互に排他的です。 <xref:System.Data.DataView.Sort%2A> プロパティを設定すると、<xref:System.Data.DataView> の作成元のクエリから推論される式ベースの並べ替えはクリアされます。  
  
 文字列ベースの詳細については<xref:System.Data.DataView.Sort%2A>フィルター処理を参照してください[並べ替え/フィルター データ](../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)です。  
  
### <a name="example"></a>例  
 次の例では、<xref:System.Data.DataView> を Contact テーブルから作成した後、姓を降順に並べ替え、名を昇順に並べ替えます。  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
### <a name="example"></a>例  
 次の例では、姓が "S" で始まる連絡先を取得するクエリを Contact テーブルに対して実行します。  このクエリから <xref:System.Data.DataView> が作成され、<xref:System.Windows.Forms.BindingSource> オブジェクトにバインドされます。  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="clearing-the-sort"></a>並べ替えのクリア  
 <xref:System.Data.DataView> の並べ替え情報は、<xref:System.Data.DataView.Sort%2A> プロパティを使用すると、並べ替えが設定された後にクリアできます。 <xref:System.Data.DataView> の並べ替え情報は、2 つの方法でクリアできます。  
  
-   <xref:System.Data.DataView.Sort%2A> プロパティを `null` に設定します。  
  
-   <xref:System.Data.DataView.Sort%2A> プロパティを空の文字列に設定します。  
  
### <a name="example"></a>例  
 次の例では、クエリから <xref:System.Data.DataView> を作成した後、<xref:System.Data.DataView.Sort%2A> プロパティを空の文字列に設定して並べ替えをクリアします。  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a>例  
 次の例では、Contact テーブルから <xref:System.Data.DataView> を作成し、<xref:System.Data.DataView.Sort%2A> プロパティを設定して、連絡先の姓を降順に並べ替えます。 次に、<xref:System.Data.DataView.Sort%2A> プロパティを `null` に設定して並べ替え情報をクリアします。  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a>関連項目  
 [データ バインディングと LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 [DataView によるフィルター処理](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 [データの並べ替え](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48)
