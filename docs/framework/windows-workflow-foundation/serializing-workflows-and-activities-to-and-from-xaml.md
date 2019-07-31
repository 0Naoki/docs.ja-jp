---
title: XAML との間のワークフローおよびアクティビティのシリアル化
ms.date: 03/30/2017
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
ms.openlocfilehash: c18afa7232adabc4f1c4e17fde993064b9189e39
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671896"
---
# <a name="serialize-workflows-and-activities-to-and-from-xaml"></a><span data-ttu-id="3eada-102">XAML との間でワークフローとアクティビティをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="3eada-102">Serialize Workflows and Activities to and from XAML</span></span>

<span data-ttu-id="3eada-103">ワークフロー定義は、アセンブリに含まれる型にコンパイルされるほか、XAML にシリアル化することもできます。</span><span class="sxs-lookup"><span data-stu-id="3eada-103">In addition to being compiled into types that are contained in assemblies, workflow definitions can also be serialized to XAML.</span></span> <span data-ttu-id="3eada-104">これらのシリアル化された定義は、編集や検査のために再度読み込んだり、コンパイルのためにビルド システムに渡したり、読み込んで呼び出したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3eada-104">These serialized definitions can be reloaded for editing or inspection, passed to a build system for compilation, or loaded and invoked.</span></span> <span data-ttu-id="3eada-105">このトピックでは、ワークフロー定義のシリアル化と XAML ワークフロー定義の使用に関する概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="3eada-105">This topic provides an overview of serializing workflow definitions and working with XAML workflow definitions.</span></span>

## <a name="work-with-xaml-workflow-definitions"></a><span data-ttu-id="3eada-106">XAML ワークフロー定義の操作</span><span class="sxs-lookup"><span data-stu-id="3eada-106">Work with XAML Workflow definitions</span></span>

<span data-ttu-id="3eada-107">シリアル化するワークフロー定義を作成するには、<xref:System.Activities.ActivityBuilder> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3eada-107">To create a workflow definition for serialization, the <xref:System.Activities.ActivityBuilder> class is used.</span></span> <span data-ttu-id="3eada-108"><xref:System.Activities.ActivityBuilder> の作成は、<xref:System.Activities.DynamicActivity> の作成とほとんど同じです。</span><span class="sxs-lookup"><span data-stu-id="3eada-108">Creating an <xref:System.Activities.ActivityBuilder> is very similar to creating a <xref:System.Activities.DynamicActivity>.</span></span> <span data-ttu-id="3eada-109">目的の引数を指定し、動作を構成するアクティビティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3eada-109">Any desired arguments are specified, and the activities that constitute the behavior are configured.</span></span> <span data-ttu-id="3eada-110">次の例では、2 つの入力引数を受け取り、それらを加算して結果を返す `Add` アクティビティを作成しています。</span><span class="sxs-lookup"><span data-stu-id="3eada-110">In the following example, an `Add` activity is created that takes two input arguments, adds them together, and returns the result.</span></span> <span data-ttu-id="3eada-111">このアクティビティは結果を返すため、ジェネリック <xref:System.Activities.ActivityBuilder%601> クラスが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3eada-111">Because this activity returns a result, the generic <xref:System.Activities.ActivityBuilder%601> class is used.</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#41](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]

