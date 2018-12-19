---
title: null キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- "null"
- null_CSharpKeyword
helpviewer_keywords:
- null keyword [C#]
ms.assetid: fecb1c60-6232-4efe-87f7-9a86ba2e9119
ms.openlocfilehash: 9c3aeb3066542080bbd5514fe536d4d125dc8ecc
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243947"
---
# <a name="null-c-reference"></a><span data-ttu-id="217e6-102">null (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="217e6-102">null (C# Reference)</span></span>

<span data-ttu-id="217e6-103">`null` キーワードは、いかなるオブジェクトも参照していない null 参照を表すリテラルです。</span><span class="sxs-lookup"><span data-stu-id="217e6-103">The `null` keyword is a literal that represents a null reference, one that does not refer to any object.</span></span> <span data-ttu-id="217e6-104">`null` は参照型変数の既定値です。</span><span class="sxs-lookup"><span data-stu-id="217e6-104">`null` is the default value of reference-type variables.</span></span> <span data-ttu-id="217e6-105">通常の値の型を null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="217e6-105">Ordinary value types cannot be null.</span></span> <span data-ttu-id="217e6-106">ただし、C# 2.0 では null 許容値型が導入されました。</span><span class="sxs-lookup"><span data-stu-id="217e6-106">However, C# 2.0 introduced nullable value types.</span></span> <span data-ttu-id="217e6-107">「[Null 許容型](../../programming-guide/nullable-types/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="217e6-107">See [Nullable Types](../../programming-guide/nullable-types/index.md).</span></span>

<span data-ttu-id="217e6-108">次の例では、null キーワードの一部の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="217e6-108">The following example demonstrates some behaviors of the null keyword:</span></span>

[!code-csharp[csrefKeywordsLiteral#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsLiteral/CS/csrefKeywordsLiteral.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="217e6-109">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="217e6-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="217e6-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="217e6-110">See also</span></span>

- [<span data-ttu-id="217e6-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="217e6-111">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="217e6-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="217e6-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="217e6-113">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="217e6-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="217e6-114">リテラル キーワード</span><span class="sxs-lookup"><span data-stu-id="217e6-114">Literal Keywords</span></span>](literal-keywords.md)
- [<span data-ttu-id="217e6-115">既定値の一覧表</span><span class="sxs-lookup"><span data-stu-id="217e6-115">Default Values Table</span></span>](default-values-table.md)
- [<span data-ttu-id="217e6-116">Nothing</span><span class="sxs-lookup"><span data-stu-id="217e6-116">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)