---
title: '演算子の宣言は、のいずれかを指定する必要があります: +、-、*、-、-、^、&amp;などの Mod、Or、Xor、Not、 &lt; &lt;、 &gt; &gt;、=、 &lt; &gt;、 &lt;、 &lt;=、 &gt;、 &gt;=、CType、IsTrue、または IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: f32935dd4aaccd3040655b418badc13c1988c1b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622274"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="4064f-102">演算子の宣言は、のいずれかを指定する必要があります: +、-、\*、\,/、^、&amp;などの Mod、Or、Xor、Not、 &lt; &lt;、 &gt; &gt;.</span><span class="sxs-lookup"><span data-stu-id="4064f-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="4064f-103">オーバー ロードできるは、演算子のみを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="4064f-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="4064f-104">次の表は、演算子を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="4064f-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="4064f-105">型</span><span class="sxs-lookup"><span data-stu-id="4064f-105">Type</span></span>|<span data-ttu-id="4064f-106">演算子</span><span class="sxs-lookup"><span data-stu-id="4064f-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="4064f-107">単項</span><span class="sxs-lookup"><span data-stu-id="4064f-107">Unary</span></span>|<span data-ttu-id="4064f-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="4064f-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="4064f-109">2 項</span><span class="sxs-lookup"><span data-stu-id="4064f-109">Binary</span></span>|<span data-ttu-id="4064f-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="4064f-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="4064f-111">変換 (単項)</span><span class="sxs-lookup"><span data-stu-id="4064f-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="4064f-112">なお、`=`バイナリの一覧で演算子は、比較演算子、代入演算子ではありません。</span><span class="sxs-lookup"><span data-stu-id="4064f-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="4064f-113">**エラー ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="4064f-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4064f-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="4064f-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="4064f-115">演算子をオーバーロード可能な演算子の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="4064f-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="4064f-116">直接オーバーロードできない演算子をオーバーロードする機能が必要な場合は、適切なパラメーターを受け取り適切な値を返す `Function` プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="4064f-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4064f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4064f-117">See also</span></span>
- [<span data-ttu-id="4064f-118">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="4064f-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="4064f-119">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4064f-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="4064f-120">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="4064f-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="4064f-121">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="4064f-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="4064f-122">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="4064f-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
