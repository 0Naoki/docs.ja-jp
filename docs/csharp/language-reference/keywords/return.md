---
title: return ステートメント - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 058dc1d51099196559bee4ec2b96dc883e813f93
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236559"
---
# <a name="return-c-reference"></a><span data-ttu-id="d0dac-102">return (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d0dac-102">return (C# Reference)</span></span>

<span data-ttu-id="d0dac-103">`return` ステートメントは、メソッドの実行を終了し、呼び出し側のメソッドに制御を戻します。</span><span class="sxs-lookup"><span data-stu-id="d0dac-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="d0dac-104">省略可能な値を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="d0dac-104">It can also return an optional value.</span></span> <span data-ttu-id="d0dac-105">メソッドが `void` 型の場合、`return` ステートメントは省略できます。</span><span class="sxs-lookup"><span data-stu-id="d0dac-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="d0dac-106">return ステートメントが `try` ブロック内にある場合は、制御が呼び出し側のメソッドに返される前に、`finally` ブロック (存在する場合) が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d0dac-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="d0dac-107">例</span><span class="sxs-lookup"><span data-stu-id="d0dac-107">Example</span></span>

 <span data-ttu-id="d0dac-108">次の例では、メソッド `CalculateArea()` がローカル変数 `area` を [double](double.md) 値として返します。</span><span class="sxs-lookup"><span data-stu-id="d0dac-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](double.md) value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="d0dac-109">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d0dac-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d0dac-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0dac-110">See also</span></span>

- [<span data-ttu-id="d0dac-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d0dac-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d0dac-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d0dac-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d0dac-113">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="d0dac-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d0dac-114">return ステートメント</span><span class="sxs-lookup"><span data-stu-id="d0dac-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
- [<span data-ttu-id="d0dac-115">ジャンプ ステートメント</span><span class="sxs-lookup"><span data-stu-id="d0dac-115">Jump Statements</span></span>](jump-statements.md)
