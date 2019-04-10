---
title: この配列は固定か、または一時的にロックされています。(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: c74d9524ff64101ba6002e133b93c9b80e8f50a9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337969"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="6b440-102">この配列は固定か、または一時的にロックされています。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b440-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="6b440-103">このエラーは、次の考えられる原因があります。</span><span class="sxs-lookup"><span data-stu-id="6b440-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="6b440-104">使用して`ReDim`固定サイズの配列の要素の数を変更します。</span><span class="sxs-lookup"><span data-stu-id="6b440-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="6b440-105">1 つの要素に渡された引数としてプロシージャをモジュール レベル動的配列の次元。</span><span class="sxs-lookup"><span data-stu-id="6b440-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="6b440-106">防ぐために、配列がロックされている要素が渡された場合、プロシージャ内での参照パラメーターのメモリの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="6b440-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="6b440-107">値を代入しようとして、`Variant`配列を含む変数が、`Variant`現在ロックされています。</span><span class="sxs-lookup"><span data-stu-id="6b440-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6b440-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="6b440-108">To correct this error</span></span>  
  
1. <span data-ttu-id="6b440-109">元の配列を作成してで宣言することで修正するのではなく動的`ReDim`(配列が宣言されているプロシージャ内で)、または (この場合、配列は、モジュール レベルで宣言されます要素の数を指定せずに宣言。</span><span class="sxs-lookup"><span data-stu-id="6b440-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="6b440-110">実際に、モジュール内のすべてのプロシージャ内で参照可能であるため、要素を渡す必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6b440-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="6b440-111">何がロックを判断、`Variant`およびそれを解決します。</span><span class="sxs-lookup"><span data-stu-id="6b440-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b440-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b440-112">See also</span></span>

- [<span data-ttu-id="6b440-113">配列</span><span class="sxs-lookup"><span data-stu-id="6b440-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
