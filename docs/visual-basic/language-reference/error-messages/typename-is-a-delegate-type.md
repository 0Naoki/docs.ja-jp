---
title: "'<typename>' はデリゲート型です。"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c308805f5e73d740ff18a40d95b9cc2576ac95fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841261"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="2d97d-102">'\<typename>' はデリゲート型です。</span><span class="sxs-lookup"><span data-stu-id="2d97d-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="2d97d-103">'\<typename>' はデリゲート型です。</span><span class="sxs-lookup"><span data-stu-id="2d97d-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="2d97d-104">デリゲート構築では、引数リストとして 1 つの AddressOf 式のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d97d-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="2d97d-105">多くの場合、デリゲート構築ではなく、AddressOf 式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d97d-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="2d97d-106">デリゲート クラスのインスタンスを作成する`New`句で、デリゲート コンストラクタへの無効な引数リストが指定されています。</span><span class="sxs-lookup"><span data-stu-id="2d97d-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="2d97d-107">デリゲート インスタンスを新規作成するときは、単一の`AddressOf`式しか指定できません。</span><span class="sxs-lookup"><span data-stu-id="2d97d-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="2d97d-108">このエラーは、デリゲート コンストラクターへ引数を 1 つも渡していない場合、複数の引数を渡している場合、または有効な`AddressOf`式ではない 1 つの引数を渡している場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d97d-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="2d97d-109">**エラー ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="2d97d-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2d97d-110">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="2d97d-110">To correct this error</span></span>  
  
-   <span data-ttu-id="2d97d-111">`New`句で、デリゲート クラスの引数リストに単一の`AddressOf`式を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d97d-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d97d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d97d-112">See also</span></span>

- [<span data-ttu-id="2d97d-113">New 演算子</span><span class="sxs-lookup"><span data-stu-id="2d97d-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="2d97d-114">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="2d97d-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="2d97d-115">デリゲート</span><span class="sxs-lookup"><span data-stu-id="2d97d-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="2d97d-116">方法: デリゲート メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="2d97d-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
