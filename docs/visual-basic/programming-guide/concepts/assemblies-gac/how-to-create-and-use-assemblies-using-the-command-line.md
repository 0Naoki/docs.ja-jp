---
title: '方法: を作成し、コマンドライン (Visual Basic) を使用してアセンブリを使用します。'
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c02f694da4e03b666fa88ea6db8ddb2db4c9637d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>方法: を作成し、コマンドライン (Visual Basic) を使用してアセンブリを使用します。
アセンブリとは、ダイナミック リンク ライブラリ (DLL) のことで、実行時にプログラムにリンクされます。 DLL のビルド例および使用例として、次に示すシナリオを考えてみます。  
  
-   `MathLibrary.DLL`: 実行時に呼び出されるメソッドが格納されているライブラリ ファイル。 この例では、DLL には 2 つのメソッド `Add` と `Multiply` が含まれています。  
  
-   `Add`: `Add` メソッドが格納されているソース ファイル。 パラメーターの和を返します。 `Add` メソッドを含む `AddClass` クラスは `UtilityMethods` 名前空間のメンバーです。  
  
-   `Mult`: `Multiply` メソッドが格納されているソース コード。 パラメーターの積を返します。 `Multiply` メソッドを含む `MultiplyClass` クラスも `UtilityMethods` 名前空間のメンバーです。  
  
-   `TestCode`: `Main` メソッドが格納されているファイル。 DLL ファイルのメソッドを使用して、実行時引数の和と積を計算します。  
  
## <a name="example"></a>例  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 このファイルには、DLL のメソッド `Add` と `Multiply` を使用するアルゴリズムが格納されています。 最初に、コマンド ラインから入力された引数 `num1` と `num2` を解析します。 次に、`AddClass` クラスの `Add` メソッドを使用して和を計算し、`MultiplyClass` クラスの `Multiply` メソッドを使って積を計算します。  
  
 注意して、`Imports`ファイルの先頭のステートメントでは、メソッドを参照、DLL、コンパイル時に次のように、非修飾クラス名を使用することができます。  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 ディレクティブを指定しない場合は、次のように、完全修飾名を使用する必要があります。  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>実行  
 プログラムを実行するには、次のように、EXE ファイルの名前と 2 つの数値を順に入力します。  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 `MathLibrary.DLL` ファイルをビルドするには、次のコマンド ラインを使用して、`Add` ファイルと `Mult` ファイルをコンパイルします。  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 [-ターゲット (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md)コンパイラ オプション、EXE ファイルではなく、DLL を出力するようにコンパイラに指示します。 [-(Visual Basic) アウト](../../../../visual-basic/reference/command-line-compiler/out.md)DLL ファイル名を指定するファイル名を続けてコンパイラ オプションを使用します。 このオプションを指定しないと、コンパイラは最初のファイル (`Add.vb`) を DLL の名前として使用します。  
  
 実行可能ファイル `TestCode.exe` をビルドするには、次のコマンド ラインを使用します。  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 **-アウト**コンパイラ オプションは EXE ファイルを出力するようにコンパイラに指示し、出力ファイルの名前を指定 (`TestCode.exe`)。 このコンパイラ オプションは省略できます。 [-参照 (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md)コンパイラ オプションは、DLL ファイルをこのプログラムを使用するファイルを指定します。  
  
 コマンドラインからのビルドの詳細については、次を参照してください。 および[コマンドラインからのビルド](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)です。  
  
## <a name="see-also"></a>関連項目  
 [プログラミングの概念](../../../../visual-basic/programming-guide/concepts/index.md)  
 [アセンブリとグローバル アセンブリ キャッシュ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [DLL 関数を保持するクラスの作成](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
