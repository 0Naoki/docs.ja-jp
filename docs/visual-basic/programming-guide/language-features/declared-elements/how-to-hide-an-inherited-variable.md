---
title: '方法: 継承された変数 (Visual Basic) を非表示にします。'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: 2b052b44043deba85c8b142a2bf1a684c1159809
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842513"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="c2e77-102">方法: 継承された変数 (Visual Basic) を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="c2e77-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>
<span data-ttu-id="c2e77-103">派生クラスでは、その基底クラスのすべての定義を継承します。</span><span class="sxs-lookup"><span data-stu-id="c2e77-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="c2e77-104">基底クラスの要素として、同じ名前を使用して変数を定義する場合は、非表示にできます、または*シャドウ*、派生クラスで、変数を定義するときにその基本クラスの要素。</span><span class="sxs-lookup"><span data-stu-id="c2e77-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="c2e77-105">これを行う場合、シャドウ機構を明示的にバイパスしない限り、派生クラスのコード、変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c2e77-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>  
  
 <span data-ttu-id="c2e77-106">継承された変数を非表示にするもう 1 つの理由は、基底クラスのリビジョンから保護するためです。</span><span class="sxs-lookup"><span data-stu-id="c2e77-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="c2e77-107">基底クラスには、継承している要素を変更する変更を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="c2e77-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="c2e77-108">この場合、`Shadows`修飾子は基底クラス要素への代わりに、変数に解決する派生クラスからの参照。</span><span class="sxs-lookup"><span data-stu-id="c2e77-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>  
  
### <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="c2e77-109">継承された変数を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="c2e77-109">To hide an inherited variable</span></span>  
  
1.  <span data-ttu-id="c2e77-110">(プロシージャ) の外側のクラス レベルで非表示にする、変数が宣言されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2e77-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="c2e77-111">それ以外の場合非表示にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c2e77-111">Otherwise you do not need to hide it.</span></span>  
  
2.  <span data-ttu-id="c2e77-112">派生クラス内で作成、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="c2e77-112">Inside your derived class, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="c2e77-113">継承された変数のと同じ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2e77-113">Use the same name as that of the inherited variable.</span></span>  
  
3.  <span data-ttu-id="c2e77-114">含める、 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)キーワードで宣言します。</span><span class="sxs-lookup"><span data-stu-id="c2e77-114">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="c2e77-115">派生クラスのコードは、変数名が参照されていると、コンパイラは、変数への参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="c2e77-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="c2e77-116">次の例では、継承された変数のシャドウを示します。</span><span class="sxs-lookup"><span data-stu-id="c2e77-116">The following example illustrates shadowing of an inherited variable.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="c2e77-117">前の例は、変数を宣言します`shadowString`基底クラスとその派生クラスでシャドウします。</span><span class="sxs-lookup"><span data-stu-id="c2e77-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="c2e77-118">プロシージャ`showStrings`派生クラスでは、シャドウのバージョンの文字列を表示します。 ときに、名前`shadowString`は修飾されません。</span><span class="sxs-lookup"><span data-stu-id="c2e77-118">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="c2e77-119">シャドウされたバージョンを次に、表示と`shadowString`で修飾されて、`MyBase`キーワード。</span><span class="sxs-lookup"><span data-stu-id="c2e77-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c2e77-120">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="c2e77-120">Robust Programming</span></span>  
 <span data-ttu-id="c2e77-121">シャドウ処理には、1 つ以上のバージョンの同じ名前の変数が導入されています。</span><span class="sxs-lookup"><span data-stu-id="c2e77-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="c2e77-122">コード ステートメントは、変数名が参照されているときに、コンパイラの参照が解決されるバージョンは、コード ステートメントの場所と該当する文字列の存在などの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c2e77-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="c2e77-123">これにより、意図しないシャドウされた変数のバージョンを参照するリスクが増加することができます。</span><span class="sxs-lookup"><span data-stu-id="c2e77-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="c2e77-124">このリスクを低くには、シャドウされた変数へのすべての参照を完全に修飾します。</span><span class="sxs-lookup"><span data-stu-id="c2e77-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e77-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2e77-125">See also</span></span>

- [<span data-ttu-id="c2e77-126">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="c2e77-126">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="c2e77-127">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="c2e77-127">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="c2e77-128">シャドウとオーバーライドの違い</span><span class="sxs-lookup"><span data-stu-id="c2e77-128">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="c2e77-129">方法: 変数と同じ名前の変数を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="c2e77-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="c2e77-130">方法: 派生クラスによって非表示に変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c2e77-130">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="c2e77-131">Overrides</span><span class="sxs-lookup"><span data-stu-id="c2e77-131">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="c2e77-132">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="c2e77-132">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="c2e77-133">継承の基本</span><span class="sxs-lookup"><span data-stu-id="c2e77-133">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
