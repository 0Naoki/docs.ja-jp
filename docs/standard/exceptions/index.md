---
title: .NET での例外の処理とスロー
ms.date: 06/19/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET], exceptions
- exceptions [.NET], throwing
- exceptions [.NET]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 263e6394a57ec3e7ef00eb79671d9b8ac47e724f
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845594"
---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="bd028-102">.NET での例外の処理とスロー</span><span class="sxs-lookup"><span data-stu-id="bd028-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="bd028-103">アプリケーションは、実行中に発生するエラーを一貫した方法で処理できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="bd028-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="bd028-104">.NET では、一貫した方法でアプリケーションにエラーを通知するためのモデルが用意されています。 .NET 操作では、例外をスローすることによって障害の発生を示します。</span><span class="sxs-lookup"><span data-stu-id="bd028-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="bd028-105">例外</span><span class="sxs-lookup"><span data-stu-id="bd028-105">Exceptions</span></span>

<span data-ttu-id="bd028-106">例外とは、プログラムを実行することによって発生するエラー状態または予期しない動作のことです。</span><span class="sxs-lookup"><span data-stu-id="bd028-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="bd028-107">例外がスローされる原因として、コードまたは呼び出したコード (たとえば共有ライブラリ) 内に障害がある、オペレーティング システム リソースを使用できない、予期しない状態 (たとえば検証できないコード) をランタイムが検出したなどがあります。</span><span class="sxs-lookup"><span data-stu-id="bd028-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that can't be verified), and so on.</span></span> <span data-ttu-id="bd028-108">アプリケーションは、他の状態からではなく、これらの状態のうちのいくつかから回復できます。</span><span class="sxs-lookup"><span data-stu-id="bd028-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="bd028-109">ほとんどのアプリケーション例外から回復できますが、ほとんどのランタイム例外からは回復できません。</span><span class="sxs-lookup"><span data-stu-id="bd028-109">Although you can recover from most application exceptions, you can't recover from most runtime exceptions.</span></span>

<span data-ttu-id="bd028-110">.NET では、例外は、<xref:System.Exception?displayProperty=nameWithType> クラスから継承されるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="bd028-110">In .NET, an exception is an object that inherits from the <xref:System.Exception?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="bd028-111">例外は問題が発生したコード領域からスローされます。</span><span class="sxs-lookup"><span data-stu-id="bd028-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="bd028-112">例外は、アプリケーションが処理するかプログラムが終了するまで、スタックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="bd028-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="bd028-113">例外:従来のエラー処理メソッド</span><span class="sxs-lookup"><span data-stu-id="bd028-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="bd028-114">言語のエラー処理モデルは従来、エラーを検出してそれに対応したハンドラーを見つける言語固有の方法か、オペレーティング システムが備えているエラー処理機構のいずれかを使用していました。</span><span class="sxs-lookup"><span data-stu-id="bd028-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="bd028-115">.NET が例外処理を実装する方法は、次の利点をもたらします。</span><span class="sxs-lookup"><span data-stu-id="bd028-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="bd028-116">例外のスローと処理は、.NET プログラミング言語では同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="bd028-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="bd028-117">例外を処理するための特定の言語構文を必要とせず、各言語が独自の構文を定義できます。</span><span class="sxs-lookup"><span data-stu-id="bd028-117">Doesn't require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="bd028-118">例外は、プロセス間、さらにはコンピューターの境界を越えてスローできます。</span><span class="sxs-lookup"><span data-stu-id="bd028-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="bd028-119">プログラムの信頼性を高めるための例外処理コードをアプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="bd028-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="bd028-120">例外には、リターン コードなどの他のエラー通知メソッドに優る利点があります。</span><span class="sxs-lookup"><span data-stu-id="bd028-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="bd028-121">例外がスローされ、それを処理しないと、ランタイムによってアプリケーションが終了されるため、エラーが見過ごされることはありません。</span><span class="sxs-lookup"><span data-stu-id="bd028-121">Failures don't go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="bd028-122">無効な値は、エラーのリターン コードの確認に失敗したコードの結果として、システムを経由した伝達を続行しません。</span><span class="sxs-lookup"><span data-stu-id="bd028-122">Invalid values don't continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span>

## <a name="common-exceptions"></a><span data-ttu-id="bd028-123">一般的な例外</span><span class="sxs-lookup"><span data-stu-id="bd028-123">Common exceptions</span></span>

