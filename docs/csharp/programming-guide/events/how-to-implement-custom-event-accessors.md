---
title: '方法 : カスタム イベント アクセサーを実装する (C# プログラミング ガイド)'
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 759a7a4518a371449723a23669816bbc0fbc0dee
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836710"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="b0875-102">方法 : カスタム イベント アクセサーを実装する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b0875-102">How to: Implement Custom Event Accessors (C# Programming Guide)</span></span>
<span data-ttu-id="b0875-103">イベントは、宣言元のクラス内でしか呼び出せない特殊なマルチキャスト デリゲートです。</span><span class="sxs-lookup"><span data-stu-id="b0875-103">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="b0875-104">クライアント コードは、イベント発生時に呼び出されるメソッドへの参照を提供することにより、イベントにサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="b0875-104">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="b0875-105">これらのメソッドは、イベント アクセサーを使用してデリゲートの呼び出しリストに追加されます。イベント アクセサーはプロパティ アクセサーに似ていますが、イベント アクセサーには `add` および `remove` という名前が付いている点が異なります。</span><span class="sxs-lookup"><span data-stu-id="b0875-105">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="b0875-106">ほとんどの場合、カスタム イベント アクセサーを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b0875-106">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="b0875-107">コードでカスタム イベント アクセサーを指定していない場合は、コンパイラによって自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b0875-107">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="b0875-108">ただし、カスタム動作の指定が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b0875-108">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="b0875-109">「[方法 : インターフェイス イベントを実装する](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)」のトピックでは、そのような場合の一例を示しています。</span><span class="sxs-lookup"><span data-stu-id="b0875-109">One such case is shown in the topic [How to:  Implement Interface Events](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0875-110">例</span><span class="sxs-lookup"><span data-stu-id="b0875-110">Example</span></span>  
 <span data-ttu-id="b0875-111">次の例は、カスタム イベント アクセサーの add と remove を実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b0875-111">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="b0875-112">アクセサー内で任意のコードに置き換えることができますが、新しいイベント ハンドラー メソッドを追加または削除する前に、イベントをロックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b0875-112">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](codesnippet/CSharp/how-to-implement-interface-events_1.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="b0875-113">参照</span><span class="sxs-lookup"><span data-stu-id="b0875-113">See Also</span></span>

- [<span data-ttu-id="b0875-114">イベント</span><span class="sxs-lookup"><span data-stu-id="b0875-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="b0875-115">event</span><span class="sxs-lookup"><span data-stu-id="b0875-115">event</span></span>](../../../csharp/language-reference/keywords/event.md)