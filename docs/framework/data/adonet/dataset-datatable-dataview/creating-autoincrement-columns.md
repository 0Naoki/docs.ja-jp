---
title: AutoIncrement 列の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 9c6b5393e1928828bca001ba1d2336f09e64c22c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43536616"
---
# <a name="creating-autoincrement-columns"></a>AutoIncrement 列の作成
列値を一意にするために、新しい行がテーブルに追加されたときに列値が自動的にインクリメントされるように設定できます。 自動インクリメントを作成する<xref:System.Data.DataColumn>、設定、<xref:System.Data.DataColumn.AutoIncrement%2A>プロパティには、列の**true**します。 <xref:System.Data.DataColumn>で定義されている値から開始し、<xref:System.Data.DataColumn.AutoIncrementSeed%2A>プロパティ、各行の値を追加し、 **AutoIncrement**列で定義されている値が、<xref:System.Data.DataColumn.AutoIncrementStep%2A>列のプロパティ。  
  
 **AutoIncrement**列、お勧め、<xref:System.Data.DataColumn.ReadOnly%2A>のプロパティ、 **DataColumn**に設定する**true**します。  
  
 値 200 から開始して 3 ずつインクリメントする列を作成する方法を次の例に示します。  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Data.DataColumn>  
 [DataTable スキーマの定義](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター](https://go.microsoft.com/fwlink/?LinkId=217917)
