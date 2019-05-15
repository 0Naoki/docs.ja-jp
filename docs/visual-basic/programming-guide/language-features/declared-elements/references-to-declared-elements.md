---
title: 宣言された要素の参照 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 616599e15c0d3d4c2177622d6820269bcff3ea39
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592799"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="e8a4c-102">宣言された要素の参照 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8a4c-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="e8a4c-103">宣言された要素をコードが参照されているとき、Visual Basic コンパイラはその名前の適切な宣言に、参照内の名前と一致します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="e8a4c-104">参照することはそれらの要素を制御するには 1 つ以上の要素が同じ名前で宣言されている場合*条件を満たす*の名前。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="e8a4c-105">コンパイラが名の宣言でへの参照を名前を照合しようとした場合、*最も狭いスコープ*します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="e8a4c-106">これは、参照するコードから開始して、下位レベルの要素を含むを通じてに向かってを意味します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="e8a4c-107">次の例では、同じ名前の 2 つの変数への参照を示します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="e8a4c-108">例では、2 つの変数を宣言して、各名前付き`totalCount`、モジュール内のスコープのさまざまなレベルで`container`します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="e8a4c-109">ときに、プロシージャ`showCount`が表示されます`totalCount`Visual Basic コンパイラが、最も狭いスコープ、ローカル宣言内 namely で宣言への参照を解決する限定なく`showCount`します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="e8a4c-110">適用されるときに`totalCount`を含んでいるモジュール`container`コンパイラがより広いスコープで宣言への参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="e8a4c-111">要素名の修飾</span><span class="sxs-lookup"><span data-stu-id="e8a4c-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="e8a4c-112">この検索処理をオーバーライドしより広い範囲での名前を宣言する必要がありますを指定する場合*修飾*より広いスコープの親要素と名前。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="e8a4c-113">場合によっては、コンテナーの要素を修飾する必要がありますも。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="e8a4c-114">ターゲット要素が定義されているかを識別する情報、ソース ステートメントの前に、名前手段を修飾します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="e8a4c-115">この情報と呼ばれる、*修飾文字列*します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="e8a4c-116">1 つ含めることができます、または複数の名前空間とモジュールの場合、クラスまたは構造体します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="e8a4c-117">修飾文字列には、モジュール、クラス、または対象の要素を含む構造体を指定する必要があります明確にします。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="e8a4c-118">コンテナーは、別のコンテナー要素名前空間には、通常で順番にある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="e8a4c-119">修飾文字列にいくつかのコンテナー要素を含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="e8a4c-120">その名前を修飾することによって宣言された要素にアクセスするには</span><span class="sxs-lookup"><span data-stu-id="e8a4c-120">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="e8a4c-121">要素が定義されている場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="e8a4c-122">名前空間、または名前空間の階層も可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="e8a4c-123">最下位レベルの名前空間内では、モジュール、クラスまたは構造体の要素を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2. <span data-ttu-id="e8a4c-124">ターゲット要素の場所に基づく修飾パスを決定します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="e8a4c-125">最上位レベルの名前空間を持つ開始、最下位レベルの名前空間に進むし、モジュール、クラス、または対象の要素を含む構造体と終了します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="e8a4c-126">パス内の各要素には、それに続く要素を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="e8a4c-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="e8a4c-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="e8a4c-128">ターゲット要素の修飾文字列を準備します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="e8a4c-129">ピリオドを挿入 (`.`)、パス内のすべての要素の後にします。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="e8a4c-130">アプリケーション、修飾文字列内のすべての要素へのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="e8a4c-131">式または代入ステートメントの通常の方法で、ターゲット要素に参照を記述します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="e8a4c-132">修飾文字列をターゲット要素名を前します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="e8a4c-133">名前は、期間直後にする必要があります (`.`) モジュール、クラス、または、要素を含む構造体に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="e8a4c-134">コンパイラでは、修飾文字列を使用して、ターゲット要素の参照を一致する明確であいまいさのない宣言を見つけます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="e8a4c-135">アプリケーションに同じ名前を持つ 1 つ以上のプログラミング要素へのアクセスがある場合は、名前の参照を修飾するためにもあります。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="e8a4c-136">たとえば、<xref:System.Windows.Forms>と<xref:System.Web.UI.WebControls>両方名前空間が含まれて、`Label`クラス (<xref:System.Windows.Forms.Label?displayProperty=nameWithType>と<xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="e8a4c-137">アプリケーションは、両方を使用する場合、または独自に定義している場合`Label`クラス、さまざまなを区別する必要があります`Label`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="e8a4c-138">変数の宣言には、名前空間やインポート エイリアスを含めます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="e8a4c-139">次の例では、インポート エイリアスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="e8a4c-140">コンテナー要素の他のメンバー</span><span class="sxs-lookup"><span data-stu-id="e8a4c-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="e8a4c-141">別のクラスまたは構造体の非共有メンバーを使用して、最初に、変数またはクラスまたは構造体のインスタンスを指す式を使用して、メンバー名を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="e8a4c-142">次の例では、`demoClass`という名前のクラスのインスタンスである`class1`します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="e8a4c-143">ないメンバーを修飾するために、クラス名自体を使用することはできません[Shared](../../../../visual-basic/language-reference/modifiers/shared.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="e8a4c-144">まず、オブジェクト変数にインスタンスを作成する必要があります (ここで`demoClass`) して、変数名で参照します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="e8a4c-145">クラスまたは構造体がある場合、 `Shared` 、メンバー クラスまたは構造体の名前を持つか、変数またはインスタンスを指す式では、そのメンバーを修飾することができます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="e8a4c-146">モジュールには、個別のインスタンスはありませんし、そのすべてのメンバーは`Shared`既定。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="e8a4c-147">そのため、モジュール名を持つモジュール メンバーを修飾します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="e8a4c-148">次の例では、モジュール メンバー プロシージャへの修飾参照を示します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="e8a4c-149">2 つの例では、宣言しています`Sub`という名前の手順、`perform`プロジェクト内の異なるモジュールでします。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="e8a4c-150">それぞれは独自のモジュール内で修飾なしを指定できますが、その他の場所から参照されている場合に修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="e8a4c-151">参照して、最終的なため`module3`修飾していない`perform`コンパイラは、その参照を解決できません。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="e8a4c-152">プロジェクトへの参照</span><span class="sxs-lookup"><span data-stu-id="e8a4c-152">References to Projects</span></span>  
 <span data-ttu-id="e8a4c-153">使用する[パブリック](../../../../visual-basic/language-reference/modifiers/public.md)別のプロジェクトで定義された要素は、まず、設定、*参照*にそのプロジェクトのアセンブリやタイプ ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="e8a4c-154">参照を設定するには、次のようにクリックします。**参照の追加**上、**プロジェクト**メニュー、または使用して、 [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md)コマンド ライン コンパイラ オプション。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="e8a4c-155">たとえば、.NET Framework の XML オブジェクト モデルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-155">For example, you can use the XML object model of the .NET Framework.</span></span> <span data-ttu-id="e8a4c-156">参照を設定した場合、<xref:System.Xml>名前空間宣言し、そのクラスのいずれかのように、使う<xref:System.Xml.XmlDocument>します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="e8a4c-157">次の例では<xref:System.Xml.XmlDocument>します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="e8a4c-158">コンテナー要素のインポート</span><span class="sxs-lookup"><span data-stu-id="e8a4c-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="e8a4c-159">使用することができます、 [Imports ステートメント (.NET Namespace よぶ型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)に*インポート*モジュールまたは使用するクラスを含む名前空間。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="e8a4c-160">これにより、その名前を完全修飾しなくても、インポートされた名前空間で定義されている要素を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="e8a4c-161">次の例では、リライトをインポートする前の例、<xref:System.Xml>名前空間。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="e8a4c-162">さらに、`Imports`ステートメントを定義できます、*インポート エイリアス*名前空間ごとにインポートします。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="e8a4c-163">これにより、ソース コードを短く読みやすくします。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="e8a4c-164">次の例を使用する前の例を書き換える`xD`のエイリアスとして、<xref:System.Xml>名前空間。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="e8a4c-165">`Imports`ステートメントは行いません他のプロジェクトから要素をアプリケーションに使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="e8a4c-166">つまり、参照設定の代わりにはなりません。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="e8a4c-167">だけ名前空間をインポートするには、その名前空間で定義された名前を修飾するために要件が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="e8a4c-168">使用することも、`Imports`モジュール、クラス、構造、および列挙型をインポートするステートメント。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="e8a4c-169">このようなインポートされた要素の修飾なしのメンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="e8a4c-170">ただし、常にクラスと構造体変数またはクラスまたは構造体のインスタンスに評価される式での非共有メンバーを修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="e8a4c-171">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="e8a4c-171">Naming Guidelines</span></span>  
 <span data-ttu-id="e8a4c-172">同じ名前を持つ 2 つ以上のプログラミング要素を定義するときに、*あいまいさを名前*コンパイラがその名前への参照を解決しようとすると発生することができます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="e8a4c-173">数より多い場合、スコープ内に 1 つの定義、または、参照が解決されない場合は、定義がスコープ内ではありません。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="e8a4c-174">たとえば、このヘルプ ページの「修飾参照例」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="e8a4c-175">すべての要素に一意の名前を指定することにより、名前のあいまいさを回避できます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="e8a4c-176">名前空間、モジュール、またはクラスでは、その名前を修飾しなくても、任意の要素への参照を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="e8a4c-177">正しくない要素を誤って参照する可能性を低くします。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="e8a4c-178">シャドウ</span><span class="sxs-lookup"><span data-stu-id="e8a4c-178">Shadowing</span></span>  
 <span data-ttu-id="e8a4c-179">2 つのプログラミング要素は、同じ名前を共有、うち 1 つが非表示できる、または*シャドウ*、もう 1 つ。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="e8a4c-180">シャドウされた要素は参照できません。代わりに、コードでは、シャドウされた要素名を使用する場合、Visual Basic コンパイラに解決されますがシャドウする要素。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="e8a4c-181">例を含む詳細については、次を参照してください。 [Visual Basic におけるシャドウ](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a4c-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8a4c-182">See also</span></span>

- [<span data-ttu-id="e8a4c-183">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="e8a4c-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="e8a4c-184">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="e8a4c-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="e8a4c-185">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="e8a4c-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="e8a4c-186">変数</span><span class="sxs-lookup"><span data-stu-id="e8a4c-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="e8a4c-187">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="e8a4c-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="e8a4c-188">New 演算子</span><span class="sxs-lookup"><span data-stu-id="e8a4c-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="e8a4c-189">Public</span><span class="sxs-lookup"><span data-stu-id="e8a4c-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
