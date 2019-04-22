---
title: デリゲート - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: fa69a03d160e7079f532e8e00245a7af3f3a8999
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088744"
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="1ebb6-102">デリゲート (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="1ebb6-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="1ebb6-103">[デリゲート](../../../csharp/language-reference/keywords/delegate.md)は、特定のパラメーター リストおよび戻り値の型を使用して、メソッドへの参照を表す型です。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="1ebb6-104">デリゲートをインスタンス化するときは、互換性のあるシグネチャと戻り値の型を持つ任意のメソッドにそのインスタンスを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="1ebb6-105">メソッドは、デリゲート インスタンスを使用して起動する (呼び出す) ことができます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="1ebb6-106">デリゲートは、他のメソッドへの引数としてメソッドを渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="1ebb6-107">イベント ハンドラーは、デリゲートを介して呼び出されるメソッドにすぎません。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="1ebb6-108">カスタム メソッドを作成して、特定のイベントの発生時に、作成したメソッドが Windows コントロールなどのクラスから呼び出されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="1ebb6-109">次の例にデリゲート宣言を示します。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-109">The following example shows a delegate declaration:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#20)]  
  
 <span data-ttu-id="1ebb6-110">デリゲート型と一致するアクセス可能なクラスまたは構造体のメソッドはすべて、デリゲートに代入できます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-110">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="1ebb6-111">メソッドは、静的メソッドとインスタンス メソッドのいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-111">The method can be either static or an instance method.</span></span> <span data-ttu-id="1ebb6-112">このため、メソッド呼び出しをプログラムによって変更でき、また新しいコードを既存のクラスに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-112">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ebb6-113">メソッドのオーバーロードのコンテキストでは、メソッドのシグネチャに戻り値は含まれません。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-113">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="1ebb6-114">しかしデリゲートのコンテキストでは、シグネチャに戻り値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-114">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="1ebb6-115">つまり、メソッドにはデリゲートと同じ戻り値の型が必要です。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-115">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="1ebb6-116">このようにメソッドをパラメーターとして参照できるため、デリゲートはコールバック メソッドを定義するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-116">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="1ebb6-117">たとえば、2 つのオブジェクトを比較するメソッドへの参照は、並べ替えのアルゴリズムへの引数として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-117">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="1ebb6-118">比較を行うコードは独立したプロシージャであるため、並べ替えのアルゴリズムはより一般的な方法で記述できます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-118">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="1ebb6-119">デリゲートの概要</span><span class="sxs-lookup"><span data-stu-id="1ebb6-119">Delegates Overview</span></span>  
 <span data-ttu-id="1ebb6-120">デリゲートには、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-120">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="1ebb6-121">デリゲートは C++ 関数ポインターと似ていますが、デリゲートは完全なオブジェクト指向です。また、メンバー関数への C++ ポインターとは異なり、デリゲートではオブジェクト インスタンスとメソッドの両方をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-121">Delegates are similar to C++ function pointers, but delegates are fully object-oriented, and unlike C++ pointers to member functions, delegates encapsulate both an object instance and a method.</span></span>
  
-   <span data-ttu-id="1ebb6-122">デリゲートを使用すると、メソッドをパラメーターとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-122">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="1ebb6-123">デリゲートは、コールバック メソッドを定義するのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-123">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="1ebb6-124">デリゲートは連結でき、たとえば、複数のメソッドを 1 つのイベントで呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-124">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="1ebb6-125">メソッドは、デリゲート型に正確に一致する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-125">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="1ebb6-126">詳細については、「[デリゲートの分散の使用](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-126">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="1ebb6-127">C# Version 2.0 で、[匿名メソッド](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)の概念が導入され、別個に定義されたメソッドの代わりにコード ブロックをパラメーターとして渡せるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-127">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="1ebb6-128">C# 3.0 ではラムダ式が導入され、インライン コード ブロックをより簡潔に記述できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-128">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="1ebb6-129">匿名メソッドと (特定のコンテキストにおける) ラムダ式はどちらも、デリゲート型にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-129">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="1ebb6-130">これらの機能は総称して、匿名関数と呼ばれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-130">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="1ebb6-131">ラムダ式について詳しくは、「[匿名関数](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-131">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ebb6-132">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1ebb6-132">In This Section</span></span>  
  
-   [<span data-ttu-id="1ebb6-133">デリゲートの使用</span><span class="sxs-lookup"><span data-stu-id="1ebb6-133">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   <span data-ttu-id="1ebb6-134">[インターフェイス (c# プログラミング ガイド) ではなくデリゲートを使用する場合](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1ebb6-134">[When to Use Delegates Instead of Interfaces (C# Programming Guide)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span></span>  
  
-   [<span data-ttu-id="1ebb6-135">名前付きメソッドを使用したデリゲートと匿名メソッドを使用したデリゲート</span><span class="sxs-lookup"><span data-stu-id="1ebb6-135">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="1ebb6-136">匿名メソッド</span><span class="sxs-lookup"><span data-stu-id="1ebb6-136">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="1ebb6-137">デリゲートの分散の使用</span><span class="sxs-lookup"><span data-stu-id="1ebb6-137">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="1ebb6-138">方法: デリゲートを結合する (マルチキャスト デリゲート)</span><span class="sxs-lookup"><span data-stu-id="1ebb6-138">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="1ebb6-139">方法: デリゲートを宣言し、インスタンス化して使用する</span><span class="sxs-lookup"><span data-stu-id="1ebb6-139">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  

## <a name="c-language-specification"></a><span data-ttu-id="1ebb6-140">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="1ebb6-140">C# Language Specification</span></span>  

<span data-ttu-id="1ebb6-141">詳細については、「[C# 言語の仕様](../../language-reference/language-specification/index.md)」の「[デリゲート](~/_csharplang/spec/delegates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-141">For more information, see [Delegates](~/_csharplang/spec/delegates.md) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="1ebb6-142">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="1ebb6-142">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="1ebb6-143">参考書籍の該当する章</span><span class="sxs-lookup"><span data-stu-id="1ebb6-143">Featured Book Chapters</span></span>  
 <span data-ttu-id="1ebb6-144">「[Delegates, Events, and Lambda Expressions (デリゲート、イベント、およびラムダ式)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29)」(『[C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers (C# 3.0 クックブック (第 3 版): C# 3.0 プログラマ向けの 250 以上のソリューション)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)』)</span><span class="sxs-lookup"><span data-stu-id="1ebb6-144">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="1ebb6-145">「[デリゲートとイベント](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29)」(『[Learning C# 3.0: Master the fundamentals of C# 3.0 (C# 3.0 の学習: C# 3.0 の基礎を習得)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)』)</span><span class="sxs-lookup"><span data-stu-id="1ebb6-145">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ebb6-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ebb6-146">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="1ebb6-147">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1ebb6-147">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1ebb6-148">イベント</span><span class="sxs-lookup"><span data-stu-id="1ebb6-148">Events</span></span>](../../../csharp/programming-guide/events/index.md)
