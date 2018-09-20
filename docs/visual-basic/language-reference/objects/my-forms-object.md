---
title: My.Forms オブジェクト (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: d15765b7673f321d4362ceea0adb73959a7e7726
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2018
ms.locfileid: "46471224"
---
# <a name="myforms-object"></a><span data-ttu-id="15bfb-102">My.Forms オブジェクト</span><span class="sxs-lookup"><span data-stu-id="15bfb-102">My.Forms Object</span></span>
<span data-ttu-id="15bfb-103">プロパティは、現在のプロジェクトで宣言されている各 Windows フォームのインスタンスへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15bfb-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="15bfb-104">Remarks</span></span>  
 <span data-ttu-id="15bfb-105">`My.Forms`オブジェクトは、現在のプロジェクト内の各フォームのインスタンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="15bfb-106">プロパティの名前は、プロパティにアクセスするフォームの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="15bfb-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="15bfb-107">によって提供されるフォームへのアクセス、`My.Forms`修飾なしのフォームの名前を使用してオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="15bfb-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="15bfb-108">プロパティ名は、フォームの型名と同じであるためこれにより、既定のインスタンスがあった場合、フォームにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="15bfb-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="15bfb-109">たとえば、`My.Forms.Form1.Show` は、`Form1.Show` と同じです。</span><span class="sxs-lookup"><span data-stu-id="15bfb-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="15bfb-110">`My.Forms`オブジェクトには、現在のプロジェクトに関連付けられているフォームのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15bfb-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="15bfb-111">参照される Dll で宣言されているフォームへのアクセスは行いません。</span><span class="sxs-lookup"><span data-stu-id="15bfb-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="15bfb-112">DLL を提供するフォームにアクセスするには、ように、フォームの修飾名を使用する必要があります*DllName*.*FormName*します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="15bfb-113">使用することができます、<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>プロパティをアプリケーションのすべてのオープン フォームのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="15bfb-114">オブジェクトとそのプロパティは、Windows アプリケーションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="15bfb-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="15bfb-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="15bfb-115">Properties</span></span>  
 <span data-ttu-id="15bfb-116">各プロパティ、`My.Forms`オブジェクトは、現在のプロジェクトのフォームのインスタンスへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="15bfb-117">プロパティの名前は、プロパティがアクセスすると、フォームの名前と同じとプロパティの型が、フォームの型と同じです。</span><span class="sxs-lookup"><span data-stu-id="15bfb-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15bfb-118">フォームにアクセスするプロパティ名は、名前の競合がある場合*RootNamespace*_*Namespace*\_*FormName*します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="15bfb-119">たとえば、という名前の 2 つの形式`Form1.`ルート名前空間ではこれらの形式のいずれかのかどうか`WindowsApplication1`と名前空間に`Namespace1`を通じてそのフォームをアクセスするには`My.Forms.WindowsApplication1_Namespace1_Form1`。</span><span class="sxs-lookup"><span data-stu-id="15bfb-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="15bfb-120">`My.Forms`オブジェクトが起動時に作成されたアプリケーションのメイン フォームのインスタンスへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="15bfb-121">その他のすべてのフォーム、`My.Forms`オブジェクトにアクセスし、格納する場合は、フォームの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="15bfb-122">後続のプロパティにアクセスするは、フォームのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="15bfb-123">割り当てることで、フォームを破棄することができます`Nothing`そのフォームのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="15bfb-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="15bfb-124">プロパティ set アクセス操作子の呼び出し、<xref:System.Windows.Forms.Form.Close%2A>メソッドのフォーム、およびし割り当てます`Nothing`に格納されている値。</span><span class="sxs-lookup"><span data-stu-id="15bfb-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="15bfb-125">以外の任意の値を割り当てた場合`Nothing`プロパティの setter がスローされます、<xref:System.ArgumentException>例外。</span><span class="sxs-lookup"><span data-stu-id="15bfb-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="15bfb-126">プロパティかどうかをテストすることができます、`My.Forms`オブジェクトを使用して、フォームのインスタンスを格納する、`Is`または`IsNot`演算子。</span><span class="sxs-lookup"><span data-stu-id="15bfb-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="15bfb-127">これらの演算子を使用するには、プロパティの値をチェックする`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15bfb-128">通常、`Is`または`IsNot`オペレーターは、比較を実行するプロパティの値を読み取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="15bfb-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="15bfb-129">ただし、プロパティが現在格納されている場合`Nothing`プロパティ、フォームの新しいインスタンスを作成し、し、そのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="15bfb-130">ただし、Visual Basic コンパイラがのプロパティを処理、`My.Forms`でき、異なる方法でオブジェクト、`Is`または`IsNot`演算子をその値を変更することがなく、プロパティの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15bfb-131">例</span><span class="sxs-lookup"><span data-stu-id="15bfb-131">Example</span></span>  
 <span data-ttu-id="15bfb-132">この例は、既定のタイトルを変更`SidebarMenu`フォーム。</span><span class="sxs-lookup"><span data-stu-id="15bfb-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="15bfb-133">この例を動作させるには、プロジェクトがという名前のフォームをいる必要があります`SidebarMenu`します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="15bfb-134">このコードは、Windows アプリケーション プロジェクトでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="15bfb-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15bfb-135">要件</span><span class="sxs-lookup"><span data-stu-id="15bfb-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="15bfb-136">プロジェクトの種類ごとの可用性</span><span class="sxs-lookup"><span data-stu-id="15bfb-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="15bfb-137">プロジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="15bfb-137">Project type</span></span>|<span data-ttu-id="15bfb-138">使用可能</span><span class="sxs-lookup"><span data-stu-id="15bfb-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="15bfb-139">Windows アプリケーション</span><span class="sxs-lookup"><span data-stu-id="15bfb-139">Windows Application</span></span>|<span data-ttu-id="15bfb-140">**はい**</span><span class="sxs-lookup"><span data-stu-id="15bfb-140">**Yes**</span></span>|  
|<span data-ttu-id="15bfb-141">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="15bfb-141">Class Library</span></span>|<span data-ttu-id="15bfb-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="15bfb-142">No</span></span>|  
|<span data-ttu-id="15bfb-143">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="15bfb-143">Console Application</span></span>|<span data-ttu-id="15bfb-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="15bfb-144">No</span></span>|  
|<span data-ttu-id="15bfb-145">Windows コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="15bfb-145">Windows Control Library</span></span>|<span data-ttu-id="15bfb-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="15bfb-146">No</span></span>|  
|<span data-ttu-id="15bfb-147">Web コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="15bfb-147">Web Control Library</span></span>|<span data-ttu-id="15bfb-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="15bfb-148">No</span></span>|  
|<span data-ttu-id="15bfb-149">Windows サービス</span><span class="sxs-lookup"><span data-stu-id="15bfb-149">Windows Service</span></span>|<span data-ttu-id="15bfb-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="15bfb-150">No</span></span>|  
|<span data-ttu-id="15bfb-151">Web サイト</span><span class="sxs-lookup"><span data-stu-id="15bfb-151">Web Site</span></span>|<span data-ttu-id="15bfb-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="15bfb-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15bfb-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="15bfb-153">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="15bfb-154">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="15bfb-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="15bfb-155">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="15bfb-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="15bfb-156">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="15bfb-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="15bfb-157">アプリケーション フォームへのアクセス</span><span class="sxs-lookup"><span data-stu-id="15bfb-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
