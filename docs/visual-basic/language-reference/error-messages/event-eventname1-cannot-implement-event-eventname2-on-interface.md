---
title: デリゲート型 '<eventname1>' および '<eventname2>' が一致しないため、イベント '<interface>' はインターフェイス '<delegate1>' 上のイベント '<delegate2>' を実装できません。
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 3ec3e7bb2f28bf8c4dd38bc71e11193456860021
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272852"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="0acda-102">イベント '\<eventname1 >' イベントを実装することはできません'\<eventname2 >' インターフェイスで '\<インターフェイス >' ため、デリゲート型の\<delegate1 >' と'\<delegate2 >' と一致しません。</span><span class="sxs-lookup"><span data-stu-id="0acda-102">Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>
<span data-ttu-id="0acda-103">イベントのデリゲート型がインターフェイスでイベントのデリゲート型と一致しないために、Visual Basic では、イベントを実装できません。</span><span class="sxs-lookup"><span data-stu-id="0acda-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="0acda-104">このエラーは、インターフェイス内で複数のイベントを定義して、同じイベントと共にそれらを実装しようとする場合に、発生します。</span><span class="sxs-lookup"><span data-stu-id="0acda-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="0acda-105">実装されたすべてのイベントが `As` 構文を使用して宣言され、同じデリゲート型を指定する場合にのみ、イベントは 2 つ以上のイベントを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="0acda-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="0acda-106">**エラー ID:** BC31423</span><span class="sxs-lookup"><span data-stu-id="0acda-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0acda-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="0acda-107">To correct this error</span></span>  
  
-   <span data-ttu-id="0acda-108">イベントを個別に実装します。</span><span class="sxs-lookup"><span data-stu-id="0acda-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="0acda-109">または</span><span class="sxs-lookup"><span data-stu-id="0acda-109">—or—</span></span>  
  
-   <span data-ttu-id="0acda-110">インターフェイスを使用して、イベントを定義、`As`構文と同じデリゲート型を指定します。</span><span class="sxs-lookup"><span data-stu-id="0acda-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acda-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="0acda-111">See also</span></span>
- [<span data-ttu-id="0acda-112">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="0acda-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="0acda-113">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="0acda-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="0acda-114">イベント</span><span class="sxs-lookup"><span data-stu-id="0acda-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
