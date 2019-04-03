---
title: '方法: 列挙体のメンバー (Visual Basic) を参照してください。'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: e9ea359d58dfa11f7bba7fec3d31955e18d24953
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813978"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="1437b-102">方法: 列挙体のメンバー (Visual Basic) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1437b-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="1437b-103">列挙体は、関連する定数を使用して、名前の定数値を関連付ける便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="1437b-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="1437b-104">たとえば、一連の整数型の定数を曜日に関連付けて列挙型として宣言すると、コードで整数値ではなく曜日名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1437b-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="1437b-105">完全修飾名の使用を避けることができます、`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1437b-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="1437b-106">詳細については、次を参照してください。[列挙型と名前修飾](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)します。</span><span class="sxs-lookup"><span data-stu-id="1437b-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="1437b-107">列挙体のメンバーを参照するには</span><span class="sxs-lookup"><span data-stu-id="1437b-107">To refer to an enumeration member</span></span>  
  
-   <span data-ttu-id="1437b-108">列挙体のメンバー名を修飾します。</span><span class="sxs-lookup"><span data-stu-id="1437b-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="1437b-109">たとえば、次の例が割り当てられます、`Saturday`のメンバー、`FirstDayOfWeek`列挙体を変数に`DayValue`します。</span><span class="sxs-lookup"><span data-stu-id="1437b-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="1437b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="1437b-110">See also</span></span>

- [<span data-ttu-id="1437b-111">方法: 列挙体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="1437b-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="1437b-112">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="1437b-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="1437b-113">方法: Visual Basic で列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="1437b-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="1437b-114">方法: 列挙値に関連付けられている文字列を確認します。</span><span class="sxs-lookup"><span data-stu-id="1437b-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="1437b-115">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="1437b-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
