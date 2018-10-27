---
title: コンパイル コマンド ラインのサンプル (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: c4c3214c4998afa23032347e08007f2f1933bba8
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181122"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>コンパイル コマンドラインのサンプル (Visual Basic)
Visual Studio 内から Visual Basic プログラムをコンパイルする代わりに、実行可能ファイル (.exe) ファイルまたはダイナミック リンク ライブラリ (.dll) ファイルを生成するためにコマンドラインからコンパイルすることができます。  
  
 Visual Basic のコマンド ライン コンパイラでは、入力を制御し、ファイル、アセンブリ、およびデバッグ、およびプリプロセッサ オプションの出力オプションの完全なセットをサポートします。 各オプションは 2 つの交換形式で使用できます:`-option`と`/option`します。 このドキュメントの表示のみ、`-option`フォーム。  
  
 次の表では、独自の用途を変更するサンプルのコマンドラインを示します。  
  
|終了|使用|  
|--------|---------|  
|.Vb というファイルをコンパイルして File.exe を作成します。|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|.Vb というファイルをコンパイルして File.dll を作成します。|`vbc -target:library File.vb`|  
|.Vb というファイルをコンパイルして My.exe を作成します。|`vbc -out:My.exe File.vb`|  
|.Vb というファイルをコンパイルし、ライブラリと File.dll をという名前の参照アセンブリの両方を作成|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|最適化で、現在のディレクトリ内のすべての Visual Basic ファイルをコンパイルして、 `DEBUG` File2.exe を生成するシンボルを定義するには、|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|ロゴや警告を表示せず、デバッグ バージョンの File2.dll を作成、現在のディレクトリ内のすべての Visual Basic ファイルをコンパイルします。|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|Something.dll に現在のディレクトリ内のすべての Visual Basic ファイルをコンパイルします。|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  関連付けられているに関する情報を表示するには、Visual Studio IDE を使用してプロジェクトをビルドするときに**vbc**出力 ウィンドウでのコンパイラ オプションがコマンド。 この情報を表示するには、開く、[オプション ダイアログ ボックス、プロジェクトとソリューションをビルドおよび実行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)、し、設定、 **MSBuild プロジェクト ビルドの出力の詳細**に**標準**または、詳細度の高いレベル。   
  
## <a name="see-also"></a>関連項目  
 [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)  
 [条件付きコンパイル](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
