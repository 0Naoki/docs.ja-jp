---
title: nameof (C# リファレンス)
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 726abfd903f37826a247e6e98c0d11f230447550
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2018
ms.locfileid: "46577049"
---
# <a name="nameof-c-reference"></a><span data-ttu-id="e3904-102">nameof (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e3904-102">nameof (C# Reference)</span></span>

<span data-ttu-id="e3904-103">変数、型、またはメンバーの単純な (修飾されていない) 文字列名を取得するのに使用します。</span><span class="sxs-lookup"><span data-stu-id="e3904-103">Used to obtain the simple (unqualified) string name of a variable, type, or member.</span></span>  

<span data-ttu-id="e3904-104">コード内のエラーの報告、モデル ビュー コントローラー (MVC) リンクのフック、プロパティの変更されたイベントの起動などの際には、多くの場合、メソッドの文字列名をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="e3904-104">When reporting errors in code, hooking up model-view-controller (MVC) links, firing property changed events, etc., you often want to capture the string name of a method.</span></span>  <span data-ttu-id="e3904-105">`nameof` の使用は、定義の名前を変更するときに、コードを有効な状態に保つのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3904-105">Using `nameof` helps keep your code valid when renaming definitions.</span></span>  <span data-ttu-id="e3904-106">以前は、定義を参照するのに文字列リテラルを使用する必要がありました。ツールには、これらの文字列リテラルを検査する方法がわからないため、コード要素の名前変更の際には当てになりません。</span><span class="sxs-lookup"><span data-stu-id="e3904-106">Before, you had to use string literals to refer to definitions, which is brittle when renaming code elements because tools do not know to check these string literals.</span></span>  
  
 <span data-ttu-id="e3904-107">`nameof` 式のフォームは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3904-107">A `nameof` expression has this form:</span></span>  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a><span data-ttu-id="e3904-108">主なユース ケース</span><span class="sxs-lookup"><span data-stu-id="e3904-108">Key Use Cases</span></span>  
 <span data-ttu-id="e3904-109">ここでは、`nameof` の主なユース ケースを示します。</span><span class="sxs-lookup"><span data-stu-id="e3904-109">These examples show the key use cases for `nameof`.</span></span>  
  
 <span data-ttu-id="e3904-110">パラメーターの確認:</span><span class="sxs-lookup"><span data-stu-id="e3904-110">Validate parameters:</span></span>  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 <span data-ttu-id="e3904-111">MVC アクション リンク:</span><span class="sxs-lookup"><span data-stu-id="e3904-111">MVC Action links:</span></span>  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 <span data-ttu-id="e3904-112">INotifyPropertyChanged:</span><span class="sxs-lookup"><span data-stu-id="e3904-112">INotifyPropertyChanged:</span></span>  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 <span data-ttu-id="e3904-113">XAML 依存関係プロパティ:</span><span class="sxs-lookup"><span data-stu-id="e3904-113">XAML dependency property:</span></span>  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 <span data-ttu-id="e3904-114">ログ:</span><span class="sxs-lookup"><span data-stu-id="e3904-114">Logging:</span></span>  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 <span data-ttu-id="e3904-115">属性:</span><span class="sxs-lookup"><span data-stu-id="e3904-115">Attributes:</span></span>  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a><span data-ttu-id="e3904-116">使用例</span><span class="sxs-lookup"><span data-stu-id="e3904-116">Examples</span></span>  
 <span data-ttu-id="e3904-117">ここでは、C# の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="e3904-117">Some C# examples:</span></span>  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
class Test {  
    static void Main (string[] args) {  
        Console.WriteLine(nameof(C)); // -> "C"  
        Console.WriteLine(nameof(C.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(C.Method2)); // -> "Method2"  
        Console.WriteLine(nameof(c.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(c.Method2)); // -> "Method2"  
        // Console.WriteLine(nameof(z)); -> "z" [inside of Method2 ok, inside Method1 is a compiler error]  
        Console.WriteLine(nameof(Stuff)); // -> "Stuff"  
        // Console.WriteLine(nameof(T)); -> "T" [works inside of method but not in attributes on the method]  
        Console.WriteLine(nameof(f)); // -> "f"  
        // Console.WriteLine(nameof(f<T>)); -> [syntax error]  
        // Console.WriteLine(nameof(f<>)); -> [syntax error]  
        // Console.WriteLine(nameof(Method2())); -> [error "This expression does not have a name"]  
    }
}
```  
  
## <a name="remarks"></a><span data-ttu-id="e3904-118">コメント</span><span class="sxs-lookup"><span data-stu-id="e3904-118">Remarks</span></span>  
 <span data-ttu-id="e3904-119">`nameof` への引数は、簡易名、修飾名、メンバー アクセス、メンバーを指定した base アクセス、またはメンバーを指定した this アクセスでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e3904-119">The argument to `nameof` must be a simple name, qualified name, member access, base access with a specified member, or this access with a specified member.</span></span>  <span data-ttu-id="e3904-120">引数の式はコード定義を識別しますが、評価されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e3904-120">The argument expression identifies a code definition, but it is never evaluated.</span></span>  
  
 <span data-ttu-id="e3904-121">引数は構文上、式でなければならないため、許容されないものが多数あります。特に必要がないため、ここではこのようなものについて逐一取り上げていません。</span><span class="sxs-lookup"><span data-stu-id="e3904-121">Because the argument needs to be an expression syntactically, there are many things disallowed that are not useful to list.</span></span>  <span data-ttu-id="e3904-122">定義済みの型 (たとえば、`int` または `void`)、Null 許容型 (`Point?`)、配列型 (`Customer[,]`)、ポインター型 (`Buffer*`)、修飾されたエイリアス (`A::B`)、バインドされていないジェネリック型 (`Dictionary<,>`)、プリプロセッサ シンボル (`DEBUG`)、およびラベル (`loop:`) はエラーが発生するため、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="e3904-122">The following are worth mentioning that produce errors: predefined types (for example, `int` or `void`), nullable types (`Point?`), array types (`Customer[,]`), pointer types (`Buffer*`), qualified alias (`A::B`), and unbound generic types (`Dictionary<,>`), preprocessing symbols (`DEBUG`), and labels (`loop:`).</span></span>  
  
 <span data-ttu-id="e3904-123">完全修飾名を取得する必要がある場合は、`nameof` と共に `typeof` 式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3904-123">If you need to get the fully-qualified name, you can use the `typeof` expression along with `nameof`.</span></span>  <span data-ttu-id="e3904-124">例:</span><span class="sxs-lookup"><span data-stu-id="e3904-124">For example:</span></span>
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 <span data-ttu-id="e3904-125">残念ながら、`typeof` は `nameof` のような定数式ではないので、`nameof` が使われるすべての場所で `nameof` と組み合わせて `typeof` を使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="e3904-125">Unfortunately `typeof` is not a constant expression like `nameof`, so `typeof` cannot be used in conjunction with `nameof` in all the same places as `nameof`.</span></span>  <span data-ttu-id="e3904-126">たとえば、次のコードでは CS0182 コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e3904-126">For example, the following would cause a CS0182 compile error:</span></span>
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 <span data-ttu-id="e3904-127">上記の例では、型名を使用でき、インスタンス メソッド名にアクセスできることが分かります。</span><span class="sxs-lookup"><span data-stu-id="e3904-127">In the examples you see that you can use a type name and access an instance method name.</span></span>  <span data-ttu-id="e3904-128">評価された式で必要とされるような、型のインスタンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e3904-128">You do not need to have an instance of the type, as required in evaluated expressions.</span></span>  <span data-ttu-id="e3904-129">型名の使用は状況によっては非常に便利です。型名では名前を参照しているだけでインスタンス データを使用してはいないため、インスタンス変数や式を考慮する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e3904-129">Using the type name can be very convenient in some situations, and since you are just referring to the name and not using instance data, you do not need to contrive an instance variable or expression.</span></span>  
  
 <span data-ttu-id="e3904-130">クラスの属性式内でクラスのメンバーを参照できます。</span><span class="sxs-lookup"><span data-stu-id="e3904-130">You can reference the members of a class in attribute expressions on the class.</span></span>  
  
 <span data-ttu-id="e3904-131">"`Method1 (str, str)`" などの署名情報を取得する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="e3904-131">There is no way to get a signatures information such as "`Method1 (str, str)`".</span></span>  <span data-ttu-id="e3904-132">そうする 1 つの方法は、`Expression e = () => A.B.Method1("s1", "s2")` という式を使用し、結果として得られる式ツリーから MemberInfo を取得することです。</span><span class="sxs-lookup"><span data-stu-id="e3904-132">One way to do that is to use an Expression, `Expression e = () => A.B.Method1("s1", "s2")`, and pull the MemberInfo from the resulting expression tree.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="e3904-133">言語仕様</span><span class="sxs-lookup"><span data-stu-id="e3904-133">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3904-134">参照</span><span class="sxs-lookup"><span data-stu-id="e3904-134">See Also</span></span>

- [<span data-ttu-id="e3904-135">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="e3904-135">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e3904-136">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e3904-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e3904-137">typeof</span><span class="sxs-lookup"><span data-stu-id="e3904-137">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)  
