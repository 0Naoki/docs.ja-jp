---
title: "方法: 文字列 (LINQ) (Visual Basic) に含まれる単語の出現回数をカウント"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc367e46-f7cc-45f9-936f-754e661b7bb9
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82b40e11a72d26858cc2b0b5c0c759517f5b5ee3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-visual-basic"></a>方法: 文字列 (LINQ) (Visual Basic) に含まれる単語の出現回数をカウント
この例では、LINQ クエリを使用して、指定された単語が文字列内に出現する回数をカウントする方法を示します。 カウントを実行するには、まず <xref:System.String.Split%2A> メソッドを呼び出して単語の配列を作成します。 <xref:System.String.Split%2A> メソッドを呼び出すと、パフォーマンスが低下します。 文字列に対する操作が単語のカウントのみである場合は、<xref:System.Text.RegularExpressions.Regex.Matches%2A> または <xref:System.String.IndexOf%2A> メソッドの使用を検討してください。 ただし、パフォーマンスが重要でない場合や、他の種類のクエリを実行する目的で事前に文章を分割している場合は、LINQ を使用して単語や語句をカウントすることにも意味があります。  
  
## <a name="example"></a>例  
  
```vb  
Class CountWords  
  
    Shared Sub Main()  
  
        Dim text As String = "Historically, the world of data and the world of objects" &   
                  " have not been well integrated. Programmers work in C# or Visual Basic" &   
                  " and also in SQL or XQuery. On the one side are concepts such as classes," &   
                  " objects, fields, inheritance, and .NET Framework APIs. On the other side" &   
                  " are tables, columns, rows, nodes, and separate languages for dealing with" &   
                  " them. Data types often require translation between the two worlds; there are" &   
                  " different standard functions. Because the object world has no notion of query, a" &   
                  " query can only be represented as a string without compile-time type checking or" &   
                  " IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" &   
                  " objects in memory is often tedious and error-prone."  
  
        Dim searchTerm As String = "data"  
  
        ' Convert the string into an array of words.  
        Dim dataSource As String() = text.Split(New Char() {" ", ",", ".", ";", ":"},   
                                                 StringSplitOptions.RemoveEmptyEntries)  
  
        ' Create and execute the query. It executes immediately   
        ' because a singleton value is produced.  
        ' Use ToLower to match "data" and "Data"   
        Dim matchQuery = From word In dataSource   
                      Where word.ToLowerInvariant() = searchTerm.ToLowerInvariant()   
                      Select word  
  
        ' Count the matches.  
        Dim count As Integer = matchQuery.Count()  
        Console.WriteLine(count & " occurrence(s) of the search term """ &   
                          searchTerm & """ were found.")  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' 3 occurrence(s) of the search term "data" were found.  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 .NET Framework Version 3.5 以降を対象とするプロジェクトを作成します。System.Core.dll および System.Linq 名前空間の `Imports` ステートメントを参照設定します。  
  
## <a name="see-also"></a>関連項目  
 [LINQ と文字列 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
