---
title: '方法 : クエリを格納および再利用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
ms.openlocfilehash: a2d16cd5dce033c563783a0882f3de73194cf2d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360139"
---
# <a name="how-to-store-and-reuse-queries"></a>方法 : クエリを格納および再利用する
同じ構造のクエリを何回も実行するアプリケーションでは、1 回コンパイルしたクエリを、パラメーターを変えて何回も実行する方が、多くの場合にパフォーマンスを向上できます。 たとえば、特定の市に住むすべての顧客を取得するアプリケーションで、ユーザーが、対象の市を実行時にフォームで指定するとします。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] はこの目的のために *コンパイル済みクエリ* の使用をサポートしています。  
  
> [!NOTE]
>  コンパイル済みクエリは、このパターンの使用法が最も一般的です。 その他にも方法は考えられます。 たとえば、デザイナーによって生成されたコードを継承した部分クラスの静的メンバーとしてコンパイル済みクエリを格納するなどです。  
  
## <a name="example"></a>例  
 スレッド境界を越えてクエリを再利用することが必要となる場合もよくあります。 その場合には、コンパイル済みクエリを静的変数に格納することは特に有効です。 次のコード例では、`Queries` クラスはコンパイル済みクエリを格納するためのクラスで、厳密に型指定された <xref:System.Data.Linq.DataContext> を表す Northwind クラスを使用することを想定しています。  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## <a name="example"></a>例  
 返す静的変数) の「ストア クエリできない現在、*匿名型*型には、汎用引数として指定する名前がないため、します。 この問題を回避する方法を次の例に示します。結果を表すことのできる型を作成し、それを汎用引数として使用しています。  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Data.Linq.CompiledQuery>  
 [クエリの概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [データベースに対するクエリの実行](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
