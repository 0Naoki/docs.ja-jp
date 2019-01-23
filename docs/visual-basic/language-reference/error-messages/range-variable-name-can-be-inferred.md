---
title: 範囲変数の名前は、引数なしの簡易名または修飾名からのみ推論できます
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: 8b95bb3c53210cc11966466d32924c13aee8234b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581945"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="dfaf8-102">範囲変数の名前は、引数なしの簡易名または修飾名からのみ推論できます</span><span class="sxs-lookup"><span data-stu-id="dfaf8-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="dfaf8-103">LINQ クエリでは、1 つまたは複数の引数を受け取るプログラミング要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dfaf8-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="dfaf8-104">コンパイラは、そのプログラミング要素の範囲変数を推論できません。</span><span class="sxs-lookup"><span data-stu-id="dfaf8-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="dfaf8-105">**エラー ID:** BC36599</span><span class="sxs-lookup"><span data-stu-id="dfaf8-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dfaf8-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="dfaf8-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="dfaf8-107">次のコードに示すように、プログラミングの要素に明示的な変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfaf8-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfaf8-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfaf8-108">See also</span></span>
- [<span data-ttu-id="dfaf8-109">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="dfaf8-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="dfaf8-110">Select 句</span><span class="sxs-lookup"><span data-stu-id="dfaf8-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
