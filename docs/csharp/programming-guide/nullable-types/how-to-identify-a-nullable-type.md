---
title: '方法: Null 許容型を識別する (C# プログラミング ガイド)'
description: 型が Null 許容型か、インスタンスが Null 許容型であるかどうかを判断する方法について学習します。
ms.date: 09/24/2018
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: f9957568d3c68f60cc9286718be9f5a496f876e6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2018
ms.locfileid: "47400544"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="2514e-103">方法: Null 許容型を識別する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="2514e-103">How to: Identify a nullable type (C# Programming Guide)</span></span>

<span data-ttu-id="2514e-104">次の例は、<xref:System.Type?displayProperty=nameWithType> インスタンスがクローズ ジェネリック null 許容型 (つまり、指定された型パラメーター `T` を使用する <xref:System.Nullable%601?displayProperty=nameWithType> 型) を表すかどうかを判断する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2514e-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a closed generic nullable type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="2514e-105">例で示されているとおり、<xref:System.Type?displayProperty=nameWithType> オブジェクトの作成には、[typeof](../../language-reference/keywords/typeof.md) 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="2514e-105">As the example shows, you use the [typeof](../../language-reference/keywords/typeof.md) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
<span data-ttu-id="2514e-106">インスタンスが Null 許容型かどうかを判断したい場合は、<xref:System.Type> インスタンスが前述のコードでテストされるように、<xref:System.Object.GetType%2A?displayProperty=nameWithType> メソッドは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2514e-106">If you want to determine whether an instance is of a nullable type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="2514e-107">Null 許容型のインスタンスで <xref:System.Object.GetType%2A?displayProperty=nameWithType> メソッドを呼び出した場合、そのインスタンスは <xref:System.Object> に[ボクシング](using-nullable-types.md#boxing-and-unboxing)されます。</span><span class="sxs-lookup"><span data-stu-id="2514e-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="2514e-108">Null 許容型の null 以外のインスタンスのボクシングは、基になる型の値のボクシングと等しいので、<xref:System.Object.GetType%2A> は、Null 許容型の基になる型を表す <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2514e-108">As boxing of a non-null instance of a nullable type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="2514e-109">インスタンスが Null 許容型であるかどうかの判断には、[is](../../language-reference/keywords/is.md) 演算子は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2514e-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable type.</span></span> <span data-ttu-id="2514e-110">次の例のとおり、`is` 演算子の使用では、Null 許容型のインスタンスの型とその基になる型は判別できません。</span><span class="sxs-lookup"><span data-stu-id="2514e-110">As the following example shows, you cannot distinguish types of instances of a nullable type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="2514e-111">次の例のコードを使用すると、インスタンスが Null 許容型であるかどうかを判別することができます。</span><span class="sxs-lookup"><span data-stu-id="2514e-111">You can use the code presented in the following example to determine whether an instance is of a nullable type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]
  
## <a name="see-also"></a><span data-ttu-id="2514e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2514e-112">See also</span></span>

- [<span data-ttu-id="2514e-113">Null 許容型</span><span class="sxs-lookup"><span data-stu-id="2514e-113">Nullable types</span></span>](index.md)  
- [<span data-ttu-id="2514e-114">Null 許容型の使用</span><span class="sxs-lookup"><span data-stu-id="2514e-114">Using nullable types</span></span>](using-nullable-types.md)  
- <xref:System.Nullable.GetUnderlyingType%2A>  
