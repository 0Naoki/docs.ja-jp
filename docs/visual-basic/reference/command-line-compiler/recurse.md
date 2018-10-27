---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 1edb648ec574c0052b7b8314f4ada710c8b0fe01
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183335"
---
# <a name="-recurse"></a>-recurse
指定されたディレクトリまたはプロジェクト ディレクトリのいずれかのすべての子ディレクトリ内のソース コード ファイルをコンパイルします。  
  
## <a name="syntax"></a>構文  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>引数  
 `dir`  
 任意。 検索を開始するディレクトリ。 指定しない場合、プロジェクト ディレクトリで検索を開始します。  
  
 `file`  
 必須。 検索するファイル。 ワイルドカード文字を使用できます。  
  
## <a name="remarks"></a>Remarks  
 使用せず、プロジェクト ディレクトリ内のすべての一致するファイルをコンパイルするファイル名にワイルドカードを使用する`-recurse`します。 出力ファイル名が指定されていない場合、コンパイラは、処理された最初の入力ファイルに出力ファイル名を行います。 これは、一般に、アルファベット順に表示したときにコンパイルされたファイルの一覧の最初のファイルです。 このためは、使用して出力ファイルを指定することをお、`-out`オプション。  
  
> [!NOTE]
>  `-recurse`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。  
  
## <a name="example"></a>例  
 次のコマンドは、現在のディレクトリ内のすべての Visual Basic ファイルをコンパイルします。  
  
```console
vbc *.vb  
```  
  
 次のコマンドですべての Visual Basic ファイルのコンパイル、`Test\ABC`ディレクトリと、その下には、そのディレクトリし、生成`Test.ABC.dll`します。  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-除外 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
