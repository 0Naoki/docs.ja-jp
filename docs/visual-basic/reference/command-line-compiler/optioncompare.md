---
title: /optioncompare
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 62a9a4bf3428f3ee731e7ecc63be51dbf3076ee4
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="optioncompare"></a>/optioncompare
文字列比較の方法を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>コメント  
 指定できます`/optioncompare`で 2 つの形式のいずれかの:`/optioncompare:binary`バイナリ文字列比較を使用して`/optioncompare:text`テキスト文字列の比較を使用します。 既定では、コンパイラを使用して`/optioncompare:binary`です。  
  
 Microsoft Windows では、使用されているコード ページは、バイナリ並べ替え順を決定します。 通常、バイナリ並べ替え順序は次のとおりです。  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 テキストに基づく文字列比較は、システムのロケールによって決まる、大文字と小文字のテキストの並べ替え順序に基づきます。 一般的なテキストの並べ替え順序は次のとおりです。  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a>Visual Studio IDE で/optioncompare を設定するには  
  
1.  **ソリューション エクスプローラー**でプロジェクトを選択します。 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。   
  
2.  **[コンパイル]** タブをクリックします。  
  
3.  値を変更、 **Option Compare**ボックス。  
  
### <a name="to-set-optioncompare-programmatically"></a>/Optioncompare をコードから設定するには  
  
-   参照してください[Option Compare ステートメント](../../../visual-basic/language-reference/statements/option-compare-statement.md)です。  
  
## <a name="example"></a>例  
 次のコードのコンパイル`ProjFile.vb`バイナリ文字列比較を使用しています。  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>参照  
 [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Option Compare ステートメント](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
