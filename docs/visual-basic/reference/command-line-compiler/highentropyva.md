---
title: /highentropyva (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55568808bb94f98ce7a20016fc5a2a0a2ef23a38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="highentropyva-visual-basic"></a>/highentropyva (Visual Basic)
示す、64 ビット実行可能ファイルまたは実行可能ファイルでマークされているかどうか、 [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)コンパイラ オプションで高エントロピ ASLR Address Space レイアウトのランダム化 () をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>引数  
 `+` &#124; `-`  
 省略可能です。 オプションは既定で無効または指定したかどうかは`/highentropyva-`します。 指定したかどうか、オプションで`/highentropyva`または`/highentropyva+`です。  
  
## <a name="remarks"></a>コメント  
 このオプションを指定する場合、互換性のあるバージョンの Windows カーネルは、カーネル プロセスのアドレス領域のレイアウトを ASLR の一部としてランダムにときにより高度なエントロピを使用できます。 カーネルより高度なエントロピを使用している場合、アドレスの数が多いをスタックとヒープなどのメモリ領域に割り当てられることができます。 これによって特定のメモリ領域の位置を推測しづらくなる効果が得られます。  
  
 オプションがオンで、ターゲットの実行可能ファイルとすべてのモジュールは、ポインター値は、これらのモジュールは、64 ビット プロセスとして実行しているときに、4 ギガバイト (GB) より大きいを処理することが依存している必要があります。  
  
## <a name="see-also"></a>関連項目  
 [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)  
 [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
