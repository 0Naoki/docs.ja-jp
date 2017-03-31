---
title: "プログラミング ガイド (LINQ to XML) (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4b1ffd10-ab81-4a0d-a0ca-e9876478d924
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5e1e95d92123b2874aace0c36005a8a07a6203fc
ms.lasthandoff: 03/13/2017

---
# <a name="programming-guide-linq-to-xml-c"></a>プログラミング ガイド (LINQ to XML) (C#)
ここでは、[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] を使用したプログラミングに関する概念と方法の情報について説明します。  
  
## <a name="who-should-read-this-documentation"></a>このドキュメントの対象読者  
 このドキュメントは、C# や [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] の基本的な側面について既に理解している開発者を対象としています。  
  
 このドキュメントの目的は、多数の開発者が [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] を簡単に使用できるようにすることです。 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] によって、XML プログラミングが容易になります。 
           を使用するために上級開発者になる必要はありません。  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] は、ジェネリック クラスに大きく依存しています。 そのため、ジェネリック クラスの使用について理解することが非常に重要です。 また、パラメーター化された型として宣言されるデリゲートに関する知識があると役立ちます。 C# のジェネリック クラスに慣れていない場合は、「[ジェネリック クラス](../../../../csharp/programming-guide/generics/generic-classes.md)」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|トピック|説明|  
|-----------|-----------------|  
|[LINQ to XML プログラミングの概要 (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)|[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] クラスの概要と、最も重要な 3 つのクラス (<xref:System.Xml.Linq.XElement>、<xref:System.Xml.Linq.XAttribute>、<xref:System.Xml.Linq.XDocument>) に関する詳細情報について説明します。|  
|[XML ツリーの作成 (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)|XML ツリーの作成に関する概念とタスク ベースの情報について説明します。 XML ツリーを作成するには、関数型構築を使用するか、文字列またはファイルから XML テキストを解析します。 <xref:System.Xml.XmlReader> を使用して XML ツリーを設定することもできます。|  
|[XML 名前空間の使用 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)|名前空間を使用する XML ツリーの作成に関する詳細情報について説明します。|  
|[XML ツリーのシリアル化 (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)|XML ツリーをシリアル化する複数の方法について説明し、どの方法を使用するかについてのガイダンスを紹介します。|  
|[LINQ to XML 軸 (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)|[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 軸メソッドを列挙して説明します。[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] クエリを記述する場合は、あらかじめこれらの軸メソッドについて理解しておく必要があります。|  
|[XML ツリーのクエリ (C#)](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)|XML ツリーのクエリの一般的な例について説明します。|  
|[XML ツリーの変更 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)|ドキュメント オブジェクト モデル (DOM) と同様、[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] では XML ツリーを直接変更できます。|  
|[高度な LINQ to XML プログラミング (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)|注釈、イベント、ストリーミング、およびその他の高度なシナリオに関する情報について説明します。|  
|[LINQ to XML のセキュリティ (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-security.md)|LINQ to XML に関連するセキュリティの問題について説明し、セキュリティ上の脆弱性を改善するためのガイダンスを紹介します。|  
|[サンプル XML ドキュメント (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)|このドキュメントの多数の例で使用されているサンプル XML ドキュメントが含まれています。|  
  
## <a name="see-also"></a>関連項目  
 [はじめに (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)   
 [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)
