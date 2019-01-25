---
title: Throw ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 9af1436af950346eef572c34b9d42da3e8c8cf24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671162"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="0af80-102">Throw ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0af80-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="0af80-103">プロシージャ内で例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="0af80-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0af80-104">構文</span><span class="sxs-lookup"><span data-stu-id="0af80-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="0af80-105">パーツ</span><span class="sxs-lookup"><span data-stu-id="0af80-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="0af80-106">スローされる例外に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0af80-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="0af80-107">内に存在するときに省略可能な`Catch`ステートメントでは、それ以外の場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="0af80-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0af80-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="0af80-108">Remarks</span></span>  
 <span data-ttu-id="0af80-109">`Throw`ステートメントは、構造化例外処理コードで処理できる例外をスローします (`Try`.`Catch`...`Finally`) または非構造化例外処理コード (`On Error GoTo`)。</span><span class="sxs-lookup"><span data-stu-id="0af80-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="0af80-110">使用することができます、 `Throw` Visual Basic は、適切な例外処理コードが見つかるまで呼び出し履歴を移動するために、コード内のエラーをトラップするステートメント。</span><span class="sxs-lookup"><span data-stu-id="0af80-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="0af80-111">A`Throw`式ステートメントでのみ使用できます、`Catch`ステートメントでは、case ステートメントが現在処理中の例外を再スロー、`Catch`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="0af80-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="0af80-112">`Throw`ステートメントの呼び出し履歴をリセットする、`expression`例外。</span><span class="sxs-lookup"><span data-stu-id="0af80-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="0af80-113">場合`expression`が指定されていない、コール スタックは変更されません。</span><span class="sxs-lookup"><span data-stu-id="0af80-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="0af80-114">例外の呼び出し履歴にアクセスすることができます、<xref:System.Exception.StackTrace%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0af80-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0af80-115">例</span><span class="sxs-lookup"><span data-stu-id="0af80-115">Example</span></span>  
 <span data-ttu-id="0af80-116">次のコードでは、`Throw`例外をスローするステートメント。</span><span class="sxs-lookup"><span data-stu-id="0af80-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="0af80-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="0af80-117">Requirements</span></span>  
 <span data-ttu-id="0af80-118">**名前空間:**[Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="0af80-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="0af80-119">**モジュール:** `Interaction`</span><span class="sxs-lookup"><span data-stu-id="0af80-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="0af80-120">**アセンブリ:** Visual Basic ランタイム ライブラリ (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="0af80-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0af80-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0af80-121">See also</span></span>
- [<span data-ttu-id="0af80-122">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="0af80-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="0af80-123">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="0af80-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
