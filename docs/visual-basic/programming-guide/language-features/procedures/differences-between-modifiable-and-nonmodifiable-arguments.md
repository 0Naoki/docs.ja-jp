---
title: 変更できる引数と変更できない引数の違い (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: a880ae8c13eebd5d9d325468098e058f58d3fa71
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665950"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="eaece-102">変更できる引数と変更できない引数の違い (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eaece-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="eaece-103">プロシージャを呼び出すときに通常を 1 つまたは複数の引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="eaece-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="eaece-104">各引数は、基になるプログラミング要素に対応します。</span><span class="sxs-lookup"><span data-stu-id="eaece-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="eaece-105">基になる要素と引数自体の両方には、変更可能なか、変更不可能なをすることができます。</span><span class="sxs-lookup"><span data-stu-id="eaece-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="eaece-106">変更可能なと変更できない要素</span><span class="sxs-lookup"><span data-stu-id="eaece-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="eaece-107">プログラミング要素には、いずれかを指定できる、*変更可能な要素*、変更されると、その値である、または*変更不可能な要素*が作成されたら、固定値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="eaece-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="eaece-108">次の表では、変更可能なと変更できないプログラミング要素を示します。</span><span class="sxs-lookup"><span data-stu-id="eaece-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="eaece-109">変更可能な要素</span><span class="sxs-lookup"><span data-stu-id="eaece-109">Modifiable elements</span></span>|<span data-ttu-id="eaece-110">変更できない要素</span><span class="sxs-lookup"><span data-stu-id="eaece-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="eaece-111">(プロシージャ内で宣言された)、ローカル変数は読み取り専用以外のオブジェクト変数を含む</span><span class="sxs-lookup"><span data-stu-id="eaece-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="eaece-112">読み取り専用の変数、フィールド、およびプロパティ</span><span class="sxs-lookup"><span data-stu-id="eaece-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="eaece-113">読み取り専用以外のフィールド (モジュール、クラス、および構造体のメンバー変数)</span><span class="sxs-lookup"><span data-stu-id="eaece-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="eaece-114">定数とリテラル</span><span class="sxs-lookup"><span data-stu-id="eaece-114">Constants and literals</span></span>|  
|<span data-ttu-id="eaece-115">読み取り専用以外のプロパティ</span><span class="sxs-lookup"><span data-stu-id="eaece-115">Properties, except for read-only</span></span>|<span data-ttu-id="eaece-116">列挙型メンバー</span><span class="sxs-lookup"><span data-stu-id="eaece-116">Enumeration members</span></span>|  
|<span data-ttu-id="eaece-117">配列の要素</span><span class="sxs-lookup"><span data-stu-id="eaece-117">Array elements</span></span>|<span data-ttu-id="eaece-118">式 (その要素は変更可能な場合でも)</span><span class="sxs-lookup"><span data-stu-id="eaece-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="eaece-119">変更可能なと変更できない引数</span><span class="sxs-lookup"><span data-stu-id="eaece-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="eaece-120">A*変更可能な引数*は変更可能な基になる要素を持つ 1 つです。</span><span class="sxs-lookup"><span data-stu-id="eaece-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="eaece-121">呼び出し元のコードは、いつでも新しい値を格納することができます、引数を渡す場合と[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)プロシージャ内のコードでは、呼び出し元のコード内の基になる要素は変更もできます。</span><span class="sxs-lookup"><span data-stu-id="eaece-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="eaece-122">A*変更できない引数*変更不可能な基になる要素があるか、渡される[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)します。</span><span class="sxs-lookup"><span data-stu-id="eaece-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="eaece-123">プロシージャは、変更可能な要素である場合でも、呼び出し元のコードでは、基になる要素を変更できません。</span><span class="sxs-lookup"><span data-stu-id="eaece-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="eaece-124">変更不可能な要素である場合、呼び出し元コード自体によって変更できません。</span><span class="sxs-lookup"><span data-stu-id="eaece-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="eaece-125">変更では、呼び出し元のコード内の基になる要素には影響しませんが、呼び出されたプロシージャ、変更できない引数のローカル コピーが変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eaece-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaece-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaece-126">See also</span></span>

- [<span data-ttu-id="eaece-127">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="eaece-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="eaece-128">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="eaece-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="eaece-129">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="eaece-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="eaece-130">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="eaece-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="eaece-131">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="eaece-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="eaece-132">方法: プロシージャ引数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="eaece-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="eaece-133">方法: プロシージャ引数の値が変化しません。</span><span class="sxs-lookup"><span data-stu-id="eaece-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="eaece-134">方法: 引数の値渡しを強制します。</span><span class="sxs-lookup"><span data-stu-id="eaece-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="eaece-135">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="eaece-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="eaece-136">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="eaece-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
