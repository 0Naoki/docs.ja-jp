---
title: "コレクション クラスの選択"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- last-in-first-out collections
- first-in-first-out collections
- collections [.NET Framework], selecting collection class
- indexed collections
- Collections classes
- grouping data in collections, selecting collection class
ms.assetid: ba049f9a-ce87-4cc4-b319-3f75c8ddac8a
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64b50839a5500b671a4bd5dd92eec2f0db9787a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="selecting-a-collection-class"></a>コレクション クラスの選択
コレクション クラスは慎重に選択してください。 間違った型を使用すると、コレクションの使用が制限されることがあります。 一般に、.NET Framework バージョン 1.1 を特に対象としている場合を除いて、<xref:System.Collections> 名前空間にある型は使用しないでください。 タイプ セーフの強化や他の改善があるため、コレクションの汎用および同時実行バージョンをお勧めします。  
  
 以下の質問を検討します。  
  
-   値が取得された後に要素が通常は破棄されるシーケンシャル リストが必要ですか。  
  
    -   そうである場合は、先入れ先出し (FIFO) の動作が必要であれば、<xref:System.Collections.Queue> クラスまたは <xref:System.Collections.Generic.Queue%601> ジェネリック クラスの使用を検討してください。 後入れ先出し (LIFO) の動作が必要であれば、<xref:System.Collections.Stack> クラスまたは <xref:System.Collections.Generic.Stack%601> ジェネリック クラスの使用を検討します。 複数のスレッドから安全にアクセスできるように、同時実行バージョンの <xref:System.Collections.Concurrent.ConcurrentQueue%601> と <xref:System.Collections.Concurrent.ConcurrentStack%601> を使用します。  
  
    -   それ以外の場合は、その他のコレクションの使用を検討してください。  
  
-   FIFO や LIFO など特定の順序で要素にアクセスする必要がありますか。またはランダムにアクセスできますか。  
  
    -   <xref:System.Collections.Queue> クラスおよび <xref:System.Collections.Generic.Queue%601> または <xref:System.Collections.Concurrent.ConcurrentQueue%601> ジェネリック クラスは、FIFO アクセスを提供します。 詳細については、「[スレッド セーフなコレクションを使用する状況](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md)」をご覧ください。  
  
    -   <xref:System.Collections.Stack> クラスおよび <xref:System.Collections.Generic.Stack%601> または <xref:System.Collections.Concurrent.ConcurrentStack%601> ジェネリック クラスは、LIFO アクセスを提供します。 詳細については、「[スレッド セーフなコレクションを使用する状況](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md)」をご覧ください。  
  
    -   <xref:System.Collections.Generic.LinkedList%601> ジェネリック クラスは、先頭から末尾または末尾から先頭への順次アクセスを可能にします。  
  
-   インデックスで各要素にアクセスする必要があるでしょうか。  
  
    -   <xref:System.Collections.ArrayList> と <xref:System.Collections.Specialized.StringCollection> クラス、および <xref:System.Collections.Generic.List%601> ジェネリック クラスは、要素の 0 から始まるインデックスによってその要素へのアクセスを提供します。  
  
    -   <xref:System.Collections.Hashtable>、<xref:System.Collections.SortedList>、<xref:System.Collections.Specialized.ListDictionary>、<xref:System.Collections.Specialized.StringDictionary> クラス、および <xref:System.Collections.Generic.Dictionary%602>、<xref:System.Collections.Generic.SortedDictionary%602> ジェネリック クラスは、要素のキーによってその要素へのアクセスを提供します。  
  
    -   <xref:System.Collections.Specialized.NameObjectCollectionBase> と <xref:System.Collections.Specialized.NameValueCollection> クラス、および <xref:System.Collections.ObjectModel.KeyedCollection%602> と <xref:System.Collections.Generic.SortedList%602> ジェネリック クラスは、要素の 0 から始まるインデックスまたはキーのいずれかによって、その要素へのアクセスを提供します。  
  
