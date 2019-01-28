---
title: continue ステートメント - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 0b3baf6eb4843ff67a3d76af06ca86ca9ec2db03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690593"
---
# <a name="continue-c-reference"></a><span data-ttu-id="5e796-102">continue (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5e796-102">continue (C# Reference)</span></span>

<span data-ttu-id="5e796-103">`continue` ステートメントは、それを囲んでいる [while](../../../csharp/language-reference/keywords/while.md)、[do](../../../csharp/language-reference/keywords/do.md)、[for](../../../csharp/language-reference/keywords/for.md)、または [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ステートメントの次の反復処理にコントロールを渡します。</span><span class="sxs-lookup"><span data-stu-id="5e796-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="5e796-104">例</span><span class="sxs-lookup"><span data-stu-id="5e796-104">Example</span></span>

<span data-ttu-id="5e796-105">この例では、1 から 10 までカウントするようカウンターが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="5e796-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="5e796-106">`continue` ステートメントと式 `(i < 9)` を組み合わせて使用すると、`for` 本文の `continue` から終わりまでのステートメントがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="5e796-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="5e796-107">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="5e796-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5e796-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e796-108">See also</span></span>

- [<span data-ttu-id="5e796-109">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="5e796-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="5e796-110">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5e796-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5e796-111">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="5e796-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="5e796-112">break ステートメント</span><span class="sxs-lookup"><span data-stu-id="5e796-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
- [<span data-ttu-id="5e796-113">ジャンプ ステートメント</span><span class="sxs-lookup"><span data-stu-id="5e796-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
