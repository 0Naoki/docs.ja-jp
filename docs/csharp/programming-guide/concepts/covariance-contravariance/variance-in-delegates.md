---
title: デリゲートの分散 (C#)
ms.date: 07/20/2015
ms.assetid: 19de89d2-8224-4406-8964-2965b732b890
ms.openlocfilehash: 3dabac4e532198871cf05d639aa692751ab17ae1
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208676"
---
# <a name="variance-in-delegates-c"></a><span data-ttu-id="cc9ba-102">デリゲートの分散 (C#)</span><span class="sxs-lookup"><span data-stu-id="cc9ba-102">Variance in Delegates (C#)</span></span>
<span data-ttu-id="cc9ba-103">.NET Framework 3.5 では、C# のすべてのデリゲートで、メソッド シグネチャとデリゲート型を一致させるために分散 (共変性と反変性) のサポートが導入されました。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C#.</span></span> <span data-ttu-id="cc9ba-104">つまり、シグネチャが一致するメソッドだけでなく、デリゲート型で指定された型よりも強い派生型を返す (共変性) メソッドや、弱い派生型のパラメーターを受け取る (反変性) メソッドを、デリゲートに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="cc9ba-105">これには、汎用デリゲートと非汎用デリゲートの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-105">This includes both generic and non-generic delegates.</span></span>  
  
 <span data-ttu-id="cc9ba-106">たとえば、次のコードについて考えます。このコードには、2 つのクラスと、汎用と非汎用の 2 つのデリゲートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>  
  
```csharp  
public class First { }  
public class Second : First { }  
public delegate First SampleDelegate(Second a);  
public delegate R SampleGenericDelegate<A, R>(A a);  
```  
  
 <span data-ttu-id="cc9ba-107">`SampleDelegate` 型または `SampleGenericDelegate<A, R>` 型のデリゲートを作成する場合、そのデリゲートには、次のいずれかのメソッドを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-107">When you create delegates of the `SampleDelegate` or `SampleGenericDelegate<A, R>` types, you can assign any one of the following methods to those delegates.</span></span>  
  
```csharp  
// Matching signature.  
public static First ASecondRFirst(Second first)  
{ return new First(); }  
  
// The return type is more derived.  
public static Second ASecondRSecond(Second second)  
{ return new Second(); }  
  
// The argument type is less derived.  
public static First AFirstRFirst(First first)  
{ return new First(); }  
  
// The return type is more derived   
// and the argument type is less derived.  
public static Second AFirstRSecond(First first)  
{ return new Second(); }  
```  
  
 <span data-ttu-id="cc9ba-108">次のコード例は、メソッド シグネチャとデリゲート型の間の暗黙的な変換を示しています。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>  
  
```csharp  
// Assigning a method with a matching signature   
// to a non-generic delegate. No conversion is necessary.  
SampleDelegate dNonGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type   
// and less derived argument type to a non-generic delegate.  
// The implicit conversion is used.  
SampleDelegate dNonGenericConversion = AFirstRSecond;  
  
// Assigning a method with a matching signature to a generic delegate.  
// No conversion is necessary.  
SampleGenericDelegate<Second, First> dGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type   
// and less derived argument type to a generic delegate.  
// The implicit conversion is used.  
SampleGenericDelegate<Second, First> dGenericConversion = AFirstRSecond;  
```  
  
 <span data-ttu-id="cc9ba-109">その他の例については、「[デリゲートの分散の使用 (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)」および「[Func および Action 汎用デリゲートでの分散の使用 (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-109">For more examples, see [Using Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="cc9ba-110">ジェネリック型パラメーターの分散</span><span class="sxs-lookup"><span data-stu-id="cc9ba-110">Variance in Generic Type Parameters</span></span>  
 <span data-ttu-id="cc9ba-111">.NET Framework 4 以降では、デリゲート間の暗黙的な変換を有効にできるため、ジェネリック型パラメーターによって汎用デリゲートにさまざまな型が指定されていても、型が分散の要件を満たすように相互に継承されていれば、それらの汎用デリゲートは相互に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-111">In .NET Framework 4 or later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>  
  
 <span data-ttu-id="cc9ba-112">暗黙的な変換を有効にするには、`in` キーワードまたは `out` キーワードを使用して、デリゲートでジェネリック パラメーターを共変または反変として明示的に宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>  
  
 <span data-ttu-id="cc9ba-113">次のコード例は、共変のジェネリック型パラメーターが指定されたデリゲートを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>  
  
```csharp  
// Type T is declared covariant by using the out keyword.  
public delegate T SampleGenericDelegate <out T>();  
  
public static void Test()  
{  
    SampleGenericDelegate <String> dString = () => " ";  
  
    // You can assign delegates to each other,  
    // because the type T is declared covariant.  
    SampleGenericDelegate <Object> dObject = dString;             
}  
```  
  
 <span data-ttu-id="cc9ba-114">分散サポートのみを使用してメソッド シグネチャをデリゲート型に一致させ、`in` キーワードと `out` キーワードを使用しない場合、同等のラムダ式かメソッドを使用すれば、デリゲートをインスタンス化できることがありますが、デリゲートを別のデリゲートに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>  
  
 <span data-ttu-id="cc9ba-115">次のコード例では、`String` が `Object` を継承していますが、`SampleGenericDelegate<String>` を `SampleGenericDelegate<Object>` に明示的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-115">In the following code example, `SampleGenericDelegate<String>` cannot be explicitly converted to `SampleGenericDelegate<Object>`, although `String` inherits `Object`.</span></span> <span data-ttu-id="cc9ba-116">この問題を修正するには、ジェネリック パラメーター `T` を `out` キーワードでマークします。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>  
  
```csharp  
public delegate T SampleGenericDelegate<T>();  
  
public static void Test()  
{  
    SampleGenericDelegate<String> dString = () => " ";  
  
    // You can assign the dObject delegate  
    // to the same lambda expression as dString delegate  
    // because of the variance support for   
    // matching method signatures with delegate types.  
    SampleGenericDelegate<Object> dObject = () => " ";  
  
    // The following statement generates a compiler error  
    // because the generic type T is not marked as covariant.  
    // SampleGenericDelegate <Object> dObject = dString;  
  
}  
```  
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="cc9ba-117">.NET Framework のバリアント型パラメーターが含まれる汎用デリゲート</span><span class="sxs-lookup"><span data-stu-id="cc9ba-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>  
 <span data-ttu-id="cc9ba-118">.NET Framework 4 では、既存の複数の汎用デリゲートで、ジェネリック型パラメーターに対して分散サポートが導入されました。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>  
  
-   <span data-ttu-id="cc9ba-119"><xref:System> 名前空間の `Action` デリゲート。<xref:System.Action%601>、<xref:System.Action%602> など</span><span class="sxs-lookup"><span data-stu-id="cc9ba-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>  
  
-   <span data-ttu-id="cc9ba-120"><xref:System> 名前空間の `Func` デリゲート。<xref:System.Func%601>、<xref:System.Func%602> など</span><span class="sxs-lookup"><span data-stu-id="cc9ba-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>  
  
-   <span data-ttu-id="cc9ba-121"><xref:System.Predicate%601> デリゲート</span><span class="sxs-lookup"><span data-stu-id="cc9ba-121">The <xref:System.Predicate%601> delegate</span></span>  
  
-   <span data-ttu-id="cc9ba-122"><xref:System.Comparison%601> デリゲート</span><span class="sxs-lookup"><span data-stu-id="cc9ba-122">The <xref:System.Comparison%601> delegate</span></span>  
  
-   <span data-ttu-id="cc9ba-123"><xref:System.Converter%602> デリゲート</span><span class="sxs-lookup"><span data-stu-id="cc9ba-123">The <xref:System.Converter%602> delegate</span></span>  
  
 <span data-ttu-id="cc9ba-124">使用例を含む詳細については、「[Func および Action 汎用デリゲートでの分散の使用 (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="cc9ba-125">汎用デリゲートのバリアント型パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="cc9ba-125">Declaring Variant Type Parameters in Generic Delegates</span></span>  
 <span data-ttu-id="cc9ba-126">汎用デリゲートに共変または反変のジェネリック型パラメーターがある場合、そのデリゲートは "*バリアント汎用デリゲート*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>  
  
 <span data-ttu-id="cc9ba-127">汎用デリゲートのジェネリック型パラメーターを共変として宣言するには、`out` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="cc9ba-128">共変の型は、メソッドの戻り値の型としてのみ使用できます。メソッド引数の型として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="cc9ba-129">共変の汎用デリゲートを宣言する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-129">The following code example shows how to declare a covariant generic delegate.</span></span>  
  
```csharp  
public delegate R DCovariant<out R>();  
```  
  
 <span data-ttu-id="cc9ba-130">汎用デリゲートのジェネリック型パラメーターを反変として宣言するには、`in` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-130">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="cc9ba-131">反変の型は、メソッド引数の型としてのみ使用できます。メソッドの戻り値の型として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-131">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="cc9ba-132">反変の汎用デリゲートを宣言する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-132">The following code example shows how to declare a contravariant generic delegate.</span></span>  
  
```csharp  
public delegate void DContravariant<in A>(A a);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc9ba-133">C# の `ref`、`in`、`out` パラメーターを、バリアントとしてマークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-133">`ref`, `in`, and `out` parameters in C# can't be marked as variant.</span></span>  
  
 <span data-ttu-id="cc9ba-134">同じデリゲートで、型パラメーターが異なる場合は、分散と共変性の両方をサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-134">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="cc9ba-135">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-135">This is shown in the following example.</span></span>  
  
```csharp  
public delegate R DVariant<in A, out R>(A a);  
```  
  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="cc9ba-136">バリアント汎用デリゲートのインスタンス化と呼び出し</span><span class="sxs-lookup"><span data-stu-id="cc9ba-136">Instantiating and Invoking Variant Generic Delegates</span></span>  
 <span data-ttu-id="cc9ba-137">バリアント デリゲートのインスタンス化および呼び出しは、インバリアント デリゲートのインスタンス化および呼び出しと同様に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-137">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="cc9ba-138">次の例では、ラムダ式によってデリゲートをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-138">In the following example, the delegate is instantiated by a lambda expression.</span></span>  
  
```csharp  
DVariant<String, String> dvariant = (String str) => str + " ";  
dvariant("test");  
```  
  
### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="cc9ba-139">バリアント汎用デリゲートの結合</span><span class="sxs-lookup"><span data-stu-id="cc9ba-139">Combining Variant Generic Delegates</span></span>  
 <span data-ttu-id="cc9ba-140">バリアント デリゲートの結合はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-140">You should not combine variant delegates.</span></span> <span data-ttu-id="cc9ba-141"><xref:System.Delegate.Combine%2A> メソッドはバリアント デリゲートの変換をサポートしていないため、デリゲートが厳密に同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-141">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="cc9ba-142">そのため、次のコード例に示すように、<xref:System.Delegate.Combine%2A> メソッドまたは `+` 演算子を使用してデリゲートを結合すると、実行時例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-142">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method or by using the `+` operator, as shown in the following code example.</span></span>  
  
```csharp  
Action<object> actObj = x => Console.WriteLine("object: {0}", x);  
Action<string> actStr = x => Console.WriteLine("string: {0}", x);  
// All of the following statements throw exceptions at run time.  
// Action<string> actCombine = actStr + actObj;  
// actStr += actObj;  
// Delegate.Combine(actStr, actObj);  
```  
  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="cc9ba-143">値型と参照型でのジェネリック型パラメーターの分散</span><span class="sxs-lookup"><span data-stu-id="cc9ba-143">Variance in Generic Type Parameters for Value and Reference Types</span></span>  
 <span data-ttu-id="cc9ba-144">ジェネリック型パラメーターの分散がサポートされるのは参照型だけです。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-144">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="cc9ba-145">たとえば、整数は値型であるため、`DVariant<int>` を `DVariant<Object>` または `DVariant<long>` に暗黙的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-145">For example, `DVariant<int>` can't be implicitly converted to `DVariant<Object>` or `DVariant<long>`, because integer is a value type.</span></span>  
  
 <span data-ttu-id="cc9ba-146">次の例は、値型ではジェネリック型パラメーターの分散がサポートされないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="cc9ba-146">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>  
  
```csharp  
// The type T is covariant.  
public delegate T DVariant<out T>();  
  
// The type T is invariant.  
public delegate T DInvariant<T>();  
  
public static void Test()  
{  
    int i = 0;  
    DInvariant<int> dInt = () => i;  
    DVariant<int> dVariantInt = () => i;  
  
    // All of the following statements generate a compiler error  
    // because type variance in generic parameters is not supported  
    // for value types, even if generic type parameters are declared variant.  
    // DInvariant<Object> dObject = dInt;  
    // DInvariant<long> dLong = dInt;  
    // DVariant<Object> dVariantObject = dVariantInt;  
    // DVariant<long> dVariantLong = dVariantInt;              
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc9ba-147">参照</span><span class="sxs-lookup"><span data-stu-id="cc9ba-147">See Also</span></span>

- [<span data-ttu-id="cc9ba-148">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="cc9ba-148">Generics</span></span>](~/docs/standard/generics/index.md)  
- [<span data-ttu-id="cc9ba-149">Func および Action 汎用デリゲートでの分散の使用 (C#)</span><span class="sxs-lookup"><span data-stu-id="cc9ba-149">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)  
- [<span data-ttu-id="cc9ba-150">方法: デリゲートを結合する (マルチキャスト デリゲート)</span><span class="sxs-lookup"><span data-stu-id="cc9ba-150">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
