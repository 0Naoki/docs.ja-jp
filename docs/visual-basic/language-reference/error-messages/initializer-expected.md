---
title: 初期化子が必要です
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 1fa66a3c50b5c1eadd4c63b92c57ab60e1a11076
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595995"
---
# <a name="initializer-expected"></a><span data-ttu-id="d7cca-102">初期化子が必要です</span><span class="sxs-lookup"><span data-stu-id="d7cca-102">Initializer expected</span></span>
<span data-ttu-id="d7cca-103">初期化リストの空の場合、次の例に示すように、オブジェクト初期化子を使用して、クラスのインスタンスを宣言しようとしました。</span><span class="sxs-lookup"><span data-stu-id="d7cca-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="d7cca-104">次の例に示すように、少なくとも 1 つのフィールドまたはプロパティが、初期化子リストで初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7cca-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="d7cca-105">**エラー ID:** BC30996</span><span class="sxs-lookup"><span data-stu-id="d7cca-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d7cca-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d7cca-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d7cca-107">少なくとも 1 つのフィールドまたはプロパティで、初期化子を初期化または、オブジェクト初期化子を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="d7cca-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7cca-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7cca-108">See also</span></span>
- [<span data-ttu-id="d7cca-109">オブジェクト初期化子:名前付きの匿名型</span><span class="sxs-lookup"><span data-stu-id="d7cca-109">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="d7cca-110">方法: オブジェクト初期化子を使用してオブジェクトを宣言します。</span><span class="sxs-lookup"><span data-stu-id="d7cca-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
