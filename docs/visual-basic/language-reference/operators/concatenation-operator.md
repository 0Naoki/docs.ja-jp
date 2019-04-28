---
title: '&amp; 演算子 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: dd85363447e9b405241d608550d9484b4760a739
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778587"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="cd28b-102">&amp; 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd28b-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="cd28b-103">2 つの式の文字列の連結を生成します。</span><span class="sxs-lookup"><span data-stu-id="cd28b-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd28b-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd28b-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="cd28b-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="cd28b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="cd28b-106">必須。</span><span class="sxs-lookup"><span data-stu-id="cd28b-106">Required.</span></span> <span data-ttu-id="cd28b-107">すべて`String`または`Object`変数。</span><span class="sxs-lookup"><span data-stu-id="cd28b-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="cd28b-108">必須。</span><span class="sxs-lookup"><span data-stu-id="cd28b-108">Required.</span></span> <span data-ttu-id="cd28b-109">任意の式を拡張するデータ型を持つ`String`します。</span><span class="sxs-lookup"><span data-stu-id="cd28b-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="cd28b-110">必須。</span><span class="sxs-lookup"><span data-stu-id="cd28b-110">Required.</span></span> <span data-ttu-id="cd28b-111">任意の式を拡張するデータ型を持つ`String`します。</span><span class="sxs-lookup"><span data-stu-id="cd28b-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd28b-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="cd28b-112">Remarks</span></span>  
 <span data-ttu-id="cd28b-113">データ型の場合`expression1`または`expression2`ない`String`に拡大変換されますが、`String`に変換されます`String`します。</span><span class="sxs-lookup"><span data-stu-id="cd28b-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="cd28b-114">かどうか、データ型のいずれかが拡大変換されないに`String`、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cd28b-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="cd28b-115">データ型`result`は`String`します。</span><span class="sxs-lookup"><span data-stu-id="cd28b-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="cd28b-116">1 つまたは両方の式に評価される場合[Nothing](../../../visual-basic/language-reference/nothing.md)またはの値に<xref:System.DBNull.Value?displayProperty=nameWithType>の値を文字列として扱われます""です。</span><span class="sxs-lookup"><span data-stu-id="cd28b-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd28b-117">`&`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="cd28b-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="cd28b-118">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="cd28b-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="cd28b-119">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd28b-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd28b-120">型として変数を識別するために、アンパサンド (&) 文字を使用することができますも`Long`します。</span><span class="sxs-lookup"><span data-stu-id="cd28b-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="cd28b-121">詳細については、次を参照してください。[型文字](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)します。</span><span class="sxs-lookup"><span data-stu-id="cd28b-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd28b-122">例</span><span class="sxs-lookup"><span data-stu-id="cd28b-122">Example</span></span>  
 <span data-ttu-id="cd28b-123">この例では、`&`文字列の連結を強制する演算子。</span><span class="sxs-lookup"><span data-stu-id="cd28b-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="cd28b-124">結果は、2 つの文字列オペランドの連結を表す文字列値です。</span><span class="sxs-lookup"><span data-stu-id="cd28b-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cd28b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd28b-125">See also</span></span>

- [<span data-ttu-id="cd28b-126">& = 演算子</span><span class="sxs-lookup"><span data-stu-id="cd28b-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="cd28b-127">連結演算子</span><span class="sxs-lookup"><span data-stu-id="cd28b-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="cd28b-128">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="cd28b-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="cd28b-129">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="cd28b-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="cd28b-130">Visual Basic の連結演算子</span><span class="sxs-lookup"><span data-stu-id="cd28b-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
