---
title: MustOverride (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: fedebf3ee791fbab02ace2ba2dc121590a241c53
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627331"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="368c3-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="368c3-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="368c3-103">プロパティまたはプロシージャは、このクラスで実装されていませんしを使用する派生クラスでオーバーライドされる必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="368c3-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="368c3-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="368c3-104">Remarks</span></span>  
 <span data-ttu-id="368c3-105">`MustOverride` は、プロパティまたはプロシージャの宣言ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="368c3-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="368c3-106">プロパティまたはプロシージャを指定する`MustOverride`クラスのメンバーである必要があり、そのクラスをマークする必要があります[MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)します。</span><span class="sxs-lookup"><span data-stu-id="368c3-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="368c3-107">ルール</span><span class="sxs-lookup"><span data-stu-id="368c3-107">Rules</span></span>  
  
-   <span data-ttu-id="368c3-108">**不完全な宣言です。**</span><span class="sxs-lookup"><span data-stu-id="368c3-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="368c3-109">指定すると`MustOverride`、任意の追加のプロパティまたはプロシージャのコード行をしない指定しないでも、 `End Function`、 `End Property`、または`End Sub`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="368c3-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="368c3-110">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="368c3-110">**Combined Modifiers.**</span></span> <span data-ttu-id="368c3-111">指定することはできません`MustOverride`と共に`NotOverridable`、 `Overridable`、または`Shared`同じ宣言内。</span><span class="sxs-lookup"><span data-stu-id="368c3-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
-   <span data-ttu-id="368c3-112">**シャドウとオーバーライドします。**</span><span class="sxs-lookup"><span data-stu-id="368c3-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="368c3-113">シャドウとオーバーライドは、どちらも継承された要素を再定義しますが、その方法は大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="368c3-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="368c3-114">詳細については、次を参照してください。 [Visual Basic におけるシャドウ](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)します。</span><span class="sxs-lookup"><span data-stu-id="368c3-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
-   <span data-ttu-id="368c3-115">**代替条件です。**</span><span class="sxs-lookup"><span data-stu-id="368c3-115">**Alternate Terms.**</span></span> <span data-ttu-id="368c3-116">オーバーライドで以外は使用できませんを要素とも呼ばれます、*純粋仮想*要素。</span><span class="sxs-lookup"><span data-stu-id="368c3-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="368c3-117">`MustOverride` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="368c3-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="368c3-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="368c3-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="368c3-119">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="368c3-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="368c3-120">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="368c3-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="368c3-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="368c3-121">See also</span></span>
- [<span data-ttu-id="368c3-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="368c3-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="368c3-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="368c3-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="368c3-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="368c3-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="368c3-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="368c3-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="368c3-126">キーワード</span><span class="sxs-lookup"><span data-stu-id="368c3-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="368c3-127">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="368c3-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
