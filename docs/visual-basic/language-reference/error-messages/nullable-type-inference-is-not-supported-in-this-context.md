---
title: Null 許容型の推論はこのコンテキストではサポートされていません
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 7dffc5233656257cd892f573a2f8b9f91d781c21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611892"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="1b2bf-102">Null 許容型の推論はこのコンテキストではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="1b2bf-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="1b2bf-103">値型と構造体が null 許容宣言できます。</span><span class="sxs-lookup"><span data-stu-id="1b2bf-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="1b2bf-104">ただし、型の推定と組み合わせて、null 許容型の宣言を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1b2bf-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="1b2bf-105">次の例では、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1b2bf-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="1b2bf-106">**エラー ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="1b2bf-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b2bf-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1b2bf-107">To correct this error</span></span>  
  
-   <span data-ttu-id="1b2bf-108">使用して、 `As` null 許容型として変数を宣言する句。</span><span class="sxs-lookup"><span data-stu-id="1b2bf-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b2bf-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b2bf-109">See also</span></span>
- [<span data-ttu-id="1b2bf-110">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="1b2bf-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="1b2bf-111">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="1b2bf-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
