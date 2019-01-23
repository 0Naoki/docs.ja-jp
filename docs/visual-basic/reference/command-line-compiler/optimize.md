---
title: -最適化
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: ddb12eb473ce53e60835acb8f1076655f78fafd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574379"
---
# <a name="-optimize"></a>-最適化
有効またはコンパイラの最適化を無効にします。  
  
## <a name="syntax"></a>構文  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>引数  
  
|用語|定義|  
|---|---|  
|`+` &#124; `-`|任意。 `-optimize-`オプションは、コンパイラの最適化を無効になります。 `-optimize+`最適化を有効にします。 既定では、最適化が無効になります。|  
  
## <a name="remarks"></a>Remarks  
 コンパイラを最適化すると、出力ファイルのサイズが小さくなり、動作が速くなり、処理の効率が向上します。 ただし、出力ファイルにコードが再配置の最適化を行うので、`-optimize+`デバッグが困難です。  
  
 生成されるすべてのモジュール`-target:module`アセンブリを使用する必要があります、同じ`-optimize`アセンブリとして設定します。 詳細については、次を参照してください。 [-ターゲット (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)します。  
  
 組み合わせることができます、`-optimize`と`-debug`オプション。  
  
|Visual Studio 統合開発環境での最適化 - を設定するには|  
|---|  
|1.**ソリューション エクスプローラー**でプロジェクトを選択します。 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。<br />     <br />2.**[コンパイル]** タブをクリックします。<br />3.**[詳細設定]** ボタンをクリックします。<br />4.変更、**の最適化を有効にする**チェック ボックスをオンします。|  
  
## <a name="example"></a>例  
 次のコードのコンパイル`T2.vb`でき、コンパイラの最適化。  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>関連項目
- [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)
- [-デバッグ (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-ターゲット (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
