---
title: 構造体メンバーとして宣言された配列を初期サイズで宣言することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 5d58b531b670715716e849cd37227bc899195df6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335304"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="2171a-102">構造体メンバーとして宣言された配列を初期サイズで宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="2171a-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="2171a-103">構造体の配列は、初期サイズで宣言されます。</span><span class="sxs-lookup"><span data-stu-id="2171a-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="2171a-104">構造体の要素を初期化することはできませんし、初期化の 1 つの形式は、配列のサイズを宣言します。</span><span class="sxs-lookup"><span data-stu-id="2171a-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="2171a-105">**エラー ID:** BC31043</span><span class="sxs-lookup"><span data-stu-id="2171a-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2171a-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="2171a-106">To correct this error</span></span>  
  
1. <span data-ttu-id="2171a-107">動的 (初期サイズはありません)、構造体の配列を定義します。</span><span class="sxs-lookup"><span data-stu-id="2171a-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="2171a-108">動的配列のディメンションを変更できる配列の特定のサイズを必要とする場合、 [ReDim ステートメント](../../../visual-basic/language-reference/statements/redim-statement.md)コードが実行されています。</span><span class="sxs-lookup"><span data-stu-id="2171a-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="2171a-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2171a-109">The following example illustrates this.</span></span>  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2171a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="2171a-110">See also</span></span>

- [<span data-ttu-id="2171a-111">配列</span><span class="sxs-lookup"><span data-stu-id="2171a-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="2171a-112">方法: 構造体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="2171a-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
