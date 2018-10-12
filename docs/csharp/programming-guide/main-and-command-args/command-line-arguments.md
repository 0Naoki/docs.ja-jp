---
title: コマンド ライン引数 (C# プログラミング ガイド)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
ms.openlocfilehash: a55e40a4a4880c39c74186c55b0886e06dc33bcb
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083950"
---
# <a name="command-line-arguments-c-programming-guide"></a>コマンド ライン引数 (C# プログラミング ガイド)
`Main` メソッドに引数を渡すには、次のいずれかの方法でメソッドを定義します。  
  
 [!code-csharp[csProgGuideMain#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_1.cs)]  
  
 [!code-csharp[csProgGuideMain#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_2.cs)]  
  
> [!NOTE]
>  Windows フォーム アプリケーションの `Main` メソッドでコマンド ライン引数を有効にするには、program.cs の `Main` のシグネチャを手動で変更する必要があります。 Windows フォーム デザイナーが生成するコードは、入力パラメーターなしの `Main` を作成します。 <xref:System.Environment.CommandLine%2A?displayProperty=nameWithType> または <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=nameWithType> を使用して、コンソールまたは Windows アプリケーション内の任意の場所からコマンド ライン引数にアクセスすることもできます。  
  
 `Main` メソッドのパラメーターは <xref:System.String> の配列で、コマンド ライン引数を表しています。 通常は、`Length` プロパティを調べて引数があるかどうかを確認します。次はその例です。  
  
 [!code-csharp[csProgGuideMain#4](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_3.cs)]  
  
 また、<xref:System.Convert> クラスまたは `Parse` メソッドを使って、文字列型の引数を数値型に変換できます。 たとえば、次のステートメントでは、`string` メソッドを使用して `long` を <xref:System.Int64.Parse%2A> 値に変換します。  
  
```  
long num = Int64.Parse(args[0]);  
```  
  
 C# の `long` 型を使うこともできます。これは `Int64` のエイリアスです。  
  
```  
long num = long.Parse(args[0]);  
```  
  
 また、同じ変換に `Convert` クラスの `ToInt64` メソッドを使うこともできます。  
  
```  
long num = Convert.ToInt64(s);  
```  
  
 詳細については、<xref:System.Int64.Parse%2A> および <xref:System.Convert> を参照してください。  
  
## <a name="example"></a>例  
 コンソール アプリケーションでコマンド ライン引数を使用する方法の例を次に示します。 アプリケーションは、実行時に引数を 1 つ受け取り、整数に変換し、その値の階乗を計算しています。 引数がない場合は、アプリケーションの正しい使用方法を説明するメッセージを表示します。  
  
 コマンド プロンプトからアプリケーションをコンパイルして実行するには、次の手順を実行します。  
  
1.  次のコードをテキスト エディターに貼り付け、`Factorial.cs` という名前でテキスト ファイルとして保存します。  
  
     [!code-csharp[csProgGuideMain#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_4.cs)]  
  
2.  **[スタート]** 画面または **[スタート]** メニューから、Visual Studio の **[開発者コマンド プロンプト]** ウィンドウを開き、先ほど作成したファイルが含まれているフォルダーに移動します。  
  
3.  次のコマンドを入力してアプリケーションをコンパイルします。  
  
     `csc Factorial.cs`  
  
     アプリケーションにコンパイル エラーがなければ、`Factorial.exe` という名前の実行可能ファイルが作成されます。  
  
4.  3 の階乗を計算する次のコマンドを入力します。  
  
     `Factorial 3`  
  
5.  次の出力が生成されます: `The factorial of 3 is 6.`  
  
> [!NOTE]
>  Visual Studio でアプリケーションを実行する場合、「[[デバッグ] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/debug-page-project-designer)」のコマンド ライン引数を指定できます。  
  
 コマンド ライン引数の使用方法の例については、「[方法: コマンド ラインを使用してアセンブリを作成および使用する](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)」を参照してください。  
  
## <a name="see-also"></a>参照

- <xref:System.Environment?displayProperty=nameWithType>  
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [Main() とコマンド ライン引数](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [方法: コマンド ライン引数を表示する](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
- [方法: foreach を使用してコマンド ライン引数にアクセスする](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
- [Main() の戻り値](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
- [クラス](../../../csharp/programming-guide/classes-and-structs/classes.md)
