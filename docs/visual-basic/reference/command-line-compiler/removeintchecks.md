---
title: -removeintchecks
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25a14ffaca6e61c6e3306f8ff58de441e2ba2ade
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="-removeintchecks"></a>-removeintchecks
オーバーフロー エラーのオンまたはオフ、整数演算のチェックをオンにします。  
  
## <a name="syntax"></a>構文  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>引数  
  
|用語|定義|  
|---|---|  
|`+` &#124; `-`|任意。 `-removeintchecks-`オプションは、すべての整数の計算でオーバーフロー エラーを確認するコンパイラです。 既定値は、`-removeintchecks-` です。<br /><br /> 指定する`-removeintchecks`または`-removeintchecks+`エラー チェックが回避し、高速の整数の計算を行うことができます。 エラーは次のチェックを行わないただし、し、エラーを発生させず、正しくない結果を格納することがありますデータ型の容量がオーバーフローした場合。|  
  
|Visual Studio 統合開発環境で-removeintchecks を設定するには|  
|---|  
|1.**ソリューション エクスプローラー**でプロジェクトを選択します。 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。 <br />2.**[コンパイル]** タブをクリックします。<br />3.**[詳細設定]** ボタンをクリックします。<br />4.値を変更、**整数オーバーフローのチェックを解除**ボックス。|  
  
## <a name="example"></a>例  
 次のコードのコンパイル`Test.vb`し整数オーバーフロー エラー チェックをオフにします。  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)  
 [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