<span data-ttu-id="bd028-124">次の表は、一般的な例外とそれらの原因の例をいくつか示しています。</span><span class="sxs-lookup"><span data-stu-id="bd028-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="bd028-125">例外の種類</span><span class="sxs-lookup"><span data-stu-id="bd028-125">Exception type</span></span> | <span data-ttu-id="bd028-126">説明</span><span class="sxs-lookup"><span data-stu-id="bd028-126">Description</span></span> | <span data-ttu-id="bd028-127">例</span><span class="sxs-lookup"><span data-stu-id="bd028-127">Example</span></span> |
| -------------- | ----------- | ------- |
| <xref:System.Exception> | <span data-ttu-id="bd028-128">すべての例外の基底クラスです。</span><span class="sxs-lookup"><span data-stu-id="bd028-128">Base class for all exceptions.</span></span> | <span data-ttu-id="bd028-129">なし (この例外の派生クラスを使用)。</span><span class="sxs-lookup"><span data-stu-id="bd028-129">None (use a derived class of this exception).</span></span> |
| <xref:System.IndexOutOfRangeException> | <span data-ttu-id="bd028-130">配列のインデックスが誤っている場合にのみ、ランタイムによってスローされます。</span><span class="sxs-lookup"><span data-stu-id="bd028-130">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="bd028-131">次のように、配列に対して配列の有効範囲外のインデックスを付けた場合。</span><span class="sxs-lookup"><span data-stu-id="bd028-131">Indexing an array outside its valid range:</span></span> <br /> `arr[arr.Length+1]` |
| <xref:System.NullReferenceException> | <span data-ttu-id="bd028-132">null オブジェクトが参照された場合にのみ、ランタイムによってスローされます。</span><span class="sxs-lookup"><span data-stu-id="bd028-132">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null;` <br /> `o.ToString();` |
| <xref:System.InvalidOperationException> | <span data-ttu-id="bd028-133">無効な状態の場合にメソッドによってスローされます。</span><span class="sxs-lookup"><span data-stu-id="bd028-133">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="bd028-134">基になるコレクションから項目を削除した後での、`Enumerator.MoveNext()` の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="bd028-134">Calling `Enumerator.MoveNext()` after removing an item from the underlying collection.</span></span> |
| <xref:System.ArgumentException> | <span data-ttu-id="bd028-135">すべての引数の例外の基底クラスです。</span><span class="sxs-lookup"><span data-stu-id="bd028-135">Base class for all argument exceptions.</span></span> | <span data-ttu-id="bd028-136">なし (この例外の派生クラスを使用)。</span><span class="sxs-lookup"><span data-stu-id="bd028-136">None (use a derived class of this exception).</span></span> |
| <xref:System.ArgumentNullException> | <span data-ttu-id="bd028-137">null の引数を許可しないメソッドによってスローされます。</span><span class="sxs-lookup"><span data-stu-id="bd028-137">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null;` <br /> `"Calculate".IndexOf(s);`|
| <xref:System.ArgumentOutOfRangeException> | <span data-ttu-id="bd028-138">引数が特定の範囲内にあることを検査するメソッドによってスローされます。</span><span class="sxs-lookup"><span data-stu-id="bd028-138">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string";` <br /> `s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="bd028-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd028-139">See also</span></span>

- [<span data-ttu-id="bd028-140">Exception クラスとプロパティ</span><span class="sxs-lookup"><span data-stu-id="bd028-140">Exception Class and Properties</span></span>](exception-class-and-properties.md)  
- [<span data-ttu-id="bd028-141">方法: Try ブロックと Catch ブロックを使用して例外をキャッチする</span><span class="sxs-lookup"><span data-stu-id="bd028-141">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)  
- [<span data-ttu-id="bd028-142">方法: catch ブロックで特定の例外を使用する</span><span class="sxs-lookup"><span data-stu-id="bd028-142">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)  
- [<span data-ttu-id="bd028-143">方法: 例外を明示的にスローする</span><span class="sxs-lookup"><span data-stu-id="bd028-143">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)  
- [<span data-ttu-id="bd028-144">方法: ユーザー定義の例外を作成する</span><span class="sxs-lookup"><span data-stu-id="bd028-144">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)  
- [<span data-ttu-id="bd028-145">ユーザー フィルター例外ハンドラーの使用</span><span class="sxs-lookup"><span data-stu-id="bd028-145">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)  
- [<span data-ttu-id="bd028-146">方法: finally ブロックを使用する</span><span class="sxs-lookup"><span data-stu-id="bd028-146">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)  
- [<span data-ttu-id="bd028-147">COM 相互運用の例外の処理</span><span class="sxs-lookup"><span data-stu-id="bd028-147">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)  
- [<span data-ttu-id="bd028-148">例外の推奨事項</span><span class="sxs-lookup"><span data-stu-id="bd028-148">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)  
- <span data-ttu-id="bd028-149">[ランタイム時の例外についてすべての開発者が知っておくべきこと](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md)</span><span class="sxs-lookup"><span data-stu-id="bd028-149">[What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span></span>
