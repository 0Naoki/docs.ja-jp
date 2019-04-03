---
title: '方法: プロパティ プロシージャ (Visual Basic) を呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 7b85239f80b4bfa87d1dbb1e3207e63d0cef7eeb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827212"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="6bde3-102">方法: プロパティ プロシージャ (Visual Basic) を呼び出す</span><span class="sxs-lookup"><span data-stu-id="6bde3-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="6bde3-103">プロパティ プロシージャを呼び出すには、「プロパティ値を保存するか値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="6bde3-104">プロパティは変数にアクセスする同じ方法でアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6bde3-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="6bde3-105">プロパティの`Set`プロシージャは、値を格納し、その`Get`プロシージャが値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="6bde3-106">ただし、明示的に呼び出さないこれらのプロシージャ名で。</span><span class="sxs-lookup"><span data-stu-id="6bde3-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="6bde3-107">格納または変数の値を取得すると同様、代入ステートメントまたは式のプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="6bde3-108">Visual Basic では、プロパティのプロシージャ呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="6bde3-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="6bde3-109">プロパティの Get プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="6bde3-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="6bde3-110">式、変数名を使用する場合と同じ方法でプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="6bde3-111">プロパティを使用する変数または定数を使用する任意の場所。</span><span class="sxs-lookup"><span data-stu-id="6bde3-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="6bde3-112">- または -</span><span class="sxs-lookup"><span data-stu-id="6bde3-112">-or-</span></span>  
  
     <span data-ttu-id="6bde3-113">等号の後、プロパティ名を使用して (`=`)、代入ステートメントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6bde3-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="6bde3-114">次の例の値を読み取る、<xref:Microsoft.VisualBasic.DateAndTime.Now%2A>プロパティ、暗黙的に呼び出すその`Get`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="6bde3-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2.  <span data-ttu-id="6bde3-115">プロパティが引数を受け取る場合は、次の引数リストを囲むためにかっこによるプロパティ名。</span><span class="sxs-lookup"><span data-stu-id="6bde3-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="6bde3-116">引数がない場合、かっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="6bde3-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="6bde3-117">コンマで区切り、かっこ内の引数リストで、引数を配置します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="6bde3-118">プロパティが、対応するパラメーターを定義するのと同じ順序で引数を指定してください。</span><span class="sxs-lookup"><span data-stu-id="6bde3-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="6bde3-119">プロパティの値が、式、変数と同様に参加する定数または変数または代入ステートメントの左側にあるプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6bde3-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="6bde3-120">プロパティを呼び出すための Set でプロシージャ</span><span class="sxs-lookup"><span data-stu-id="6bde3-120">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="6bde3-121">代入ステートメントの左側にあるプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="6bde3-122">次の例の値の設定、<xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>プロパティ、暗黙的に呼び出して、`Set`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="6bde3-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2.  <span data-ttu-id="6bde3-123">プロパティが引数を受け取る場合は、次の引数リストを囲むためにかっこによるプロパティ名。</span><span class="sxs-lookup"><span data-stu-id="6bde3-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="6bde3-124">引数がない場合、かっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="6bde3-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="6bde3-125">コンマで区切り、かっこ内の引数リストで、引数を配置します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="6bde3-126">プロパティが、対応するパラメーターを定義するのと同じ順序で引数を指定してください。</span><span class="sxs-lookup"><span data-stu-id="6bde3-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="6bde3-127">代入ステートメントの右側にある生成された値は、プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6bde3-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bde3-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bde3-128">See also</span></span>

- [<span data-ttu-id="6bde3-129">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="6bde3-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="6bde3-130">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="6bde3-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6bde3-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="6bde3-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="6bde3-132">Visual Basic でのプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="6bde3-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="6bde3-133">方法: プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="6bde3-134">方法: 混合アクセス レベルを持つプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="6bde3-135">方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="6bde3-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="6bde3-136">方法: プロパティに値を格納します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="6bde3-137">方法: プロパティから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6bde3-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="6bde3-138">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="6bde3-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="6bde3-139">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="6bde3-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
