---
title: 名前空間 (F#)
description: F# 名前空間を使用すると、プログラム要素のグループに名前を追加することによって関連する機能の領域にコードを整理する方法について説明します。
ms.date: 04/24/2017
ms.openlocfilehash: 769a1241f76ac32d3a6a80bd637078493119bb3c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44178257"
---
# <a name="namespaces"></a><span data-ttu-id="ed2f1-103">名前空間</span><span class="sxs-lookup"><span data-stu-id="ed2f1-103">Namespaces</span></span>

<span data-ttu-id="ed2f1-104">名前空間を使用すると、プログラム要素のグループに名前を割り当てて、関連する機能の区分にコードを編成することができます。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of program elements.</span></span>

## <a name="syntax"></a><span data-ttu-id="ed2f1-105">構文</span><span class="sxs-lookup"><span data-stu-id="ed2f1-105">Syntax</span></span>

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="ed2f1-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="ed2f1-106">Remarks</span></span>

<span data-ttu-id="ed2f1-107">名前空間にコードを配置する場合は、ファイル内の最初の宣言は名前空間を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-107">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="ed2f1-108">全体のファイルの内容は、名前空間の一部になります。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-108">The contents of the entire file then become part of the namespace.</span></span>

<span data-ttu-id="ed2f1-109">値および関数、名前空間を含める直接ことはできません。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-109">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="ed2f1-110">代わりに、モジュールでは、値および関数を含める必要があるし、モジュールの名前空間に含まれます。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-110">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="ed2f1-111">名前空間は、モジュールの種類を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-111">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="ed2f1-112">名前空間は明示的に宣言する名前空間キーワード、または暗黙的にモジュールを宣言するときに。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-112">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="ed2f1-113">名前空間を明示的に宣言するには、名前空間キーワードの後に名前空間の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-113">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="ed2f1-114">次の例では、型とその名前空間に含まれるモジュールのウィジェットの名前空間を宣言するコード ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-114">The following example shows a code file that declares a namespace Widgets with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="ed2f1-115">ファイルの内容全体が 1 つのモジュールである場合は、宣言することも名前空間に暗黙的を使用して、`module`キーワードとモジュールの完全修飾名で新しい名前空間名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-115">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="ed2f1-116">次の例では、名前空間を宣言するコード ファイル`Widgets`とモジュール`WidgetsModule`関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-116">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="ed2f1-117">次のコードは上記のコードと同じですが、モジュールがローカル モジュールの宣言。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-117">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="ed2f1-118">その場合は、名前空間は、独自の行に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-118">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="ed2f1-119">1 つ以上のモジュールが 1 つまたは複数の名前空間で同じファイルで必要に応じて、ローカル モジュール宣言を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-119">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="ed2f1-120">モジュールのローカル宣言を使用する場合は、モジュール宣言で修飾名前空間を使用できません。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-120">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="ed2f1-121">次のコードでは、名前空間の宣言と 2 つのモジュールのローカル宣言を持つファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-121">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="ed2f1-122">この場合、モジュールが、名前空間で直接に含まれるファイルと同じ名前を持つ、暗黙的に作成されたモジュールはありません。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-122">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="ed2f1-123">などのファイルで、コードの他の`do`モジュール メンバーを修飾する必要があるため、内部のモジュールではなく、名前空間には、バインド、`widgetFunction`モジュール名を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-123">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="ed2f1-124">この例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-124">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="ed2f1-125">詳細については、次を参照してください。[モジュール](modules.md)します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-125">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="ed2f1-126">入れ子になった名前空間</span><span class="sxs-lookup"><span data-stu-id="ed2f1-126">Nested Namespaces</span></span>

<span data-ttu-id="ed2f1-127">入れ子になった名前空間を作成するときに、完全修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-127">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="ed2f1-128">それ以外の場合、新しい最上位レベルの名前空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-128">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="ed2f1-129">インデントは、名前空間の宣言では無視されます。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-129">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="ed2f1-130">次の例では、入れ子になった名前空間を宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-130">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="ed2f1-131">ファイルとアセンブリの名前空間</span><span class="sxs-lookup"><span data-stu-id="ed2f1-131">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="ed2f1-132">名前空間は、1 つのプロジェクトやコンパイルで複数のファイルにまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-132">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="ed2f1-133">用語*名前空間のフラグメント*1 つのファイルに含まれている名前空間の一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-133">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="ed2f1-134">名前空間は、複数のアセンブリをまたがることもできます。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-134">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="ed2f1-135">たとえば、`System`名前空間に多数のアセンブリにまたがり、多数の入れ子になった名前空間が含まれていますが、全体の .NET Framework が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-135">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="ed2f1-136">グローバル Namespace</span><span class="sxs-lookup"><span data-stu-id="ed2f1-136">Global Namespace</span></span>

<span data-ttu-id="ed2f1-137">定義済みの名前空間を使用する`global`に最上位レベルの .NET 名前空間に名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-137">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="ed2f1-138">使用することできますもグローバル他の名前空間と名前が競合を解決するのには、たとえば最上位レベルの .NET 名前空間を参照します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-138">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="ed2f1-139">再帰的な名前空間</span><span class="sxs-lookup"><span data-stu-id="ed2f1-139">Recursive namespaces</span></span>

<span data-ttu-id="ed2f1-140">F# 4.1 には、再帰的に相互に含まれているすべてのコードでは、名前空間の概念が導入されています。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-140">F# 4.1 introduces the notion of namespaces which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="ed2f1-141">使用してこれには`namespace rec`します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-141">This is done via `namespace rec`.</span></span>  <span data-ttu-id="ed2f1-142">使用`namespace rec`されない型とモジュール間の相互参照コードを記述することでいくつかの問題を軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-142">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="ed2f1-143">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-143">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

<span data-ttu-id="ed2f1-144">なお、例外`DontSqueezeTheBananaException`とクラス`Banana`両方には、互いを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-144">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="ed2f1-145">モジュールではさらに、`BananaHelpers`とクラス`Banana`も互いに参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-145">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="ed2f1-146">これは、削除した場合、f# で表現できませんが、`rec`からキーワード、`MutualReferences`名前空間。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-146">This would not be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="ed2f1-147">この機能は使用できる最上位[モジュール](modules.md)f# 4.1 またはそれ以降。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-147">This feature is also available for top-level [Modules](modules.md) in F# 4.1 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed2f1-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed2f1-148">See also</span></span>

- [<span data-ttu-id="ed2f1-149">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="ed2f1-149">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ed2f1-150">モジュール</span><span class="sxs-lookup"><span data-stu-id="ed2f1-150">Modules</span></span>](modules.md)
- [<span data-ttu-id="ed2f1-151">F# RFC FS-1009 - ファイル内でより大きな範囲経由で相互に参照型とモジュールを許可します。</span><span class="sxs-lookup"><span data-stu-id="ed2f1-151">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
