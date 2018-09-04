---
title: AddHandler ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: f731ff150bd901e325726fca5aa682ff1770f979
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502951"
---
# <a name="addhandler-statement"></a><span data-ttu-id="3b22b-102">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b22b-102">AddHandler Statement</span></span>
<span data-ttu-id="3b22b-103">実行時にイベントをイベント ハンドラーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b22b-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b22b-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="3b22b-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="3b22b-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="3b22b-106">event</span><span class="sxs-lookup"><span data-stu-id="3b22b-106">event</span></span>|<span data-ttu-id="3b22b-107">処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="3b22b-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="3b22b-108">イベントを処理するプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="3b22b-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="3b22b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b22b-109">Remarks</span></span>  
 <span data-ttu-id="3b22b-110">`AddHandler`と`RemoveHandler`ステートメントでは、開始およびプログラムの実行中にいつでもイベント処理を停止することができます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="3b22b-111">署名、`eventhandler`プロシージャは、イベントのシグネチャに一致する必要があります`event`します。</span><span class="sxs-lookup"><span data-stu-id="3b22b-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="3b22b-112">`Handles` キーワードと `AddHandler` ステートメントはどちらも特定のプロシージャで特定のイベントを処理するように指定できますが、両者には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="3b22b-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="3b22b-113">`AddHandler` ステートメントは、実行時にプロシージャをイベントに接続します。</span><span class="sxs-lookup"><span data-stu-id="3b22b-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="3b22b-114">`Handles` キーワードは、プロシージャの定義時に特定のイベントを処理するよう指定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="3b22b-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="3b22b-115">詳細については、次を参照してください。[処理](../../../visual-basic/language-reference/statements/handles-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="3b22b-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b22b-116">カスタム イベントの場合、`AddHandler`ステートメントで呼び出されるイベントの`AddHandler`アクセサー。</span><span class="sxs-lookup"><span data-stu-id="3b22b-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="3b22b-117">カスタム イベントの詳細については、次を参照してください。 [Event ステートメント](../../../visual-basic/language-reference/statements/event-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="3b22b-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b22b-118">例</span><span class="sxs-lookup"><span data-stu-id="3b22b-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3b22b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b22b-119">See Also</span></span>  
 [<span data-ttu-id="3b22b-120">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b22b-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="3b22b-121">Handles</span><span class="sxs-lookup"><span data-stu-id="3b22b-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="3b22b-122">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b22b-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="3b22b-123">イベント</span><span class="sxs-lookup"><span data-stu-id="3b22b-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
