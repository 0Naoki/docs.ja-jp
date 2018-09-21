---
title: インターフェイス (F#)
description: F# インターフェイスが関連するその他のクラスが実装するメンバーのセットを指定する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 6d7f8ee9ea17d2294933f88577c30a96975ae5d4
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2018
ms.locfileid: "46481518"
---
# <a name="interfaces"></a><span data-ttu-id="a06b4-103">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a06b4-103">Interfaces</span></span>

<span data-ttu-id="a06b4-104">*インターフェイス*他のクラスを実装する関連するメンバーのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="a06b4-105">構文</span><span class="sxs-lookup"><span data-stu-id="a06b4-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="a06b4-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="a06b4-106">Remarks</span></span>

<span data-ttu-id="a06b4-107">インターフェイスの宣言ではメンバーが実装されていないがクラス宣言に似ています。</span><span class="sxs-lookup"><span data-stu-id="a06b4-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="a06b4-108">代わりに、すべてのメンバーが抽象クラスで、キーワードで示されている`abstract`します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="a06b4-109">抽象メソッドでは、メソッド本体は提供されません。</span><span class="sxs-lookup"><span data-stu-id="a06b4-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="a06b4-110">ただしもと共にメソッドとして、メンバーの個々 の定義を含めることで、既定の実装を提供できます、`default`キーワード。</span><span class="sxs-lookup"><span data-stu-id="a06b4-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="a06b4-111">これは、他の .NET 言語の基本クラスでの仮想メソッドの作成と同じです。</span><span class="sxs-lookup"><span data-stu-id="a06b4-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="a06b4-112">このような仮想メソッドは、インターフェイスを実装するクラスでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="a06b4-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="a06b4-113">インターフェイスの既定のアクセシビリティが`public`します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="a06b4-114">各メソッドのパラメーターに通常の f# 構文を使用して名前を付けることができます必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="a06b4-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="a06b4-115">上記の`ISprintable`例では、`Print`メソッドには、型の 1 つのパラメーター`string`名前`format`します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="a06b4-116">インターフェイスを実装する 2 つの方法: オブジェクトの式を使用して、クラスの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="a06b4-117">どちらの場合は、クラス型またはオブジェクトの式は、インターフェイスの抽象メソッドのメソッド本体を提供します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="a06b4-118">実装では、各インターフェイスを実装する型に固有です。</span><span class="sxs-lookup"><span data-stu-id="a06b4-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="a06b4-119">そのため、さまざまな種類のインターフェイス メソッドは、互いに異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a06b4-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="a06b4-120">キーワード`interface`と`end`、軽量構文を使用すると、開始と、定義の最後をマークするは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a06b4-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="a06b4-121">これらのキーワードを使用しない場合、コンパイラは、使用する構成要素を分析することでは、クラスまたはインターフェイスに、型かどうかを推測しようとします。</span><span class="sxs-lookup"><span data-stu-id="a06b4-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="a06b4-122">メンバーを定義または他のクラスの構文を使用する場合は、型がクラスとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="a06b4-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="a06b4-123">.NET のコーディング スタイルは、大文字のすべてのインターフェイスを開始する`I`します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="a06b4-124">クラス型を使用してインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="a06b4-125">使用して、クラス型の 1 つまたは複数のインターフェイスを実装することができます、`interface`キーワードをインターフェイスの名前と`with`キーワード、インターフェイス メンバーの定義後に次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="a06b4-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="a06b4-126">インターフェイスの実装が継承されるので、派生クラスは、それらを再実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a06b4-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="a06b4-127">インターフェイス メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="a06b4-127">Calling Interface Methods</span></span>

<span data-ttu-id="a06b4-128">インターフェイス メソッドは、インターフェイスを実装する型のオブジェクトではなく、インターフェイスを介してのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a06b4-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="a06b4-129">したがってを使用して、インターフェイス型にキャストする必要があります、`:>`演算子または`upcast`これらのメソッドを呼び出すために演算子。</span><span class="sxs-lookup"><span data-stu-id="a06b4-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="a06b4-130">型のオブジェクトがある場合は、インターフェイス メソッドを呼び出す`SomeClass`、次のコードに示すようにアップ キャスト オブジェクトをインターフェイス型で、必要があります。</span><span class="sxs-lookup"><span data-stu-id="a06b4-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="a06b4-131">代替では、そのキャスト、オブジェクトのメソッドを宣言することですし、次の例のように、インターフェイス メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="a06b4-132">オブジェクト式を使用してインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="a06b4-133">オブジェクトの式は、インターフェイスを実装する簡単な手段です。</span><span class="sxs-lookup"><span data-stu-id="a06b4-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="a06b4-134">これらは、名前付きの型を作成する必要はありませんし、追加メソッドを指定せず、インターフェイス メソッドをサポートするオブジェクト、たいときに便利です。</span><span class="sxs-lookup"><span data-stu-id="a06b4-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="a06b4-135">オブジェクト式は、次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="a06b4-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="a06b4-136">インターフェイスの継承</span><span class="sxs-lookup"><span data-stu-id="a06b4-136">Interface Inheritance</span></span>

<span data-ttu-id="a06b4-137">インターフェイスは、1 つまたは複数の基底インターフェイスから継承できます。</span><span class="sxs-lookup"><span data-stu-id="a06b4-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="a06b4-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="a06b4-138">See also</span></span>

- [<span data-ttu-id="a06b4-139">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="a06b4-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a06b4-140">オブジェクト式</span><span class="sxs-lookup"><span data-stu-id="a06b4-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="a06b4-141">クラス</span><span class="sxs-lookup"><span data-stu-id="a06b4-141">Classes</span></span>](classes.md)
