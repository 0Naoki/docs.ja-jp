---
title: 例外の種類 (F#)
description: 定義して、f# の例外の種類を使用する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: b8d648a3649153a3604856deb61ce41db8c40bf2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858822"
---
# <a name="exception-types"></a><span data-ttu-id="1b3fb-103">例外の種類</span><span class="sxs-lookup"><span data-stu-id="1b3fb-103">Exception Types</span></span>

<span data-ttu-id="1b3fb-104">F# の例外の 2 つのカテゴリがあります: .NET 例外の種類と f# の例外の種類。</span><span class="sxs-lookup"><span data-stu-id="1b3fb-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="1b3fb-105">このトピックでは、定義して、f# の例外の種類を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b3fb-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b3fb-106">構文</span><span class="sxs-lookup"><span data-stu-id="1b3fb-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="1b3fb-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1b3fb-107">Remarks</span></span>

<span data-ttu-id="1b3fb-108">前の構文で*例外型*新しい f# の例外型の名前を指定および*引数の型*この種類の例外が発生するときに指定できる引数の型を表します。</span><span class="sxs-lookup"><span data-stu-id="1b3fb-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="1b3fb-109">タプル型を使用して複数の引数を指定することができます*引数型*します。</span><span class="sxs-lookup"><span data-stu-id="1b3fb-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="1b3fb-110">F# の例外の一般的な定義では、次の項目に似ています。</span><span class="sxs-lookup"><span data-stu-id="1b3fb-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="1b3fb-111">使用してこの型の例外を生成することができます、`raise`関数は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1b3fb-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="1b3fb-112">F# の例外の種類を使用するには、フィルター内で直接、`try...with`式は、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="1b3fb-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="1b3fb-113">例外の種類で定義された、 `exception` f# でのキーワードはから継承する新しい型`System.Exception`します。</span><span class="sxs-lookup"><span data-stu-id="1b3fb-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b3fb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b3fb-114">See also</span></span>

- [<span data-ttu-id="1b3fb-115">例外処理</span><span class="sxs-lookup"><span data-stu-id="1b3fb-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="1b3fb-116">例外: `raise` 関数</span><span class="sxs-lookup"><span data-stu-id="1b3fb-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="1b3fb-117">例外階層</span><span class="sxs-lookup"><span data-stu-id="1b3fb-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
