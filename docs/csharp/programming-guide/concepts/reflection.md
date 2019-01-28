---
title: リフレクション (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: 8cdfe00a09d340d8b77f1f5582a3a3ad82c496b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537648"
---
# <a name="reflection-c"></a><span data-ttu-id="5c4f7-102">リフレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="5c4f7-102">Reflection (C#)</span></span>
<span data-ttu-id="5c4f7-103">リフレクションは、アセンブリ、モジュール、および型を記述する (<xref:System.Type> 型の) オブジェクトを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="5c4f7-104">リフレクションを使用すると、動的に型のインスタンスを作成したり、作成したインスタンスを既存のオブジェクトにバインドしたり、さらに既存のオブジェクトから型を取得してそのオブジェクトのメソッドを呼び出したり、フィールドやプロパティにアクセスしたりできます。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="5c4f7-105">コードで属性を使用している場合は、リフレクションを使用してそれらにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="5c4f7-106">詳細については、「[属性](../../../../docs/standard/attributes/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-106">For more information, see [Attributes](../../../../docs/standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="5c4f7-107">次の例は、`GetType` メソッドを使用して変数の型を取得する簡単なリフレクションを示しています。このメソッドは、`Object` 基底クラスからすべての型に継承される静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 <span data-ttu-id="5c4f7-108">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="5c4f7-109">次の例では、リフレクションを使用して、読み込まれたアセンブリの完全名を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```csharp  
// Using Reflection to get information from an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 <span data-ttu-id="5c4f7-110">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  <span data-ttu-id="5c4f7-111">C# の `protected` キーワードと `internal` キーワードは、IL では意味を持たないため、リフレクション API でも使用されません。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-111">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="5c4f7-112">IL では、"*ファミリ*" および "*アセンブリ*" という用語がこれに相当します。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-112">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="5c4f7-113">リフレクションを使用して `internal` メソッドを指定するには、<xref:System.Reflection.MethodBase.IsAssembly%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-113">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="5c4f7-114">`protected internal` メソッドを指定するには、<xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-114">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>  
  
## <a name="reflection-overview"></a><span data-ttu-id="5c4f7-115">リフレクションの概要</span><span class="sxs-lookup"><span data-stu-id="5c4f7-115">Reflection Overview</span></span>  
 <span data-ttu-id="5c4f7-116">リフレクションは、次の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-116">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="5c4f7-117">プログラムのメタデータ内の属性にアクセスする必要がある。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-117">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="5c4f7-118">詳細については、「[属性に格納されている情報の取得](../../../standard/attributes/retrieving-information-stored-in-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-118">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="5c4f7-119">アセンブリの型をチェックし、インスタンス化する。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-119">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="5c4f7-120">実行時に新しい型を作成する。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-120">For building new types at runtime.</span></span> <span data-ttu-id="5c4f7-121"><xref:System.Reflection.Emit> でクラスを使います。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-121">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="5c4f7-122">遅延バインディングを実行するために、実行時に作成された型でメソッドにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-122">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="5c4f7-123">「[型の動的な読み込みおよび使用](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c4f7-123">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5c4f7-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c4f7-124">Related Sections</span></span>  
 <span data-ttu-id="5c4f7-125">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5c4f7-125">For more information:</span></span>  
  
-   [<span data-ttu-id="5c4f7-126">リフレクション</span><span class="sxs-lookup"><span data-stu-id="5c4f7-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="5c4f7-127">型情報の表示</span><span class="sxs-lookup"><span data-stu-id="5c4f7-127">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="5c4f7-128">リフレクションとジェネリック型</span><span class="sxs-lookup"><span data-stu-id="5c4f7-128">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="5c4f7-129">属性に格納されている情報の取得</span><span class="sxs-lookup"><span data-stu-id="5c4f7-129">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="5c4f7-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c4f7-130">See also</span></span>

- [<span data-ttu-id="5c4f7-131">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5c4f7-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5c4f7-132">共通言語ランタイムのアセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c4f7-132">Assemblies in the Common Language Runtime</span></span>](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
