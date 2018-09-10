---
title: 名前空間 (C# プログラミング ガイド)
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: c4011092a6c605137053b544d4b9f14cce2fdb4c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211997"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="d5fc4-102">名前空間 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d5fc4-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="d5fc4-103">C# プログラミングでは、名前空間が 2 つの方法でよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="d5fc4-104">最初の方法では、次のように .NET Framework で名前空間を使用して、その多くのクラスを整理します。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
<span data-ttu-id="d5fc4-105">`System` は名前空間で、`Console` はその名前空間内のクラスです。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="d5fc4-106">以下の例のように、`using` キーワードを使用できるため、完全な名前は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
<span data-ttu-id="d5fc4-107">詳細については、「[using ディレクティブ](../../language-reference/keywords/using-directive.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="d5fc4-108">2 つ目の方法では、独自の名前空間を宣言します。これは、より大きなプログラミング プロジェクトでクラス名とメソッド名のスコープを制御するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="d5fc4-109">名前空間を宣言するには、以下の例のように、[namespace](../../language-reference/keywords/namespace.md) キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

<span data-ttu-id="d5fc4-110">名前空間の名前を、有効な C# の[識別子名](../inside-a-program/identifier-names.md)にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="d5fc4-111">名前空間の概要</span><span class="sxs-lookup"><span data-stu-id="d5fc4-111">Namespaces Overview</span></span>  

<span data-ttu-id="d5fc4-112">名前空間には次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="d5fc4-113">大きなコード プロジェクトを整理します。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-113">They organize large code projects.</span></span>  
- <span data-ttu-id="d5fc4-114">`.` 演算子を使用して、区切られます。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="d5fc4-115">`using directive` を使用すると、クラスごとに名前空間の名前を指定する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-115">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="d5fc4-116">`global` 名前空間は "ルート" 名前空間です。`global::System` は常に .NET Framework 名前空間の `System` を参照します。</span><span class="sxs-lookup"><span data-stu-id="d5fc4-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="d5fc4-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d5fc4-117">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5fc4-118">参照</span><span class="sxs-lookup"><span data-stu-id="d5fc4-118">See Also</span></span>

- [<span data-ttu-id="d5fc4-119">名前空間の使用</span><span class="sxs-lookup"><span data-stu-id="d5fc4-119">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="d5fc4-120">方法: グローバル名前空間エイリアスを使用する</span><span class="sxs-lookup"><span data-stu-id="d5fc4-120">How to: Use the Global Namespace Alias</span></span>](how-to-use-the-global-namespace-alias.md)
- [<span data-ttu-id="d5fc4-121">方法: My 名前空間を使用する</span><span class="sxs-lookup"><span data-stu-id="d5fc4-121">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="d5fc4-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d5fc4-122">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="d5fc4-123">識別子名</span><span class="sxs-lookup"><span data-stu-id="d5fc4-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="d5fc4-124">名前空間キーワード</span><span class="sxs-lookup"><span data-stu-id="d5fc4-124">Namespace Keywords</span></span>](../../language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="d5fc4-125">using ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="d5fc4-125">using Directive</span></span>](../../language-reference/keywords/using-directive.md)  
- [<span data-ttu-id="d5fc4-126">:: 演算子</span><span class="sxs-lookup"><span data-stu-id="d5fc4-126">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="d5fc4-127">。演算子</span><span class="sxs-lookup"><span data-stu-id="d5fc4-127">. Operator</span></span>](../../language-reference/operators/member-access-operator.md)
>>>>>>> <span data-ttu-id="d5fc4-128">識別子の名前指定の規則の追加</span><span class="sxs-lookup"><span data-stu-id="d5fc4-128">add identifier naming rules</span></span>
