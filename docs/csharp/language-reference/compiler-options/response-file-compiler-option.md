---
title: '@ (C# コンパイラ オプション)'
ms.date: 07/20/2015
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
ms.openlocfilehash: f342f26ee8abe29e6c5a1477469c8b7292cd702e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43456504"
---
# <a name="-c-compiler-options"></a>@ (C# コンパイラ オプション)
@ オプションを使用すると、コンパイラ オプションおよびコンパイルするソース コード ファイルを含むファイルを指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>引数  
 `response_file`  
 コンパイラ オプションやコンパイルするソース コード ファイルの一覧を含むファイルです。  
  
## <a name="remarks"></a>コメント  
 コンパイラ オプションとソース コード ファイルは、コマンド ラインで指定した場合と同じように、コンパイラによって処理されます。  
  
 コンパイル時に複数の応答ファイルを指定するには、複数の応答ファイル オプションを指定します。 例:  
  
```  
@file1.rsp @file2.rsp  
```  
  
 応答ファイルでは、複数のコンパイラ オプションとソース コード ファイルを 1 行に記述できます。 1 つのコンパイラ オプションは 1 行に指定する必要があり、複数行にわたって指定できません。 応答ファイルには、シャープ記号 (#) で始まるコメントを記述できます。  
  
 応答ファイルでのコンパイラ オプションの指定方法は、コマンド ラインでのコンパイラ オプションの指定方法と同じです。 詳細については、「[Building from the Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)」(コマンド ラインからのビルド) を参照してください。  
  
 コンパイラは、検出した順にコマンド オプションを処理します。 このため、コマンド ライン引数によって、応答ファイルで先に指定したオプションをオーバーライドできます。 逆に、応答ファイルのオプションが、コマンド ラインや他の応答ファイルで先に指定したオプションをオーバーライドすることもあります。  
  
 C# では、csc.exe ファイルと同じディレクトリに csc.rsp ファイルがあります。 csc.rsp の詳細については、「[-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)」を参照してください。  
  
 このコンパイラ オプションは、Visual Studio 開発環境で設定することはできません。また、プログラムで変更することもできません。  
  
## <a name="example"></a>例  
 サンプルの応答ファイルの一部を次に示します。  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a>参照  

- [C# コンパイラ オプション](../../../csharp/language-reference/compiler-options/index.md)
