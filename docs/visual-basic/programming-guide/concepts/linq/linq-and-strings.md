---
title: "LINQ と文字列 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b615f3dc76d72e7f73146498e0143f88c52278a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="linq-and-strings-visual-basic"></a>LINQ と文字列 (Visual Basic)
文字列やそのコレクションは、LINQ を使って照会したり変換したりすることができます。 特に、テキスト ファイル内の半構造化されたデータでその利便性が発揮されます。 LINQ クエリは、従来の文字列関数や正規表現と組み合わせることができます。 たとえば、<xref:System.String.Split%2A> または <xref:System.Text.RegularExpressions.Regex.Split%2A> メソッドを使用して、文字列の配列を作成し、その後で LINQ を使用してクエリを実行したり変更したりすることができます。 LINQ クエリの `where` 句で <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> メソッドを使用できます。 LINQ を使用して、正規表現によって返される <xref:System.Text.RegularExpressions.MatchCollection> の結果に対してクエリを実行したり変更したりすることができます。  
  
 このセクションで説明する手法を使えば、半構造化されたテキスト データを XML に変換することもできます。 詳細については、「[方法: CSV ファイルから XML を生成する](how-to-generate-xml-from-csv-files.md)」を参照してください。  
  
 このセクションの例は、次の 2 つのカテゴリに分かれています。  
  
## <a name="querying-a-block-of-text"></a>テキスト ブロックの照会  
 <xref:System.String.Split%2A> メソッドまたは <xref:System.Text.RegularExpressions.Regex.Split%2A> メソッドを使用して、テキスト ブロックをクエリ可能な小さな文字列の配列に分割することによって、テキスト ブロックのクエリ、分析、および変更を実行できます。 単語や文、段落、ページなどの単位にソース テキストを分割できるほか、クエリ内で必要であれば、さらに細かく分割することもできます。  
  
 [方法: 文字列 (LINQ) (Visual Basic) に含まれる単語の出現回数をカウント](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 テキストに対する単純なクエリを LINQ で行う方法が紹介されています。  
  
 [方法: 指定された単語 (LINQ) (Visual Basic) のセットを含む文章を照会します。](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 区切りを指定してテキスト ファイルを分割する方法やその各構成要素に対してクエリを実行する方法が紹介されています。  
  
 [方法: 文字列 (LINQ) (Visual Basic) 内の文字に対するクエリ](how-to-query-for-characters-in-a-string-linq.md)  
 文字列がクエリ可能型であることを実証します。  
  
 [方法: LINQ クエリを正規表現 (Visual Basic) とを組み合わせる](how-to-combine-linq-queries-with-regular-expressions.md)  
 LINQ クエリで正規表現を使い、フィルター処理されたクエリ結果に対して複雑なパターン マッチを行う方法が紹介されています。  
  
## <a name="querying-semi-structured-data-in-text-format"></a>半構造化されたテキスト形式データのクエリ  
 テキスト ファイルにはさまざまな種類がありますが、タブ区切りファイルやコンマ区切りファイル、固定長行など同様の形式を持った一連の行で構成されていることは少なくありません。 そのようなテキスト ファイルをメモリに読み込んだ後、LINQ を使って、必要な行を照会したり編集したりすることができます。 複数ソースからのデータを組み合わせる作業も LINQ クエリなら簡単に行うことができます。  
  
 [方法: 2 つのリスト (LINQ) (Visual Basic) の差集合を検索](how-to-find-the-set-difference-between-two-lists-linq.md)  
 ある特定のリストには存在しているものの、それ以外には存在しない文字列をすべて探す方法が紹介されています。  
  
 [方法: 並べ替えまたはフィルター テキスト データで任意の単語またはフィールド (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 単語やフィールドに基づいてテキスト行を並べ替える方法が紹介されています。  
  
 [方法: 区切り記号入りファイル (LINQ) (Visual Basic) のフィールドの順序を変更](how-to-reorder-the-fields-of-a-delimited-file.md)  
 .csv ファイルの行に含まれるフィールドを並べ替える方法が紹介されています。  
  
 [方法: 結合および比較文字列のコレクションに (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)  
 文字列リストをさまざまな方法で結合する方法が紹介されています。  
  
 [方法: 複数のソース (LINQ) (Visual Basic) からオブジェクトのコレクションへの追加](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 複数のテキスト ファイルをデータ ソースとしてオブジェクトのコレクションを作成する方法が紹介されています。  
  
 [方法: 異種ファイル (LINQ) (Visual Basic) からコンテンツを結合します。](how-to-join-content-from-dissimilar-files-linq.md)  
 2 つのリストに含まれる文字列を、一致するキーを使って 1 つの文字列に結合する方法が紹介されています。  
  
 [方法: 複数のファイルのファイル グループ (LINQ) (Visual Basic) を使用して分割](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 1 つのファイルをデータ ソースとして新しいファイルを作成する方法が紹介されています。  
  
 [方法: CSV テキスト ファイル (LINQ) (Visual Basic) で列の値を計算](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 .csv ファイルでテキスト データに対して数学的計算を実行する方法が紹介されています。  
  
## <a name="see-also"></a>関連項目  
 [統合言語クエリ (LINQ) (Visual Basic)](index.md)  
 [方法: CSV ファイルから XML を生成する](how-to-generate-xml-from-csv-files.md)
