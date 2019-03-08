---
title: "'<typename>' はデリゲート型です。"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4278ea0fc6a8dc2c6a90b720d2da70b1c26f2a17
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283453"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="cc59c-102">'\<typename>' はデリゲート型です。</span><span class="sxs-lookup"><span data-stu-id="cc59c-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="cc59c-103">'\<typename>' はデリゲート型です。</span><span class="sxs-lookup"><span data-stu-id="cc59c-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="cc59c-104">デリゲート構築では、引数リストとして 1 つの AddressOf 式のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="cc59c-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="cc59c-105">多くの場合、デリゲート構築ではなく、AddressOf 式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc59c-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="cc59c-106">A`New`デリゲート クラスのインスタンスを作成する句は、デリゲート コンス トラクターに無効な引数リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="cc59c-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="cc59c-107">1 つだけを指定する`AddressOf`新しいデリゲート インスタンスを作成するときの式。</span><span class="sxs-lookup"><span data-stu-id="cc59c-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="cc59c-108">1 つ以上の引数を渡すまたは有効なではない場合は 1 つの引数を渡す場合、デリゲート コンス トラクターに引数を渡したしない場合、このエラーは発生`AddressOf`式。</span><span class="sxs-lookup"><span data-stu-id="cc59c-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="cc59c-109">**エラー ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="cc59c-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cc59c-110">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="cc59c-110">To correct this error</span></span>  
  
-   <span data-ttu-id="cc59c-111">1 つを使用して、`AddressOf`にデリゲート クラスの引数リスト内の式、`New`句。</span><span class="sxs-lookup"><span data-stu-id="cc59c-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc59c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc59c-112">See also</span></span>
- [<span data-ttu-id="cc59c-113">New 演算子</span><span class="sxs-lookup"><span data-stu-id="cc59c-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="cc59c-114">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="cc59c-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="cc59c-115">デリゲート</span><span class="sxs-lookup"><span data-stu-id="cc59c-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="cc59c-116">方法: デリゲート メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="cc59c-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
