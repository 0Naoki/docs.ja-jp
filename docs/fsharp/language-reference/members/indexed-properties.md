---
title: インデックス付きプロパティ (F#)
description: インデックス付きプロパティについて説明しますF#、順序付けられたデータを配列に似たアクセスを許可します。
ms.date: 10/17/2018
ms.openlocfilehash: 3dac60eba3d9e7a9c3e76ad7ee051e6b30b88636
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452249"
---
# <a name="indexed-properties"></a><span data-ttu-id="4a1c9-103">インデックス付きプロパティ</span><span class="sxs-lookup"><span data-stu-id="4a1c9-103">Indexed Properties</span></span>

<span data-ttu-id="4a1c9-104">順序付けられたデータを抽象化するクラスを定義するときに基になる実装を公開することがなく、そのデータにインデックス付きのアクセスを提供する便利なあることができます。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="4a1c9-105">これは、`Index`メンバー。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-105">This is done with the `Index` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a1c9-106">構文</span><span class="sxs-lookup"><span data-stu-id="4a1c9-106">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.Index
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property with get only
member self-identifier.Index
    with get(index-values) =
        get-member-body

// Indexed property that has set only.
member self-identifier.Index
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="4a1c9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a1c9-107">Remarks</span></span>

<span data-ttu-id="4a1c9-108">前の構文のフォームは、両方があるインデックス付きプロパティを定義する方法を示して、`get`と`set`メソッドが、`get`メソッドのみかが、`set`メソッドのみ。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="4a1c9-109">取得のみと set のみに対して表示される構文に示す構文を組み合わせてまたを get と set の両方を持つプロパティを生成します。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="4a1c9-110">この後者の形式を使用すると、get に異なるアクセシビリティ修飾子と属性を配置し、メソッドを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="4a1c9-111">名前を使用して`Item`コンパイラは、既定のインデックス付きプロパティとしてプロパティを扱います。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="4a1c9-112">A*既定のインデックス付きプロパティ*オブジェクト インスタンスの配列に似た構文を使用してアクセスできるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="4a1c9-113">たとえば場合、`o`構文は、このプロパティを定義する型のオブジェクトである`o.[index]`プロパティにアクセスするために使用します。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="4a1c9-114">既定以外のインデックス付きプロパティにアクセスするための構文は、プロパティと、通常のメンバーと同様、かっこ内のインデックスの名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="4a1c9-115">たとえば場合のプロパティ`o`が呼び出されます`Ordinal`、記述する`o.Ordinal(index)`へのアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="4a1c9-116">使用する形式に関係なく、インデックス付きプロパティの set メソッドのカリー化されたフォームを常に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="4a1c9-117">カリー化関数については、次を参照してください。[関数](../functions/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="4a1c9-118">例</span><span class="sxs-lookup"><span data-stu-id="4a1c9-118">Example</span></span>

<span data-ttu-id="4a1c9-119">次のコード例では、定義と使用の既定と既定以外のインデックス付きプロパティ get し、set メソッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="4a1c9-120">出力</span><span class="sxs-lookup"><span data-stu-id="4a1c9-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="4a1c9-121">複数のインデックス変数でインデックス付きプロパティ</span><span class="sxs-lookup"><span data-stu-id="4a1c9-121">Indexed Properties with Multiple Index Variables</span></span>

<span data-ttu-id="4a1c9-122">インデックス付きプロパティには、1 つ以上のインデックス変数をことができます。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-122">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="4a1c9-123">その場合は、変数は、プロパティを使用すると、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-123">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="4a1c9-124">このようなプロパティの set メソッドには、キーを含むタプル 1 つ目は、2 番目の値が設定されているは 2 つのカリー化された引数が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="4a1c9-125">次のコードでは、複数のインデックス変数でインデックス付きプロパティの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="4a1c9-125">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a><span data-ttu-id="4a1c9-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a1c9-126">See also</span></span>

- [<span data-ttu-id="4a1c9-127">メンバー</span><span class="sxs-lookup"><span data-stu-id="4a1c9-127">Members</span></span>](index.md)
