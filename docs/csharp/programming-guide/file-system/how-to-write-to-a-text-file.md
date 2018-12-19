---
title: '方法: テキスト ファイルに書き込む - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: e753f10acd33234d7f5e0c1a4203125ab880e2ae
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237143"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>方法: テキスト ファイルに書き込む (C# プログラミング ガイド)
テキストをファイルに書き込むさまざまな方法を次の例に示します。 最初の 2 つの例では、<xref:System.IO.File?displayProperty=nameWithType> クラスの便利な静的メソッドを使用して、すべての `IEnumerable<string>` の各要素と文字列をテキスト ファイルに記述しています。 例 3 は、ファイルに書き込むときに各行を個別に処理する必要がある場合にテキストをファイルに追加する方法を示します。 例 1 ～ 3 ではすべての既存の内容が上書きされます。例 4 に、既存のファイルにテキストを追加する方法を示します。  
  
 これらの例はいずれもリテラル文字列をファイルに書き込みます。 ファイルに書き込まれるテキストの書式を設定する場合は、<xref:System.String.Format%2A> メソッドまたは C# の[文字列補間](../../../csharp/language-reference/tokens/interpolated.md)機能を使用します。  
  
## <a name="example"></a>例  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 次の条件を満たす場合は、例外が発生する可能性があります。  
  
-   ファイルは存在するが、読み取り専用である。  
  
-   パス名が長すぎる。  
  
-   ディスクがいっぱいになっている。  
  
## <a name="see-also"></a>参照

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [ファイル システムとレジストリ (C# プログラミング ガイド)](../../../csharp/programming-guide/file-system/index.md)  
- [サンプル: コレクションをアプリケーション ストレージに保存する](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
