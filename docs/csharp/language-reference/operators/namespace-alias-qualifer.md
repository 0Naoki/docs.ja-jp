---
title: ':: 演算子 (C# リファレンス)'
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 480ed224d1994dac926dfc78d59e227c8d1e8f36
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934996"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d5118-102">:: 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d5118-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="d5118-103">名前空間エイリアス修飾子 (`::`) を使用して識別子を検索できます。</span><span class="sxs-lookup"><span data-stu-id="d5118-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="d5118-104">この例に示すように、常に 2 つの識別子の間に配置します。</span><span class="sxs-lookup"><span data-stu-id="d5118-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="d5118-105">コメント</span><span class="sxs-lookup"><span data-stu-id="d5118-105">Remarks</span></span>  
 <span data-ttu-id="d5118-106">名前空間エイリアス修飾子として `global` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d5118-106">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="d5118-107">これにより、エイリアスを使用した名前空間ではなく、グローバル名前空間で検索が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d5118-107">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="d5118-108">参照項目</span><span class="sxs-lookup"><span data-stu-id="d5118-108">For More Information</span></span>  
 <span data-ttu-id="d5118-109">`::` 演算子の使用例については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5118-109">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="d5118-110">方法: グローバル名前空間エイリアスを使用する</span><span class="sxs-lookup"><span data-stu-id="d5118-110">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="d5118-111">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d5118-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5118-112">参照</span><span class="sxs-lookup"><span data-stu-id="d5118-112">See Also</span></span>

- [<span data-ttu-id="d5118-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d5118-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d5118-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d5118-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d5118-115">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="d5118-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="d5118-116">名前空間キーワード</span><span class="sxs-lookup"><span data-stu-id="d5118-116">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="d5118-117">。演算子</span><span class="sxs-lookup"><span data-stu-id="d5118-117">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="d5118-118">extern エイリアス</span><span class="sxs-lookup"><span data-stu-id="d5118-118">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
