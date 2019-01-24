---
title: 型パラメーターは修飾子として使用できません。
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 8ee0fd5822c22da090aa0abee679e2f68e0fc1d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659708"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="fb852-102">型パラメーターは修飾子として使用できません。</span><span class="sxs-lookup"><span data-stu-id="fb852-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="fb852-103">プログラミング要素は、型パラメーターを含む修飾文字列で修飾されます。</span><span class="sxs-lookup"><span data-stu-id="fb852-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="fb852-104">型パラメーターは、ジェネリック型が構築されるときに指定する型の要件を表します。</span><span class="sxs-lookup"><span data-stu-id="fb852-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="fb852-105">特定の定義された型は表しません。</span><span class="sxs-lookup"><span data-stu-id="fb852-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="fb852-106">修飾文字列には、コンパイル時に定義されている要素のみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb852-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="fb852-107">次のステートメントでは、このエラーが生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb852-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="fb852-108">**エラー ID:** BC32098</span><span class="sxs-lookup"><span data-stu-id="fb852-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fb852-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="fb852-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="fb852-110">修飾文字列から型パラメーターを削除するか、定義された型に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="fb852-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="fb852-111">修飾されているプログラミング要素の検索に構築された型を使用する必要がある場合は、プログラム ロジックの追加を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb852-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb852-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb852-112">See also</span></span>
- [<span data-ttu-id="fb852-113">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="fb852-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="fb852-114">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="fb852-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="fb852-115">型リスト</span><span class="sxs-lookup"><span data-stu-id="fb852-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
