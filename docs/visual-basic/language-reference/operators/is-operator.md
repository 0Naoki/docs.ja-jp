---
title: Is 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: a78189a6b82100665ac07b9d7c89590613ec1e1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745624"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="41351-102">Is 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41351-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="41351-103">2 つのオブジェクト参照変数を比較します。</span><span class="sxs-lookup"><span data-stu-id="41351-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41351-104">構文</span><span class="sxs-lookup"><span data-stu-id="41351-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="41351-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="41351-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="41351-106">必須。</span><span class="sxs-lookup"><span data-stu-id="41351-106">Required.</span></span> <span data-ttu-id="41351-107">すべて`Boolean`値。</span><span class="sxs-lookup"><span data-stu-id="41351-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="41351-108">必須。</span><span class="sxs-lookup"><span data-stu-id="41351-108">Required.</span></span> <span data-ttu-id="41351-109">すべて`Object`名。</span><span class="sxs-lookup"><span data-stu-id="41351-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="41351-110">必須。</span><span class="sxs-lookup"><span data-stu-id="41351-110">Required.</span></span> <span data-ttu-id="41351-111">すべて`Object`名。</span><span class="sxs-lookup"><span data-stu-id="41351-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41351-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="41351-112">Remarks</span></span>  
 <span data-ttu-id="41351-113">`Is`演算子が 2 つのオブジェクト参照が同じオブジェクトを参照してかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="41351-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="41351-114">ただし、値の比較は実行されません。</span><span class="sxs-lookup"><span data-stu-id="41351-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="41351-115">場合`object1`と`object2`両方には、まったく同じオブジェクト インスタンスを参照してください`result`は`True`; が存在しない場合、`result`は`False`します。</span><span class="sxs-lookup"><span data-stu-id="41351-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="41351-116">`Is` 使用することができますも、`TypeOf`キーワードを`TypeOf`.`Is`オブジェクト変数のデータ型と互換性があるかどうかをテストする式。</span><span class="sxs-lookup"><span data-stu-id="41351-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41351-117">`Is`でキーワードを使用しても、[を選択しています.Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="41351-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41351-118">例</span><span class="sxs-lookup"><span data-stu-id="41351-118">Example</span></span>  
 <span data-ttu-id="41351-119">次の例では、`Is`オブジェクト参照のペアを比較する演算子。</span><span class="sxs-lookup"><span data-stu-id="41351-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="41351-120">割り当てられている結果を`Boolean`2 つのオブジェクトが同一であるかどうかを表す値。</span><span class="sxs-lookup"><span data-stu-id="41351-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 <span data-ttu-id="41351-121">使用することができます、前の例に示すよう、`Is`両方をテストする演算子が事前バインディングし、遅延バインドされたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="41351-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41351-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="41351-122">See also</span></span>
- [<span data-ttu-id="41351-123">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="41351-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="41351-124">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="41351-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="41351-125">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="41351-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="41351-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="41351-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="41351-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="41351-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="41351-128">演算子および式</span><span class="sxs-lookup"><span data-stu-id="41351-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
