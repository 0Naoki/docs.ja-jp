---
title: 等値演算子
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27550a8fd8292029cad9c2e699374a190b1a532e
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2018
ms.locfileid: "46526491"
---
# <a name="equality-operators"></a><span data-ttu-id="c3005-102">等値演算子</span><span class="sxs-lookup"><span data-stu-id="c3005-102">Equality Operators</span></span>
<span data-ttu-id="c3005-103">このセクションでは、等値演算子のオーバー ロードをについて説明しを指す`operator==`と`operator!=`として等値演算子。</span><span class="sxs-lookup"><span data-stu-id="c3005-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="c3005-104">**X DO NOT** 等値演算子および以外のいずれかのオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="c3005-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="c3005-105">**✓ DO** いることを確認<xref:System.Object.Equals%2A?displayProperty=nameWithType>等値演算子は、同じセマンティクスと同様のパフォーマンス特性があるとします。</span><span class="sxs-lookup"><span data-stu-id="c3005-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="c3005-106">多くの場合、つまり`Object.Equals`等値演算子はオーバー ロード時にオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3005-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="c3005-107">**X AVOID** 等値演算子から例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="c3005-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="c3005-108">たとえば、引数のいずれかがスローする代わりに null の場合は false を返す`NullReferenceException`します。</span><span class="sxs-lookup"><span data-stu-id="c3005-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="c3005-109">値の型で等値演算子</span><span class="sxs-lookup"><span data-stu-id="c3005-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="c3005-110">**✓ DO** 等しいかどうかがわかりやすい場合は、値型で等値演算子をオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="c3005-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="c3005-111">ほとんどのプログラミング言語での既定の実装がない`operator==`値の型。</span><span class="sxs-lookup"><span data-stu-id="c3005-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="c3005-112">参照型で等値演算子</span><span class="sxs-lookup"><span data-stu-id="c3005-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="c3005-113">**X AVOID** 変更可能な参照型で等値演算子のオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="c3005-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="c3005-114">多くの言語では、参照型の組み込みの等値演算子があります。</span><span class="sxs-lookup"><span data-stu-id="c3005-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="c3005-115">組み込みの演算子は、通常は参照の等価性を実装し、値の等価性を既定の動作が変更されたときに、多くの開発者は驚かします。</span><span class="sxs-lookup"><span data-stu-id="c3005-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="c3005-116">この問題は、不変性をより参照の等価性と値の等価性の間の違いに注意をはるかに困難になるために、変更不可の参照型の軽減されます。</span><span class="sxs-lookup"><span data-stu-id="c3005-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="c3005-117">**X AVOID** 実装では、参照の等価性の場合よりもはるかに低速になる場合は、参照型で等値演算子をオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="c3005-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="c3005-118">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="c3005-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c3005-119">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="c3005-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3005-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3005-120">See also</span></span>

- [<span data-ttu-id="c3005-121">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c3005-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="c3005-122">使用方法のガイドライン</span><span class="sxs-lookup"><span data-stu-id="c3005-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