<span data-ttu-id="3eada-112">それぞれの <xref:System.Activities.DynamicActivityProperty> インスタンスでワークフローへの入力引数を 1 つずつ表し、<xref:System.Activities.ActivityBuilder.Implementation%2A> にワークフローのロジックを構成するアクティビティが格納されています。</span><span class="sxs-lookup"><span data-stu-id="3eada-112">Each of the <xref:System.Activities.DynamicActivityProperty> instances represents one of the input arguments to the workflow, and the <xref:System.Activities.ActivityBuilder.Implementation%2A> contains the activities that make up the logic of the workflow.</span></span> <span data-ttu-id="3eada-113">この例では、右辺値の式が Visual Basic 式であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3eada-113">Note that the r-value expressions in this example are Visual Basic expressions.</span></span> <span data-ttu-id="3eada-114"><xref:System.Activities.Expressions.ExpressionServices.Convert%2A> を使用しないと、ラムダ式は XAML 形式にシリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="3eada-114">Lambda expressions are not serializable to XAML unless <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> is used.</span></span> <span data-ttu-id="3eada-115">ワークフローデザイナーでシリアル化されたワークフローを開いたり編集したりする場合は、Visual Basic 式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eada-115">If the serialized workflows are intended to be opened or edited in the workflow designer, then Visual Basic expressions should be used.</span></span> <span data-ttu-id="3eada-116">詳細については、「[命令型コードを使用したワークフロー、アクティビティ、および式の作成](authoring-workflows-activities-and-expressions-using-imperative-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3eada-116">For more information, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

<span data-ttu-id="3eada-117">XAML への <xref:System.Activities.ActivityBuilder> インスタンスで表されるワークフロー定義を XAML 形式にシリアル化するには、<xref:System.Activities.XamlIntegration.ActivityXamlServices> を使用して <xref:System.Xaml.XamlWriter> を作成した後、その <xref:System.Xaml.XamlServices> を使用することで、<xref:System.Xaml.XamlWriter> を使用してワークフロー定義をシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="3eada-117">To serialize the workflow definition represented by the <xref:System.Activities.ActivityBuilder> instance to XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> to create a <xref:System.Xaml.XamlWriter>, and then use <xref:System.Xaml.XamlServices> to serialize the workflow definition by using the <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="3eada-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices>には、xaml <xref:System.Activities.ActivityBuilder>との間でインスタンスをマップし、xaml ワークフローを読み込ん<xref:System.Activities.DynamicActivity>で、呼び出すことができるを返すメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3eada-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> has methods to map <xref:System.Activities.ActivityBuilder> instances to and from XAML and to load XAML workflows and return a <xref:System.Activities.DynamicActivity> that can be invoked.</span></span> <span data-ttu-id="3eada-119">次の例では、 <xref:System.Activities.ActivityBuilder>前の例のインスタンスを文字列にシリアル化し、ファイルに保存しています。</span><span class="sxs-lookup"><span data-stu-id="3eada-119">In the following example, the <xref:System.Activities.ActivityBuilder> instance from the previous example is serialized to a string and saved to a file.</span></span>

```csharp
// Serialize the workflow to XAML and store it in a string.
StringBuilder sb = new StringBuilder();
StringWriter tw = new StringWriter(sb);
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));
XamlServices.Save(xw, ab);
string serializedAB = sb.ToString();

// Display the XAML to the console.
Console.WriteLine(serializedAB);

// Serialize the workflow to XAML and save it to a file.
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));
XamlServices.Save(xw2, ab);
sw.Close();
```

<span data-ttu-id="3eada-120">シリアル化されたワークフローの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3eada-120">The following example represents the serialized workflow.</span></span>

```xaml
<Activity
  x:TypeArguments="x:Int32"
  x:Class="Add"
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <x:Members>
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />
  </x:Members>
  <Sequence>
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">
      <Assign.To>
        <OutArgument x:TypeArguments="x:Int32">
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />
          </OutArgument>
      </Assign.To>
    </Assign>
  </Sequence>
</Activity>
```

<span data-ttu-id="3eada-121">シリアル化されたワークフローを読み込む<xref:System.Activities.XamlIntegration.ActivityXamlServices>には、 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3eada-121">To load a serialized workflow, use the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="3eada-122">このメソッドは、シリアル化されたワークフロー定義を受け取り、ワークフロー定義を表す <xref:System.Activities.DynamicActivity> を返します。</span><span class="sxs-lookup"><span data-stu-id="3eada-122">This takes the serialized workflow definition and returns a <xref:System.Activities.DynamicActivity> that represents the workflow definition.</span></span> <span data-ttu-id="3eada-123">検証プロセス中に <xref:System.Activities.Activity.CacheMetadata%2A> の本体で <xref:System.Activities.DynamicActivity> が呼び出されるまでは、XAML は逆シリアル化されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3eada-123">Note that the XAML is not deserialized until <xref:System.Activities.Activity.CacheMetadata%2A> is called on the body of the <xref:System.Activities.DynamicActivity> during the validation process.</span></span> <span data-ttu-id="3eada-124">検証が明示的に呼び出されていない場合は、ワークフローが呼び出されたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="3eada-124">If validation is not explicitly called, then it is performed when the workflow is invoked.</span></span> <span data-ttu-id="3eada-125">XAML ワークフロー定義が無効な場合、<xref:System.ArgumentException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3eada-125">If the XAML workflow definition is invalid, then an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="3eada-126"><xref:System.Activities.Activity.CacheMetadata%2A> からスローされる例外は、<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> への呼び出しからエスケープされ、呼び出し元によって処理される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eada-126">Any exceptions thrown from <xref:System.Activities.Activity.CacheMetadata%2A> escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span> <span data-ttu-id="3eada-127">次の例では、前の例のシリアル化されたワークフローを読み込み、<xref:System.Activities.WorkflowInvoker> を使用して呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="3eada-127">In the following example, the serialized workflow from the previous example is loaded and invoked by using <xref:System.Activities.WorkflowInvoker>.</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#43](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]

<span data-ttu-id="3eada-128">このワークフローが呼び出されると、次の出力がコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3eada-128">When this workflow is invoked, the following output is displayed to the console.</span></span>

<span data-ttu-id="3eada-129">**25 + 15**</span><span class="sxs-lookup"><span data-stu-id="3eada-129">**25 + 15**</span></span>\
<span data-ttu-id="3eada-130">**40**</span><span class="sxs-lookup"><span data-stu-id="3eada-130">**40**</span></span>

> [!NOTE]
> <span data-ttu-id="3eada-131">入力引数と出力引数を使用してワークフローを呼び出す方法の詳細については<xref:System.Activities.WorkflowInvoker.Invoke%2A>、「 [Workflowinvoker 元と WorkflowApplication の使用](using-workflowinvoker-and-workflowapplication.md)」および「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3eada-131">For more information about invoking workflows with input and output arguments, see [Using WorkflowInvoker and WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) and <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span>

<span data-ttu-id="3eada-132">シリアル化されたC#ワークフローに式が<xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings>含まれて<xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A>いる場合、 `true`そのプロパティがに設定され<xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>たインスタンスは<xref:System.NotSupportedException> 、にパラメーターとして渡される必要があります。それ以外の場合は、次のようなメッセージと共にがスローされます。次のようになります。**式のアクティビティ型 ' CSharpValue ' 1 ' を実行するには、コンパイルが必要です。ワークフローがコンパイルされていることを確認してください。**</span><span class="sxs-lookup"><span data-stu-id="3eada-132">If the serialized workflow contains C# expressions, then an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true` must be passed as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, otherwise a <xref:System.NotSupportedException> will be thrown with a message similar to the following: **Expression Activity type 'CSharpValue\`1' requires compilation in order to run.  Please ensure that the workflow has been compiled.**</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

<span data-ttu-id="3eada-133">詳細については、「 [ C#式](csharp-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3eada-133">For more information, see [C# Expressions](csharp-expressions.md).</span></span>

<span data-ttu-id="3eada-134">シリアル化されたワークフロー定義は、 <xref:System.Activities.ActivityBuilder> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A>メソッド<xref:System.Activities.XamlIntegration.ActivityXamlServices>を使用してインスタンスに読み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="3eada-134">A serialized workflow definition can also be loaded into an <xref:System.Activities.ActivityBuilder> instance by using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> method.</span></span> <span data-ttu-id="3eada-135">シリアル化されたワークフローを<xref:System.Activities.ActivityBuilder>インスタンスに読み込むと、そのワークフローを検査および変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3eada-135">After a serialized workflow is loaded into an <xref:System.Activities.ActivityBuilder> instance, it can be inspected and modified.</span></span> <span data-ttu-id="3eada-136">これにより、デザイン プロセス中にワークフロー定義を保存したり再度読み込んだりするためのメカニズムが提供され、カスタム ワークフロー デザイナーを作成するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3eada-136">This is useful for custom workflow designer authors and provides a mechanism for saving and reloading workflow definitions during the design process.</span></span> <span data-ttu-id="3eada-137">次の例では、前の例のシリアル化されたワークフロー定義を読み込み、そのプロパティを検査しています。</span><span class="sxs-lookup"><span data-stu-id="3eada-137">In the following example, the serialized workflow definition from the previous example is loaded and its properties are inspected.</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#44](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
