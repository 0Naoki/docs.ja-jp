---
title: Call ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 259fcc6f1c59df09e768a08204df81aa8105de53
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936790"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="85d4c-102">Call ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85d4c-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="85d4c-103">転送コントロールを`Function`、 `Sub`、またはダイナミック リンク ライブラリ (DLL) プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="85d4c-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d4c-104">構文</span><span class="sxs-lookup"><span data-stu-id="85d4c-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="85d4c-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="85d4c-105">Parts</span></span>  
|||
|---|---|
|`procedureName`|<span data-ttu-id="85d4c-106">必須。</span><span class="sxs-lookup"><span data-stu-id="85d4c-106">Required.</span></span> <span data-ttu-id="85d4c-107">呼び出すプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="85d4c-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="85d4c-108">任意。</span><span class="sxs-lookup"><span data-stu-id="85d4c-108">Optional.</span></span> <span data-ttu-id="85d4c-109">変数または呼び出された場合、プロシージャに渡される引数を表す式の一覧です。</span><span class="sxs-lookup"><span data-stu-id="85d4c-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="85d4c-110">複数の引数は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="85d4c-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="85d4c-111">含める場合`argumentList`かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="85d4c-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="85d4c-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="85d4c-112">Remarks</span></span>  
 <span data-ttu-id="85d4c-113">使用することができます、`Call`プロシージャを呼び出すときに、キーワード。</span><span class="sxs-lookup"><span data-stu-id="85d4c-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="85d4c-114">ほとんどのプロシージャ呼び出しについては、このキーワードを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="85d4c-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="85d4c-115">通常、使用、`Call`キーワード、識別子で呼び出された式が開始しない場合。</span><span class="sxs-lookup"><span data-stu-id="85d4c-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="85d4c-116">使用、`Call`キーワードの他の使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="85d4c-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="85d4c-117">プロシージャは、値を返す場合、`Call`ステートメントでは、それを破棄します。</span><span class="sxs-lookup"><span data-stu-id="85d4c-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85d4c-118">例</span><span class="sxs-lookup"><span data-stu-id="85d4c-118">Example</span></span>  
 <span data-ttu-id="85d4c-119">次のコードは 2 つの例で、`Call`キーワードは、プロシージャを呼び出すために必要な。</span><span class="sxs-lookup"><span data-stu-id="85d4c-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="85d4c-120">どちらの例では、呼び出された式が識別子で開始しません。</span><span class="sxs-lookup"><span data-stu-id="85d4c-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="85d4c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="85d4c-121">See Also</span></span>  
 [<span data-ttu-id="85d4c-122">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="85d4c-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="85d4c-123">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="85d4c-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="85d4c-124">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="85d4c-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="85d4c-125">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="85d4c-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