-   各要素に含まれることになるのは、1 つの値、1 つのキーと 1 つの値の組み合わせ、または 1 つのキーと複数の値の組み合わせのどれですか。  
  
    -   1 つの値: <xref:System.Collections.IList> インターフェイスまたは <xref:System.Collections.Generic.IList%601> ジェネリック インターフェイスに基づくいずれかのコレクションを使用します。  
  
    -   1 つのキーと 1 つの値: <xref:System.Collections.IDictionary> インターフェイスまたは <xref:System.Collections.Generic.IDictionary%602> ジェネリック インターフェイスに基づくいずれかのコレクションを使用します。  
  
    -   埋め込みのキーを持つ 1 つの値: <xref:System.Collections.ObjectModel.KeyedCollection%602> ジェネリック クラスを使用します。  
  
    -   複数の値を持つ 1 つのキー: <xref:System.Collections.Specialized.NameValueCollection> クラスを使用します。  
  
-   要素を入力されたときとは異なる方法で並べ替える必要がありますか。  
  
    -   <xref:System.Collections.Hashtable> クラスは、ハッシュ コードによってその要素を並べ替えます。  
  
    -   <xref:System.Collections.SortedList> クラスおよび <xref:System.Collections.Generic.SortedDictionary%602> と <xref:System.Collections.Generic.SortedList%602> ジェネリック クラスは、<xref:System.Collections.IComparer> インターフェイスおよび <xref:System.Collections.Generic.IComparer%601> ジェネリック インターフェイスの実装に基づいて、キーによってその要素を並べ替えます。  
  
    -   <xref:System.Collections.ArrayList> は、<xref:System.Collections.IComparer> 実装をパラメーターとして受け取る、<xref:System.Collections.ArrayList.Sort%2A> メソッドを提供します。 それに対応するジェネリックである <xref:System.Collections.Generic.List%601> ジェネリック クラスは、<xref:System.Collections.Generic.IComparer%601> ジェネリック インターフェイスの実装をパラメーターとして受け取る、<xref:System.Collections.Generic.List%601.Sort%2A> メソッドを提供します。  
  
-   高速な検索と情報の取得が必要ですか。  
  
    -   <xref:System.Collections.Specialized.ListDictionary> は、小規模なコレクション (10 個以下のアイテム) では <xref:System.Collections.Hashtable> より高速です。 <xref:System.Collections.Generic.Dictionary%602> ジェネリック クラスは、<xref:System.Collections.Generic.SortedDictionary%602> ジェネリック クラスよりも高速の参照を提供します。 マルチスレッドの実装は <xref:System.Collections.Concurrent.ConcurrentDictionary%602> です。 <xref:System.Collections.Concurrent.ConcurrentBag%601> は、順序指定されていないデータのために、高速なマルチスレッドの挿入を提供します。 両方のマルチスレッドのタイプについては、「[スレッド セーフなコレクションを使用する状況](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md)」を参照してください。  
  
-   文字列だけを受け入れるコレクションは必要ですか。  
  
    -   <xref:System.Collections.Specialized.StringCollection> (<xref:System.Collections.IList> に基づく) および <xref:System.Collections.Specialized.StringDictionary> (<xref:System.Collections.IDictionary> に基づく) は、<xref:System.Collections.Specialized> 名前空間にあります。  
  
    -   さらに、ジェネリック型の引数として <xref:System.String> クラスを指定することにより、<xref:System.Collections.Generic> 名前空間にある任意のジェネリック コレクション クラスを厳密に型指定された文字列コレクションとして使用できます。  
  
## <a name="linq-to-objects-and-plinq"></a>LINQ to Objects および PLINQ  
 LINQ to Objects により、開発者は、オブジェクト型で <xref:System.Collections.IEnumerable> または <xref:System.Collections.Generic.IEnumerable%601> を実装している限り、LINQ クエリを使用してインメモリ オブジェクトにアクセスできます。 LINQ クエリはデータ アクセス用の一般的なパターンです。通常、これは標準の `foreach` ループよりも簡潔で読みやすく、フィルター処理、並べ替え、およびグループ化機能を備えています。 詳細については、「[LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)」を参照してください。  
  
 PLINQ は、マルチコア コンピューターをより効率的に使用することにより、多くのシナリオでより高速にクエリを実行できる LINQ to Objects の並列実装を提供します。 詳細については、「[Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Collections>  
 <xref:System.Collections.Specialized>  
 <xref:System.Collections.Generic>  
 [スレッドセーフなコレクション](../../../docs/standard/collections/thread-safe/index.md)
