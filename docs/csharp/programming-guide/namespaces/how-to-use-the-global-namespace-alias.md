---
title: '方法: グローバル名前空間エイリアスを使用する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: 19d8d20ae630573b44399f8f5c5351f02b9fb1df
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236610"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="146bc-102">方法: グローバル名前空間エイリアスを使用する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="146bc-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="146bc-103">グローバル[名前空間](../../../csharp/language-reference/keywords/namespace.md)のメンバーにアクセスできると、そのメンバーが同名の別のエンティティによって隠される可能性がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="146bc-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="146bc-104">たとえば、次のコードでは、`Console` は、<xref:System> 名前空間の `Console` 型ではなく、`TestApp.Console` に解決されます。</span><span class="sxs-lookup"><span data-stu-id="146bc-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 <span data-ttu-id="146bc-105">`System.Console` を使用すると、`System` 名前空間が `TestApp.System` クラスによって隠されているため、依然としてエラーになります。</span><span class="sxs-lookup"><span data-stu-id="146bc-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 <span data-ttu-id="146bc-106">ただし、次のように `global::System.Console` を使用すると、このエラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="146bc-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 <span data-ttu-id="146bc-107">左の識別子が `global` の場合、右の識別子の検索はグローバル名前空間から開始されます。</span><span class="sxs-lookup"><span data-stu-id="146bc-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="146bc-108">たとえば、次の宣言は、グローバル空間のメンバーとして `TestApp` を参照します。</span><span class="sxs-lookup"><span data-stu-id="146bc-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 <span data-ttu-id="146bc-109">当然ながら、`System` という名前の独自の名前空間を作成することはお勧めしません。そのようなコードに遭遇することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="146bc-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="146bc-110">ただし、大型のプロジェクトでは、フォームによっては名前空間の重複が実際に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="146bc-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="146bc-111">そのような場合は、グローバル名前空間修飾子によって、ルート名前空間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="146bc-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="146bc-112">例</span><span class="sxs-lookup"><span data-stu-id="146bc-112">Example</span></span>  
 <span data-ttu-id="146bc-113">次の例では、`System` 名前空間を使用して `TestClass` クラスを格納しています。そのため、`System` クラスによって隠されている `System.Console` クラスを参照するのに `global::System.Console` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="146bc-113">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="146bc-114">また、`System.Collections` 名前空間を参照するのに `colAlias` エイリアスを使用するため、名前空間の代わりにこのエイリアスを使用して <xref:System.Collections.Hashtable?displayProperty=nameWithType> のインスタンスを作成しています。</span><span class="sxs-lookup"><span data-stu-id="146bc-114">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=nameWithType> was created using this alias instead of the namespace.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
<span data-ttu-id="146bc-115">**A 1**
**B 2**
**C 3**</span><span class="sxs-lookup"><span data-stu-id="146bc-115">**A 1**
**B 2**
**C 3**</span></span>

## <a name="see-also"></a><span data-ttu-id="146bc-116">参照</span><span class="sxs-lookup"><span data-stu-id="146bc-116">See Also</span></span>

- [<span data-ttu-id="146bc-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="146bc-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="146bc-118">名前空間</span><span class="sxs-lookup"><span data-stu-id="146bc-118">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
- [<span data-ttu-id="146bc-119">。演算子</span><span class="sxs-lookup"><span data-stu-id="146bc-119">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="146bc-120">::演算子</span><span class="sxs-lookup"><span data-stu-id="146bc-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="146bc-121">extern</span><span class="sxs-lookup"><span data-stu-id="146bc-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
