---
title: 構造体のデザイン
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3879dc3f0270a56132b44882a74c50d05914ff89
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862485"
---
# <a name="struct-design"></a><span data-ttu-id="68876-102">構造体のデザイン</span><span class="sxs-lookup"><span data-stu-id="68876-102">Struct Design</span></span>
<span data-ttu-id="68876-103">ほとんどの場合、汎用的な値の型は構造体、c# のキーワードと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="68876-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="68876-104">このセクションでは、一般的な構造体のデザインのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="68876-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="68876-105">**X DO NOT** 構造体の既定のコンス トラクターを提供します。</span><span class="sxs-lookup"><span data-stu-id="68876-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="68876-106">このガイドラインに従うには、配列の各項目に対して、コンス トラクターを実行することがなく作成する構造体の配列が使用できます。</span><span class="sxs-lookup"><span data-stu-id="68876-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="68876-107">C# で許可しないことを既定のコンス トラクターがある構造体に注意してください。</span><span class="sxs-lookup"><span data-stu-id="68876-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="68876-108">**X DO NOT** 変更可能な値の型を定義します。</span><span class="sxs-lookup"><span data-stu-id="68876-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="68876-109">変更可能な値の型には、いくつかの問題があります。</span><span class="sxs-lookup"><span data-stu-id="68876-109">Mutable value types have several problems.</span></span> <span data-ttu-id="68876-110">たとえば、プロパティ get アクセス操作子が値型を返すときに、呼び出し元は、コピーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="68876-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="68876-111">コピーが暗黙的に作成されるため、開発者があります、コピー、および元の値ではなくを変更することに注意してくださかった。</span><span class="sxs-lookup"><span data-stu-id="68876-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="68876-112">また、(動的言語、特に) の一部の言語では、ローカル変数を逆参照時にも、コピーできるようにするために、変更可能な値の型を使用して問題があります。</span><span class="sxs-lookup"><span data-stu-id="68876-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="68876-113">**✓ DO** すべてのインスタンス データの状態が 0 に設定されている、false の場合、または null (該当する場合) が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="68876-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="68876-114">構造体の配列が作成されたときに、無効なインスタンスの偶発的な作成ができないようにします。</span><span class="sxs-lookup"><span data-stu-id="68876-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="68876-115">**✓ DO** 実装<xref:System.IEquatable%601>を値の型。</span><span class="sxs-lookup"><span data-stu-id="68876-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="68876-116"><xref:System.Object.Equals%2A?displayProperty=nameWithType>値型のメソッドとボックス化、および既定の実装がリフレクションを使用しているために、非常に効率的です。</span><span class="sxs-lookup"><span data-stu-id="68876-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="68876-117"><xref:System.IEquatable%601.Equals%2A> 優れたパフォーマンスを持つことができ、ボックス化が発生しないように実装することができます。</span><span class="sxs-lookup"><span data-stu-id="68876-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="68876-118">**X DO NOT** 明示的に拡張<xref:System.ValueType>です。</span><span class="sxs-lookup"><span data-stu-id="68876-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="68876-119">実際、ほとんどの言語は、これを回避します。</span><span class="sxs-lookup"><span data-stu-id="68876-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="68876-120">一般に、構造体は非常に役に立ちますが、頻繁には手書きされませんが小さく、1 つ、不変の値にのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68876-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="68876-121">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="68876-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="68876-122">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="68876-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68876-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="68876-123">See also</span></span>

- [<span data-ttu-id="68876-124">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="68876-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="68876-125">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="68876-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="68876-126">クラスまたは構造体の選択</span><span class="sxs-lookup"><span data-stu-id="68876-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
