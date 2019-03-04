---
title: 構造体の使用 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
ms.openlocfilehash: fe7cf3cf1982060d22f648c5e17d002b1a695ac0
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978528"
---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="831f1-102">構造体の使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="831f1-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="831f1-103">`struct` 型は、 `Point`、 `Rectangle`、 `Color`などの軽量のオブジェクトを表すのに適しています。</span><span class="sxs-lookup"><span data-stu-id="831f1-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="831f1-104">点を表すには [自動実装プロパティ](../../../csharp/language-reference/keywords/class.md) がある [クラス](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)を使用するのと同じくらい便利ですが、シナリオによっては [構造体](../../../csharp/language-reference/keywords/struct.md) を使用する方がより効率的です。</span><span class="sxs-lookup"><span data-stu-id="831f1-104">Although it is just as convenient to represent a point as a [class](../../../csharp/language-reference/keywords/class.md) with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), a [struct](../../../csharp/language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="831f1-105">たとえば、1,000 個の `Point` オブジェクトから成る配列を宣言する場合は、各オブジェクトの参照用に追加のメモリを割り当てます。この場合、構造体であれば処理上の負荷を抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="831f1-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="831f1-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] には <xref:System.Drawing.Point>という名前のオブジェクトが含まれているため、この例の構造体には代わりに "Coords" という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="831f1-106">Because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contains an object called <xref:System.Drawing.Point>, the struct in this example is named "Coords" instead.</span></span>  
  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 <span data-ttu-id="831f1-107">構造体に既定の (パラメーターなしの) コンストラクターを定義するとエラーになります。</span><span class="sxs-lookup"><span data-stu-id="831f1-107">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="831f1-108">また、構造体の本体のインスタンス フィールドを初期化した場合もエラーになります。</span><span class="sxs-lookup"><span data-stu-id="831f1-108">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="831f1-109">外部アクセス可能な構造体メンバーを初期化するには、パラメーター化されたコンストラクター、暗黙的な既定のコンストラクター、[オブジェクト初期化子](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)を使用するか、構造体を宣言した後で個別にメンバーにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="831f1-109">You can initialize externally accessible struct members only by using a parameterized constructor, the implicit, default constructor, an [object initializer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md), or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="831f1-110">プライベートかそれ以外の理由でアクセスできないメンバーの場合、コンストラクターを独占的に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="831f1-110">Any private or otherwise inaccessible members require the use of constructors exclusively.</span></span>
  
 <span data-ttu-id="831f1-111">[new](../../../csharp/language-reference/keywords/new.md) 演算子を使用して struct オブジェクトを作成すると、[コンストラクター シグネチャ](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax)に基づき、オブジェクトが作成されて適切なコンストラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="831f1-111">When you create a struct object using the [new](../../../csharp/language-reference/keywords/new.md) operator, it gets created and the appropriate constructor is called according to the [constructor's signature](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax).</span></span> <span data-ttu-id="831f1-112">クラスとは異なり、構造体は `new` 演算子を使用せずにインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="831f1-112">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="831f1-113">このような場合、コンストラクターの呼び出しが行われないため、割り当てがより効率的になります。</span><span class="sxs-lookup"><span data-stu-id="831f1-113">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="831f1-114">ただし、各フィールドは未割り当てのままになり、すべてのフィールドが初期化されるまではオブジェクトを使用できません。</span><span class="sxs-lookup"><span data-stu-id="831f1-114">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span> <span data-ttu-id="831f1-115">たとえば、自動的に実装されたプロパティから値を取得したり、設定したりできません。</span><span class="sxs-lookup"><span data-stu-id="831f1-115">This includes the inability to get or set values through auto-implemented properties.</span></span>
 
 <span data-ttu-id="831f1-116">既定の、パラメーターのないコンストラクターを利用して構造体オブジェクトを初期化する場合、その[既定値](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md)に基づいてすべてのメンバーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="831f1-116">If you instantiate a struct object using the default, parameterless constructor, all members are assigned according to their [default values](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>
  
 <span data-ttu-id="831f1-117">構造体のパラメーターを使用してコンストラクターを記述するとき、すべてのメンバーを明示的に初期化する必要があります。それをしない場合、1 つまたは複数のメンバーが未割り当てのままとなり、構造体を使用できず、コンパイラ エラー CS0171 が出ます。</span><span class="sxs-lookup"><span data-stu-id="831f1-117">When writing a constructor with parameters for a struct, you must explicitly initialize all members; otherwise one or more members remain unassigned and the struct cannot be used, producing compiler error CS0171.</span></span>  
  
 <span data-ttu-id="831f1-118">クラスには継承がありますが、構造体には継承がありません。</span><span class="sxs-lookup"><span data-stu-id="831f1-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="831f1-119">構造体は、他の構造体やクラスから継承できず、基本クラスになることはできません。</span><span class="sxs-lookup"><span data-stu-id="831f1-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="831f1-120">ただし、構造体は、基本クラス <xref:System.Object>から継承します。</span><span class="sxs-lookup"><span data-stu-id="831f1-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="831f1-121">構造体は、クラスの場合とまったく同じ方法でインターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="831f1-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="831f1-122">`struct`キーワードを使用してクラスを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="831f1-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="831f1-123">C# では、クラスと構造体は、意味が異なります。</span><span class="sxs-lookup"><span data-stu-id="831f1-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="831f1-124">構造体は値型ですが、クラスは参照型です。</span><span class="sxs-lookup"><span data-stu-id="831f1-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="831f1-125">詳細については、「 [Value Types (値型)](../../../csharp/language-reference/keywords/value-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="831f1-125">For more information, see [Value Types](../../../csharp/language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="831f1-126">参照型の機能が必要な場合以外は、小さいクラスを構造体として宣言した方が、システムによってより効率的に処理される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="831f1-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="831f1-127">例 1</span><span class="sxs-lookup"><span data-stu-id="831f1-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="831f1-128">説明</span><span class="sxs-lookup"><span data-stu-id="831f1-128">Description</span></span>  
 <span data-ttu-id="831f1-129">既定のコンストラクターとパラメーター化されたコンストラクターの両方を使用した `struct` の初期化の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="831f1-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="831f1-130">コード</span><span class="sxs-lookup"><span data-stu-id="831f1-130">Code</span></span>  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 [!code-csharp[csProgGuideObjects#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="831f1-131">例 2</span><span class="sxs-lookup"><span data-stu-id="831f1-131">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="831f1-132">説明</span><span class="sxs-lookup"><span data-stu-id="831f1-132">Description</span></span>  
 <span data-ttu-id="831f1-133">構造体に固有の機能を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="831f1-133">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="831f1-134">この例では、`new` 演算子を使用せずに Coords オブジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="831f1-134">It creates a Coords object without using the `new` operator.</span></span> <span data-ttu-id="831f1-135">`struct` を `class`という単語に置き換えた場合、プログラムはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="831f1-135">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="831f1-136">コード</span><span class="sxs-lookup"><span data-stu-id="831f1-136">Code</span></span>  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 [!code-csharp[csProgGuideObjects#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="831f1-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="831f1-137">See also</span></span>

- [<span data-ttu-id="831f1-138">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="831f1-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="831f1-139">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="831f1-139">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="831f1-140">構造体</span><span class="sxs-lookup"><span data-stu-id="831f1-140">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)
