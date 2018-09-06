---
title: レコード (F#)
description: F# のレコードがオプションでメンバーの名前付きの値の単純な集計を表す方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 6103d96b6b80a9e2ed168755958dbe800f7fa862
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43882364"
---
# <a name="records"></a><span data-ttu-id="2640e-103">レコード</span><span class="sxs-lookup"><span data-stu-id="2640e-103">Records</span></span>

<span data-ttu-id="2640e-104">レコードは、名前付きの値の単純な集合を表しており、オプションでメンバーを含みます。</span><span class="sxs-lookup"><span data-stu-id="2640e-104">Records represent simple aggregates of named values, optionally with members.</span></span>  <span data-ttu-id="2640e-105">F# 4.1 以降では、することは構造体または参照型。</span><span class="sxs-lookup"><span data-stu-id="2640e-105">Starting with F# 4.1, they can either be structs or reference types.</span></span>  <span data-ttu-id="2640e-106">これが、既定では参照型です。</span><span class="sxs-lookup"><span data-stu-id="2640e-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="2640e-107">構文</span><span class="sxs-lookup"><span data-stu-id="2640e-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="2640e-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2640e-108">Remarks</span></span>

<span data-ttu-id="2640e-109">前の構文で*typename*レコードの種類の名前を指定*label1*と*label2*と呼ばれる値の名前は*ラベル*、*type1*と*type2*これらの値の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="2640e-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="2640e-110">*メンバー リスト*省略可能な型のメンバーの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2640e-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="2640e-111">使用することができます、`[<Struct>]`参照型であるレコードではなく、構造体のレコードを作成する属性。</span><span class="sxs-lookup"><span data-stu-id="2640e-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="2640e-112">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2640e-112">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="2640e-113">各ラベルは、個別の行には、セミコロンを省略できます。</span><span class="sxs-lookup"><span data-stu-id="2640e-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="2640e-114">値を設定するには式と呼ばれるで*式を記録*します。</span><span class="sxs-lookup"><span data-stu-id="2640e-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="2640e-115">コンパイラでは、(ラベルが十分に区別されるその他のレコードの種類の場合) を使用するラベルから型を推測します。</span><span class="sxs-lookup"><span data-stu-id="2640e-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="2640e-116">中かっこ ({}) は、レコードの式を囲みます。</span><span class="sxs-lookup"><span data-stu-id="2640e-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="2640e-117">次のコードはラベルが付いた 3 つの浮動要素を持つレコードを初期化するレコード式`x`、`y`と`z`します。</span><span class="sxs-lookup"><span data-stu-id="2640e-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="2640e-118">同じラベルも別の型がある場合は、短縮形を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2640e-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="2640e-119">最後に宣言された型のラベルの以前に宣言された型よりも優先で、前の例では、`mypoint3D`推論されます`Point3D`します。</span><span class="sxs-lookup"><span data-stu-id="2640e-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="2640e-120">次のコードのように、レコードの種類を明示的に指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2640e-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="2640e-121">クラス型と同様、レコードの種類のメソッドを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="2640e-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="2640e-122">レコード式を使用してレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="2640e-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="2640e-123">レコードはレコードで定義されているラベルを使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="2640e-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="2640e-124">これを行う式として参照されます、*記録式*します。</span><span class="sxs-lookup"><span data-stu-id="2640e-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="2640e-125">レコード式を囲むし、区切り記号としてセミコロンを使用するには、中かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="2640e-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="2640e-126">次の例では、レコードを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2640e-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="2640e-127">レコード式には、型定義では、最後のフィールドの後のセミコロンは、1 つの行ですべてのフィールドがあるかどうかに関係なく、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2640e-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="2640e-128">レコードを作成するときに各フィールドの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2640e-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="2640e-129">任意のフィールドの初期化式では、他のフィールドの値を参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="2640e-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="2640e-130">次のコードの種類で`myRecord2`フィールドの名前から推測されます。</span><span class="sxs-lookup"><span data-stu-id="2640e-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="2640e-131">必要に応じて、型名を明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="2640e-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="2640e-132">レコード構築の別の形式は、既存のレコードをコピーし、フィールドの値の一部を変更したりするときに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="2640e-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="2640e-133">次のコード行を示します。</span><span class="sxs-lookup"><span data-stu-id="2640e-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="2640e-134">レコード式のこのフォームと呼ばれる、*コピーして更新するレコード式*。</span><span class="sxs-lookup"><span data-stu-id="2640e-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="2640e-135">レコードは既定では変更できません。ただし、コピーと更新の式を使用して簡単に変更されたレコードを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="2640e-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="2640e-136">変更可能なフィールドを明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="2640e-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="2640e-137">レコードのフィールドでは、DefaultValue 属性を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2640e-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="2640e-138">既定値に初期化されるフィールドを持つレコードの既定のインスタンスの定義、およびコピーを使用して、既定値と異なる任意のフィールドを設定する式をレコードを更新にことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2640e-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="pattern-matching-with-records"></a><span data-ttu-id="2640e-139">レコードを使用したパターン マッチ</span><span class="sxs-lookup"><span data-stu-id="2640e-139">Pattern Matching with Records</span></span>

<span data-ttu-id="2640e-140">レコードは、パターン マッチングで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2640e-140">Records can be used with pattern matching.</span></span> <span data-ttu-id="2640e-141">一部のフィールドを明示的に指定し、一致が発生したときに割り当てられる他のフィールドの変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2640e-141">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="2640e-142">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="2640e-142">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="2640e-143">このコードの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2640e-143">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="2640e-144">レコードとクラス間の違い</span><span class="sxs-lookup"><span data-stu-id="2640e-144">Differences Between Records and Classes</span></span>

<span data-ttu-id="2640e-145">レコード フィールドは、プロパティとして自動的に公開されているし、それらが作成時に使用され、レコードのコピーで、クラスとは異なります。</span><span class="sxs-lookup"><span data-stu-id="2640e-145">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="2640e-146">レコードの作成は、クラスの構築からも異なります。</span><span class="sxs-lookup"><span data-stu-id="2640e-146">Record construction also differs from class construction.</span></span> <span data-ttu-id="2640e-147">レコードの種類では、コンス トラクターを定義できません。</span><span class="sxs-lookup"><span data-stu-id="2640e-147">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="2640e-148">代わりに、このトピックで説明した構築の構文が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2640e-148">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="2640e-149">クラスは、コンス トラクターのパラメーター、フィールド、およびプロパティ間の直接の関係のあるありません。</span><span class="sxs-lookup"><span data-stu-id="2640e-149">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="2640e-150">共用体と構造体の型と同様には、レコードは、構造的等値セマンティクスを持ちます。</span><span class="sxs-lookup"><span data-stu-id="2640e-150">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="2640e-151">クラスの参照がある等値セマンティクスです。</span><span class="sxs-lookup"><span data-stu-id="2640e-151">Classes have reference equality semantics.</span></span> <span data-ttu-id="2640e-152">次のコード例はこの処理方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2640e-152">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="2640e-153">このコードの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2640e-153">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="2640e-154">クラスと同じコードを記述する場合、2 つのクラスのオブジェクトが等しくならない 2 つの値は、ヒープ上の 2 つのオブジェクトを表しますであり、アドレスだけが比較 (クラス型のオーバーライドしない限り、`System.Object.Equals`メソッド)。</span><span class="sxs-lookup"><span data-stu-id="2640e-154">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="2640e-155">レコードの等価性を参照する必要がある場合、属性を追加`[<ReferenceEquality>]`レコード上。</span><span class="sxs-lookup"><span data-stu-id="2640e-155">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="2640e-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="2640e-156">See also</span></span>

- [<span data-ttu-id="2640e-157">F# の型</span><span class="sxs-lookup"><span data-stu-id="2640e-157">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="2640e-158">クラス</span><span class="sxs-lookup"><span data-stu-id="2640e-158">Classes</span></span>](classes.md)
- [<span data-ttu-id="2640e-159">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="2640e-159">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2640e-160">参照の等価性</span><span class="sxs-lookup"><span data-stu-id="2640e-160">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="2640e-161">パターン一致</span><span class="sxs-lookup"><span data-stu-id="2640e-161">Pattern Matching</span></span>](pattern-matching.md)
