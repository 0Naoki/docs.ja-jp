---
title: '例外: try...with 式 (F#)'
description: 例外処理の F# の 'try...with' 式を使用する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 588960c0f8ccedb431c37d0f1314bf1a293b638c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2018
ms.locfileid: "44042167"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="e10cb-103">例外: try...with 式</span><span class="sxs-lookup"><span data-stu-id="e10cb-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="e10cb-104">このトピックで説明します、`try...with`式、F# 言語での例外処理に使用される式。</span><span class="sxs-lookup"><span data-stu-id="e10cb-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="e10cb-105">構文</span><span class="sxs-lookup"><span data-stu-id="e10cb-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="e10cb-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="e10cb-106">Remarks</span></span>

<span data-ttu-id="e10cb-107">`try...with` F# の例外を処理する式を使用します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="e10cb-108">似ています、 `try...catch` (C#) ステートメント。</span><span class="sxs-lookup"><span data-stu-id="e10cb-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="e10cb-109">上記の構文では、コードでは、 *expression1*例外を生成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e10cb-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="e10cb-110">`try...with`式が値を返します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="e10cb-111">全体の式の値を返しますの例外がスローされない場合*expression1*します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="e10cb-112">例外がスローされた場合、各*パターン*がさらに、例外とは、対応する、最初の一致するパターンの比較*式*と呼ばれる、*例外ハンドラー*、その分岐が実行され、全体的な式は、その例外ハンドラーで、式の値を返します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="e10cb-113">パターンが一致しない場合、例外は、一致するハンドラーが見つかるまで呼び出し履歴を伝達します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="e10cb-114">例外ハンドラー内の各式から返される値の型が式から返される型と一致する必要があります、`try`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="e10cb-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="e10cb-115">多くの場合、エラーが発生するという事実は、各例外ハンドラー内の式から返される有効な値がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="e10cb-116">一般的なパターンとしてオプション型である式の型です。</span><span class="sxs-lookup"><span data-stu-id="e10cb-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="e10cb-117">次のコード例は、このパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="e10cb-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="e10cb-118">例外は、.NET 例外か F# の例外になることができます。</span><span class="sxs-lookup"><span data-stu-id="e10cb-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="e10cb-119">F# の例外を使用して定義することができます、`exception`キーワード。</span><span class="sxs-lookup"><span data-stu-id="e10cb-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="e10cb-120">例外の種類とその他の条件でフィルター処理するさまざまなパターンを使用することができます。オプションは、次の表にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="e10cb-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="e10cb-121">パターン</span><span class="sxs-lookup"><span data-stu-id="e10cb-121">Pattern</span></span>|<span data-ttu-id="e10cb-122">説明</span><span class="sxs-lookup"><span data-stu-id="e10cb-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="e10cb-123">:?</span><span class="sxs-lookup"><span data-stu-id="e10cb-123">:?</span></span> <span data-ttu-id="e10cb-124">*例外の種類*</span><span class="sxs-lookup"><span data-stu-id="e10cb-124">*exception-type*</span></span>|<span data-ttu-id="e10cb-125">指定した種類の .NET 例外に一致します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="e10cb-126">:?</span><span class="sxs-lookup"><span data-stu-id="e10cb-126">:?</span></span> <span data-ttu-id="e10cb-127">*例外の種類*として*識別子*</span><span class="sxs-lookup"><span data-stu-id="e10cb-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="e10cb-128">指定された .NET 例外の種類と一致するが、例外の名前付きの値を示します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="e10cb-129">*例外名*(*引数*)</span><span class="sxs-lookup"><span data-stu-id="e10cb-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="e10cb-130">F# の例外の種類と一致して、引数をバインドします。</span><span class="sxs-lookup"><span data-stu-id="e10cb-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="e10cb-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="e10cb-131">*identifier*</span></span>|<span data-ttu-id="e10cb-132">任意の例外に一致し、例外オブジェクトに名前をバインドします。</span><span class="sxs-lookup"><span data-stu-id="e10cb-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="e10cb-133">等価 \**: でしょうか。System.Exception として \* \* \* 識別子*</span><span class="sxs-lookup"><span data-stu-id="e10cb-133">Equivalent to \**:? System.Exception as\*\*\*identifier*</span></span>|
|<span data-ttu-id="e10cb-134">*識別子*とき*条件*</span><span class="sxs-lookup"><span data-stu-id="e10cb-134">*identifier* when *condition*</span></span>|<span data-ttu-id="e10cb-135">条件が true の場合、すべての例外と一致します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="e10cb-136">使用例</span><span class="sxs-lookup"><span data-stu-id="e10cb-136">Examples</span></span>

<span data-ttu-id="e10cb-137">次のコード例では、さまざまな例外ハンドラー パターンの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

>[!NOTE]
<span data-ttu-id="e10cb-138">`try...with`コンス トラクターは、個別の式から、`try...finally`式。</span><span class="sxs-lookup"><span data-stu-id="e10cb-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="e10cb-139">そのため、コードでは、両方が必要な場合、`with`ブロックと`finally`ブロック、2 つの式を入れ子にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e10cb-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE]
<span data-ttu-id="e10cb-140">使用することができます`try...with`非同期ワークフローでおよびその他のコンピュテーション式でのカスタマイズされたバージョンの場合、`try...with`式を使用します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="e10cb-141">詳細については、次を参照してください。[非同期ワークフロー](../asynchronous-workflows.md)、および[コンピュテーション式](../computation-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="e10cb-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e10cb-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="e10cb-142">See also</span></span>

- [<span data-ttu-id="e10cb-143">例外処理</span><span class="sxs-lookup"><span data-stu-id="e10cb-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="e10cb-144">例外の種類</span><span class="sxs-lookup"><span data-stu-id="e10cb-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="e10cb-145">例外: `try...finally` 式</span><span class="sxs-lookup"><span data-stu-id="e10cb-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
