---
title: "単一テーブルのクエリ (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0b74bcf8-3f87-449f-bff7-6bcb0d69d212
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5ac58f5e98113150123b152dad8d2cc25c61cf97
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="single-table-queries-linq-to-dataset"></a>単一テーブルのクエリ (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]実装するデータ ソースに対するクエリは、処理、<xref:System.Collections.Generic.IEnumerable%601>インターフェイスまたは<xref:System.Linq.IQueryable%601>インターフェイスです。 <xref:System.Data.DataTable>クラスがいずれのインターフェイスを実装していないので、呼び出す必要があります、<xref:System.Data.DataTableExtensions.AsEnumerable%2A>メソッドを使用する場合、<xref:System.Data.DataTable>のソースとして、`From`の句、[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]クエリ。  
  
 次の例では、SalesOrderHeader テーブルからオンラインでの注文をすべて取得し、注文 ID、注文日、および注文番号をコンソールに出力します。  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)] 
  
 ローカル変数 query は、いずれかから 1 つまたは複数のクエリ演算子を適用することで標準クエリ演算子の 1 つ以上の情報ソースに基づいて動作する、クエリ式でまたはの大文字と小文字を初期化は[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]、に固有の演算子<xref:System.Data.DataSet>クラスです。 前の例のクエリ式には、2 つの標準クエリ演算子、`Where` と `Select` が使用されています。  
  
 この場合、`Where` 句では、`OnlineOrderFlag` = `true` という条件に基づいてデータを抽出します。 `Select` 演算子は、その演算子に渡された引数をキャプチャする列挙可能なオブジェクトを割り当てて返します。 上の例では、`SalesOrderID`、`OrderDate`、`SalesOrderNumber` の 3 つのプロパティを使って匿名型を作成しています。 この 3 つのプロパティの値は、`SalesOrderID` テーブルの `OrderDate` 列、`SalesOrderNumber` 列、および `SalesOrderHeader` 列の値に設定されます。  
  
 次に、`foreach` から返された列挙可能なオブジェクトを `Select` ループで列挙し、クエリ結果を出力します。 クエリは <xref:System.Linq.Enumerable> を実装する <xref:System.Collections.Generic.IEnumerable%601> 型であるため、`foreach` ループでクエリ変数を反復処理するまでクエリは評価されません。 クエリの評価を遅らせることで、繰り返し評価することのできる値としてクエリを維持し、評価のたびに異なる結果を得ることができます。  
  
 <xref:System.Data.DataRowExtensions.Field%2A> は、<xref:System.Data.DataRow> の列値にアクセスするためのメソッドです。また、前出の例には使用されていませんが、<xref:System.Data.DataRowExtensions.SetField%2A> を使用すると、<xref:System.Data.DataRow> の列値を設定できます。 <xref:System.Data.DataRowExtensions.Field%2A> メソッドも <xref:System.Data.DataRowExtensions.SetField%2A> メソッドも Null 許容型を扱うことができるため、Null 値を明示的にチェックする必要はありません。 また、どちらのメソッドもジェネリック メソッドです。つまり、戻り値の型をキャストする必要はありません。 <xref:System.Data.DataRow> の既存の列アクセサー (`o["OrderDate"]` など) を使用することもできますが、その場合、返されたオブジェクトを適切な型にキャストする必要があります。  列に NULL 値が許容されている場合、<xref:System.Data.DataRow.IsNull%2A> メソッドを使って、値が NULL かどうかをチェックする必要があります。 詳細については、次を参照してください。[メソッド ジェネリック Field および SetField](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)です。  
  
 `T` メソッドおよび <xref:System.Data.DataRowExtensions.Field%2A> メソッドのジェネリック パラメーター <xref:System.Data.DataRowExtensions.SetField%2A> に指定するデータ型は、基になる値の型と一致している必要があります。一致していない場合、<xref:System.InvalidCastException> がスローされます。 指定する列の名前も <xref:System.Data.DataSet> 内の列名と一致している必要があります。一致していない場合、<xref:System.ArgumentException> がスローされます。 どちらの場合も、例外は、実行時にデータが列挙されて、クエリが実行されたときにスローされます。  
  
## <a name="see-also"></a>参照  
 [複数テーブルにまたがるクエリ](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [型指定された DataSet のクエリ](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 [ジェネリック メソッド Field および SetField](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)
