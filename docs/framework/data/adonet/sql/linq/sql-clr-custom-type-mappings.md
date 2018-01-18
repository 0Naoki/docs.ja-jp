---
title: "SQL と CLR のカスタム型マッピング"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d916c7fb-4b56-4214-acbe-5e23365047b2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9ead5c43d295a5dc42f09deb21955de46fa1a576
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="sql-clr-custom-type-mappings"></a>SQL と CLR のカスタム型マッピング
SQL Server と共通言語ランタイム (CLR) 間の型マッピングは、SQLMetal コマンド ライン ツールのオブジェクト リレーショナル デザイナー (O/R デザイナー) を使用すると、自動的に指定されます。  
  
 カスタマイズされたマッピングが行われない場合にこれらのツールを割り当てるデフォルト型のマッピング」の説明に従って[SQL-CLR 型マッピング](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)です。 これらの既定とは異なる型マッピングを使用する場合は、型マッピングをカスタマイズする必要があります。  
  
 型マッピングをカスタマイズする場合は、中間の DBML ファイルに変更を加える方法が推奨されます。 次に、SQLMetal または O/R デザイナーでカスタマイズした DBML ファイルを使用して、コード ファイルとマッピング ファイルを作成します。  
  
 コード ファイルとマッピング ファイルから <xref:System.Data.Linq.DataContext> オブジェクトをインスタンス化すると、指定した型マッピングに従って <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> メソッドがデータベースを作成します。 マッピングに CLR の `type` 属性が指定されていない場合は、既定の型マッピングが使用されます。  
  
## <a name="customization-with-sqlmetal-or-or-designer"></a>SQLMetal または O/R デザイナーを使用したカスタマイズ  
 SQLMetal と O/R デザイナーを使用すると、コード ファイルの内外の型マッピング情報を含むオブジェクト ファイルを自動作成できます。 これらのファイルはマッピングを再作成するたびに SQLMetal または O/R デザイナーによって上書きされるため、カスタム型マッピングを指定する場合は DBML ファイルをカスタマイズする方法をお勧めします。  
  
 SQLMetal または O/R デザイナーで型マッピングをカスタマイズするには、最初に DBML ファイルを生成します。 次に、コード ファイルやマッピング ファイルを生成する前に、DBML ファイルを変更して適切な型マッピングを指定します。 SQLMetal では、DBML ファイルの `Type` 属性と `DbType` 属性を手動で変更して、型マッピングをカスタマイズする必要があります。 O/R デザイナーでは、デザイナー内で変更を加えることができます。 詳細については、O/R デザイナーを使用して、次を参照してください。 [LINQ to Visual Studio での SQL ツール](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)です。  
  
> [!NOTE]
>  一部の型マッピングでは、データベースに対する変換操作中にオーバーフローやデータ損失の例外が発生することがあります。 種類のマッピングの実行時動作の関係を見直し、 [SQL-CLR 型マッピング](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)任意のカスタマイズを行う前にします。  
  
 型マッピングのカスタマイズが SQLMetal または O/R デザイナーで認識されるためには、コード ファイルや外部のマッピング ファイルを生成するときに、必ずこれらのツールにカスタム DBML ファイルのパスを提供する必要があります。 型マッピングのカスタマイズでは必須ではありませんが、常に型マッピング情報をコード ファイルから分離し、外部の型マッピング ファイルを追加生成することをお勧めします。 コード ファイルの再コンパイルを要求しないことで、柔軟性を残しておくことができます。  
  
## <a name="incorporating-database-changes"></a>データベースの変更の組み込み  
 データベースを変更すると、DBML ファイルを更新して、これらの変更を反映する必要があります。 その 1 つの方法として、新しい DBML ファイルを自動作成してから型マッピングのカスタマイズをやり直します。 もう 1 つは、新しい DBML ファイルとカスタマイズした DBML ファイルを比較し、カスタム DBML ファイルを手動で更新してデータベースの変更を反映させる方法です。  
  
## <a name="see-also"></a>参照  
 [SQL と CLR の型マッピング](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [LINQ to SQL でのコード生成](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
