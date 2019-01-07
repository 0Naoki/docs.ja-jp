---
title: カスタム属性の作成 (C#)
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: 0a27924623cc462f6d3339149718a1b29999ac1d
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058270"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="32c07-102">カスタム属性の作成 (C#)</span><span class="sxs-lookup"><span data-stu-id="32c07-102">Creating Custom Attributes (C#)</span></span>
<span data-ttu-id="32c07-103">属性クラスを定義することで、独自のカスタム属性を作成できます。属性クラスは、<xref:System.Attribute> の直接的または間接的な派生クラスです。これにより、メタデータの中で属性の定義をすばやく簡単に特定できます。</span><span class="sxs-lookup"><span data-stu-id="32c07-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="32c07-104">型にそれを記述したプログラマーの名前でタグを付けるとします。</span><span class="sxs-lookup"><span data-stu-id="32c07-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="32c07-105">`Author` というカスタム属性クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="32c07-105">You might define a custom `Author` attribute class:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class Author : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 <span data-ttu-id="32c07-106">クラス名は属性の名前の `Author` です。</span><span class="sxs-lookup"><span data-stu-id="32c07-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="32c07-107">このクラスは `System.Attribute` から派生しているので、カスタム属性クラスです。</span><span class="sxs-lookup"><span data-stu-id="32c07-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="32c07-108">コンストラクターのパラメーターはカスタム属性の位置指定パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="32c07-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="32c07-109">この例では、`name` が位置指定パラメーターになります。</span><span class="sxs-lookup"><span data-stu-id="32c07-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="32c07-110">パブリックな読み取り/書き込みフィールドまたはプロパティは名前付きパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="32c07-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="32c07-111">この場合は、`version` が唯一の名前付きパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="32c07-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="32c07-112">`AttributeUsage` 属性を使用して、クラスと `struct` の宣言に対してのみ `Author` 属性を有効にしていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="32c07-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="32c07-113">この新しい属性の使用方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="32c07-113">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="32c07-114">`AttributeUsage` には名前付きパラメーター `AllowMultiple` があります。これを使用すると、カスタム属性が 1 回しか指定できない属性か、または複数回指定できる属性かを設定できます。</span><span class="sxs-lookup"><span data-stu-id="32c07-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="32c07-115">次のコード例では、複数回指定できる属性が作成されます。</span><span class="sxs-lookup"><span data-stu-id="32c07-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 <span data-ttu-id="32c07-116">次のコード例では、同じ型の複数の属性が 1 つのクラスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="32c07-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="32c07-117">「</span><span class="sxs-lookup"><span data-stu-id="32c07-117">See Also</span></span>

- <xref:System.Reflection>  
- [<span data-ttu-id="32c07-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="32c07-118">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="32c07-119">カスタム属性の記述</span><span class="sxs-lookup"><span data-stu-id="32c07-119">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)  
- [<span data-ttu-id="32c07-120">リフレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="32c07-120">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
- [<span data-ttu-id="32c07-121">属性 (C#)</span><span class="sxs-lookup"><span data-stu-id="32c07-121">Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
- [<span data-ttu-id="32c07-122">リフレクションを使用した属性へのアクセス (C#)</span><span class="sxs-lookup"><span data-stu-id="32c07-122">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
- [<span data-ttu-id="32c07-123">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="32c07-123">AttributeUsage (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md)
