---
title: 正しいシグネチャを持つ、アクセス可能な 'Main' メソッドは、'<name>' に見つかりませんでした。
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: b3aa66416f0cad6a6fb29a20aa0bca5e3486a18e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275432"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>適切なシグネチャを持つアクセス可能な 'Main' メソッドが見つかりませんでした '\<名 >'
コマンド ライン アプリケーションが必要、`Sub Main`定義します。 `Main` として宣言する必要があります`Public Shared`クラス、またはとして定義されている場合`Public`モジュールで定義されている場合。  
  
 **エラー ID:** BC30737  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   定義、`Public Sub Main`プロジェクト用のプロシージャです。 として宣言`Shared`クラス内で定義する場合にのみです。  
  
## <a name="see-also"></a>関連項目
- [Visual Basic プログラムの構造](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/index.md)
