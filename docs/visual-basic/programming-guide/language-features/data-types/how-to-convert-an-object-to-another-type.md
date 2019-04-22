---
title: '方法: オブジェクトを Visual Basic で別の型に変換します。'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 1e515c0f4ce8e787754c61a9b53d247fa93c49f2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814381"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="a535f-102">方法: オブジェクトを Visual Basic で別の型に変換します。</span><span class="sxs-lookup"><span data-stu-id="a535f-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="a535f-103">変換する、`Object`変数などの変換キーワードを使用して、別のデータ型を[CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="a535f-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a535f-104">例</span><span class="sxs-lookup"><span data-stu-id="a535f-104">Example</span></span>  
 <span data-ttu-id="a535f-105">次の例では、変換、`Object`変数を`Integer`と`String`します。</span><span class="sxs-lookup"><span data-stu-id="a535f-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="a535f-106">わかっている場合の内容、`Object`変数は、特定のデータ型が変数にそのデータ型に変換する方がよい。</span><span class="sxs-lookup"><span data-stu-id="a535f-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="a535f-107">引き続き使用する場合、`Object`いずれかが発生する、変数*ボックス化*と*ボックス化解除*(の値型) または*遅延バインディング*(の参照型)。</span><span class="sxs-lookup"><span data-stu-id="a535f-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="a535f-108">これらの操作はすべてにかかる実行時間を追加して、パフォーマンスが低下です。</span><span class="sxs-lookup"><span data-stu-id="a535f-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a535f-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a535f-109">Compiling the Code</span></span>  
 <span data-ttu-id="a535f-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a535f-110">This example requires:</span></span>  
  
-   <span data-ttu-id="a535f-111"><xref:System?displayProperty=nameWithType> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="a535f-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a535f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a535f-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="a535f-113">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="a535f-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="a535f-114">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="a535f-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="a535f-115">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="a535f-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="a535f-116">文字列とその他の型との変換</span><span class="sxs-lookup"><span data-stu-id="a535f-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="a535f-117">配列変換</span><span class="sxs-lookup"><span data-stu-id="a535f-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="a535f-118">構造体</span><span class="sxs-lookup"><span data-stu-id="a535f-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a535f-119">データの種類</span><span class="sxs-lookup"><span data-stu-id="a535f-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a535f-120">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="a535f-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
