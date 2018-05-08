---
title: インスタンスを経由する共有メンバーへのアクセスです。正規の式は評価されません。
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 035882b60c90d9a6141ad0d34b4c40682e0c32a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>インスタンスを経由する共有メンバーへのアクセスです。正規の式は評価されません。
クラスまたは構造体のインスタンス変数の使用にアクセスする、`Shared`変数、プロパティ、プロシージャ、またはそのクラスまたは構造体で定義されたイベント。 この警告は、クラスまたは定数または列挙型、または入れ子になったクラスまたは構造体などの構造体の暗黙的な共有メンバーにアクセスするインスタンス変数を使用する場合にも発生することができます。  
  
 メンバーの共有の目的は、そのメンバーの 1 つのコピーだけを作成し、その 1 つのコピーをクラスまたは構造体が宣言されているのすべてのインスタンスを使用できるようにします。 アクセスするには、この目的で一貫性が、`Shared`メンバーがそのクラスまたは構造体の個々 のインスタンスを保持する変数ではなく、そのクラスまたは構造の名前を使用します。  
  
 アクセス、`Shared`メンバー インスタンス変数を使用できますが、コード メンバーであるという事実を隠すことがわかりにくくなる`Shared`です。 さらに、このようなアクセスが、式の一部である場合などに、他の操作を実行するには`Function`共有メンバーのインスタンスを返すプロシージャでは、Visual Basic は、式と本来は実行されているその他の操作をバイパスします。  
  
 例および詳細については、次を参照してください。 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)です。  
  
 既定では、このメッセージは警告です。 警告を非表示や、警告をエラーとして扱う方法の詳細については、次を参照してください。 [Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)です。  
  
 **エラー ID:** BC42025  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   クラスまたは定義する構造体の名前を使用して、`Shared`に次の例で示すように、アクセスするメンバー。  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  スコープの効果のアラートは、2 つのプログラミング要素が同じ名前を付けるとき。 使用してインスタンスを宣言する場合、前の例で`Dim testClass as testClass = Nothing`、コンパイラはへの呼び出しを処理`testClass.sayHello()`クラス名、および警告なしでメソッドのアクセスが発生するとします。  
  
## <a name="see-also"></a>関連項目  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Visual Basic におけるスコープ](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
