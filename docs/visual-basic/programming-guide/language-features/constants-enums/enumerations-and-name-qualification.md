---
title: 列挙型と名前修飾 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: 0336ac54c6a0dadeb9758bcb15477fe96dbfcc65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513699"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="b7595-102">列挙型と名前修飾 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7595-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="b7595-103">通常、列挙体のメンバーを指す場合は、列挙名でメンバー名を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7595-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="b7595-104">たとえばを参照する、`Sunday`のメンバー、`Days`列挙型では、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7595-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="b7595-105">Imports ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7595-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="b7595-106">完全修飾名を使用して追加することで回避できます、`Imports`ステートメントを次の例のように、コードの名前空間の宣言セクション。</span><span class="sxs-lookup"><span data-stu-id="b7595-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 <span data-ttu-id="b7595-107">`Imports`と内から参照されたプロジェクトおよびアセンブリから、ステートメントが名前空間をインポート、ステートメントが表示されるモジュールと同じプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="b7595-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="b7595-108">このステートメントを追加すると、次の例のように、修飾なしの列挙型メンバーを参照できます。</span><span class="sxs-lookup"><span data-stu-id="b7595-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 <span data-ttu-id="b7595-109">列挙型に関連する定数のセットを整理することによって、別のコンテキストで同じ定数名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7595-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="b7595-110">曜日の定数に同じ名前を使用するなど、`Days`と`WorkDays`列挙体。</span><span class="sxs-lookup"><span data-stu-id="b7595-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="b7595-111">使用する場合、`Imports`ステートメントで列挙型では、する必要がありますあいまいな参照を回避するように注意してください。</span><span class="sxs-lookup"><span data-stu-id="b7595-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="b7595-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b7595-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 <span data-ttu-id="b7595-113">仮定`Monday`両方のメンバーである、`Days`列挙と`Workdays`列挙型でこのコードはコンパイラ エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="b7595-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="b7595-114">あいまいな参照を避けるためには、個々 の定数を参照するときには、その列挙型の定数名を修飾します。</span><span class="sxs-lookup"><span data-stu-id="b7595-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="b7595-115">次のコードを指す、`Saturday`内の定数、`Days`と`WorkDays`列挙体。</span><span class="sxs-lookup"><span data-stu-id="b7595-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b7595-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7595-116">See also</span></span>
- [<span data-ttu-id="b7595-117">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="b7595-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="b7595-118">方法: 列挙体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="b7595-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="b7595-119">方法: 列挙体のメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7595-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="b7595-120">方法: Visual Basic で列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="b7595-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="b7595-121">方法: 列挙値に関連付けられている文字列を確認します。</span><span class="sxs-lookup"><span data-stu-id="b7595-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="b7595-122">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="b7595-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="b7595-123">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="b7595-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="b7595-124">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="b7595-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="b7595-125">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="b7595-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="b7595-126">データの種類</span><span class="sxs-lookup"><span data-stu-id="b7595-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
