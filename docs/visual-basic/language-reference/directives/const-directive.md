---
title: '#Const ディレクティブ (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 5458bbebc6064eb6273b8deb5447b8941e1d233f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842266"
---
# <a name="const-directive"></a><span data-ttu-id="19128-102">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="19128-102">#Const Directive</span></span>
<span data-ttu-id="19128-103">Visual Basic の条件付きコンパイラ定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="19128-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19128-104">構文</span><span class="sxs-lookup"><span data-stu-id="19128-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="19128-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="19128-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="19128-106">必須。</span><span class="sxs-lookup"><span data-stu-id="19128-106">Required.</span></span> <span data-ttu-id="19128-107">定義されている定数の名前。</span><span class="sxs-lookup"><span data-stu-id="19128-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="19128-108">必須。</span><span class="sxs-lookup"><span data-stu-id="19128-108">Required.</span></span> <span data-ttu-id="19128-109">リテラルやその他の条件付きコンパイラ定数、またはすべての算術演算子または論理演算子を除く任意の組み合わせ`Is`します。</span><span class="sxs-lookup"><span data-stu-id="19128-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19128-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="19128-110">Remarks</span></span>  
 <span data-ttu-id="19128-111">条件付きコンパイラ定数は、表示されるファイルにプライベートでは常にです。</span><span class="sxs-lookup"><span data-stu-id="19128-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="19128-112">使用してパブリック コンパイラ定数を作成することはできません、`#Const`ディレクティブです。 または、ユーザー インターフェイスでのみ作成できます、`/define`コンパイラ オプション。</span><span class="sxs-lookup"><span data-stu-id="19128-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="19128-113">使用できるは、条件付きコンパイラ定数とリテラルのみ`expression`します。</span><span class="sxs-lookup"><span data-stu-id="19128-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="19128-114">定義されている標準の定数を使用して`Const`エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="19128-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="19128-115">逆で定義されている定数を使用することができます、`#Const`条件付きコンパイルのみのキーワード。</span><span class="sxs-lookup"><span data-stu-id="19128-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="19128-116">定数できますもが定義されていないの値がある場合`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="19128-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19128-117">例</span><span class="sxs-lookup"><span data-stu-id="19128-117">Example</span></span>  
 <span data-ttu-id="19128-118">`#Const` ディレクティブの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="19128-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="19128-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="19128-119">See also</span></span>

- [<span data-ttu-id="19128-120">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19128-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
- [<span data-ttu-id="19128-121">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="19128-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="19128-122">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="19128-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="19128-123">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="19128-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="19128-124">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="19128-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
