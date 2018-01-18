---
title: "ローカル メソッド呼び出し"
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
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d652072d5f2e0e0cfc74d627b573389864bca9dc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="local-method-calls"></a>ローカル メソッド呼び出し
ローカル メソッド呼び出しとは、オブジェクト モデル内で実行される呼び出しです。 リモート メソッド呼び出しとは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] が SQL に変換し、データベース エンジンに送信して実行される呼び出しです。 ローカル メソッド呼び出しが必要なときに[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]SQL への呼び出しを変換することはできません。 それ以外の場合、<xref:System.InvalidOperationException>がスローされます。  
  
## <a name="example-1"></a>例 1  
 次の例では、`Order` クラスは Northwind サンプル データベースの Orders テーブルに割り当てられています。 このクラスには、ローカル インスタンス メソッドが追加されています。  
  
 クエリ 1 では、`Order` クラスのコンストラクターがローカルで実行されます。 クエリ 2 では、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] が `LocalInstanceMethod()` を SQL に変換しようとすると、処理は失敗し、<xref:System.InvalidOperationException> 例外がスローされるはずです。 しかし、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ではローカル メソッド呼び出しがサポートされているため、クエリ 2 で例外はスローされません。  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a>参照  
 [背景情報](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
