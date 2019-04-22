---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 75d118ee2bd4918c3a936cb341864ddc5315726b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826614"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="f35bc-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f35bc-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="f35bc-103">1 つまたは複数の宣言されたメンバー変数がイベントを発生させるクラスのインスタンスを参照しているを指定します。</span><span class="sxs-lookup"><span data-stu-id="f35bc-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f35bc-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="f35bc-104">Remarks</span></span>  
 <span data-ttu-id="f35bc-105">使用して変数を定義するとき`WithEvents`、メソッドを使用して、変数のイベントを処理することを宣言によって指定できます、`Handles`キーワード。</span><span class="sxs-lookup"><span data-stu-id="f35bc-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="f35bc-106">使用することができます`WithEvents`クラスまたはモジュール レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="f35bc-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="f35bc-107">これは、意味の宣言コンテキスト、`WithEvents`変数がクラスまたはモジュールにある必要があるあり、ソース ファイル、名前空間、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f35bc-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="f35bc-108">使用することはできません`WithEvents`構造体のメンバーにします。</span><span class="sxs-lookup"><span data-stu-id="f35bc-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="f35bc-109">個々 の変数を宣言することができます: 配列ではありません — で`WithEvents`します。</span><span class="sxs-lookup"><span data-stu-id="f35bc-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f35bc-110">ルール</span><span class="sxs-lookup"><span data-stu-id="f35bc-110">Rules</span></span>  
  
-   <span data-ttu-id="f35bc-111">**要素の型。**</span><span class="sxs-lookup"><span data-stu-id="f35bc-111">**Element Types.**</span></span> <span data-ttu-id="f35bc-112">宣言する必要があります`WithEvents`の変数を受け付けることができるため、オブジェクト変数クラスのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="f35bc-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="f35bc-113">ただし、としてを宣言できません`Object`します。</span><span class="sxs-lookup"><span data-stu-id="f35bc-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="f35bc-114">イベントを発生させる特定のクラスとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f35bc-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="f35bc-115">`WithEvents`修飾子は、このコンテキストで使用できます。[Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="f35bc-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f35bc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f35bc-116">See also</span></span>

- [<span data-ttu-id="f35bc-117">Handles</span><span class="sxs-lookup"><span data-stu-id="f35bc-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="f35bc-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="f35bc-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="f35bc-119">イベント</span><span class="sxs-lookup"><span data-stu-id="f35bc-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
