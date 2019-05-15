---
title: WF の XAML ファイルに追加、デザイナーのビューステートの削除
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: af57f838ea12d7199268988bf01baa0b61447650
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637856"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a><span data-ttu-id="1dfba-102">デザイナーのビューステートの削除を XAML ファイルに追加します</span><span class="sxs-lookup"><span data-stu-id="1dfba-102">Removing the view state the designer adds to an XAML file</span></span>

<span data-ttu-id="1dfba-103">このサンプルでは、<xref:System.Xaml.XamlWriter> から派生するクラスを作成する方法を示し、XAML ファイルからビュー ステートを削除します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-103">This sample demonstrates how to create a class that derives from <xref:System.Xaml.XamlWriter> and removes view state from a XAML file.</span></span> [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] <span data-ttu-id="1dfba-104">は、ビュー ステートと呼ばれる情報を XAML ドキュメントに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-104">writes information into the XAML document, which is known as view state.</span></span> <span data-ttu-id="1dfba-105">ビュー ステートは、ランタイムでは不必要なレイアウト配置などの、デザイン時に必要な情報を参照します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-105">View state refers to the information that is required at design time, such as layout positioning, that is not required at runtime.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] <span data-ttu-id="1dfba-106">は、編集時に、XAML ドキュメントにこの情報を挿入します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-106">inserts this information into the XAML document as it is edited.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] <span data-ttu-id="1dfba-107">は、`mc:Ignorable` 属性を持つ XAML ファイルにビュー ステートを書き込みます。この結果、ランタイムが XAML ファイルを読み込みとき、この情報は読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="1dfba-107">writes the view state into the XAML file with the `mc:Ignorable` attribute, so this information is not loaded when the runtime loads the XAML file.</span></span> <span data-ttu-id="1dfba-108">このサンプルでは、XAML ノードの処理中にそのビューステート情報を削除するクラスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-108">This sample demonstrates how to create a class that removes that view state information while processing XAML nodes.</span></span>

## <a name="discussion"></a><span data-ttu-id="1dfba-109">説明</span><span class="sxs-lookup"><span data-stu-id="1dfba-109">Discussion</span></span>

<span data-ttu-id="1dfba-110">このサンプルでは、カスタム ライターを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-110">This sample demonstrates how to create a custom writer.</span></span>

<span data-ttu-id="1dfba-111">カスタム XAML ライターをビルドするには、<xref:System.Xaml.XamlWriter> を継承するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-111">To build a custom XAML writer, create a class that inherits from <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="1dfba-112">XAML ライターは多くの場合、入れ子になっていると、「内部」XAML ライターを追跡するのには一般的です。</span><span class="sxs-lookup"><span data-stu-id="1dfba-112">As XAML writers are often nested, it is typical to keep track of an "inner" XAML writer.</span></span> <span data-ttu-id="1dfba-113">これら"内部"ライターすると、仕事を行い、スタックの残りの部分の処理を委任し、複数のエントリ ポイントを持つことができます、XAML ライターの残りのスタックへの参照として考えることができます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-113">These "inner’ writers can be thought of as the reference to the remaining stack of XAML writers, allowing you to have multiple entry points to do work and then delegate processing to the remainder of the stack.</span></span>

<span data-ttu-id="1dfba-114">このサンプルには、重要な項目がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="1dfba-114">In this sample, there are a few items of interest.</span></span> <span data-ttu-id="1dfba-115">その 1 つとして、書き込まれる項目がデザイナー名前空間からのものであるかどうかの確認が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-115">One is the check to see whether the item being written is from a designer namespace.</span></span> <span data-ttu-id="1dfba-116">これにより、ワークフローでデザイナー名前空間の他の型の使用が排除されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1dfba-116">Note that this also strips out the use of other types from the designer namespace in a workflow.</span></span>

```csharp
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)
{
    return xamlMember.IsAttachable &&
        xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);
}

const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";

// The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.
public ViewStateCleaningWriter(XamlWriter innerWriter)
{
    this.InnerWriter = innerWriter;
    this.MemberStack = new Stack<XamlMember>();
}

XamlWriter InnerWriter {get; set; }
Stack<XamlMember> MemberStack {get; set; }
```

<span data-ttu-id="1dfba-117">これにより、ノード ストリームの走査中に使用される XAML メンバーのスタックも作成されます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-117">This also creates a stack of XAML members that are used while traversing the node stream.</span></span> <span data-ttu-id="1dfba-118">このサンプルの残りの作業は、主に `WriteStartMember` メソッドに含まれています。</span><span class="sxs-lookup"><span data-stu-id="1dfba-118">The remaining work of this sample is largely contained in the `WriteStartMember` method.</span></span>

```csharp
public override void WriteStartMember(XamlMember xamlMember)
{
    MemberStack.Push(xamlMember);

    if (IsDesignerAttachedProperty(xamlMember))
    {
        m_attachedPropertyDepth++;
    }

    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteStartMember(xamlMember);
}
```

<span data-ttu-id="1dfba-119">後続のメソッドで、まだビューステート コンテナーに含まれているかどうかがチェックされ、含まれている場合は制御が戻り、ノードはライター スタックに渡されません。</span><span class="sxs-lookup"><span data-stu-id="1dfba-119">Subsequent methods then check to see whether they are still contained in a view state container, and if so, return, and do not pass the node down the writer stack.</span></span>

```csharp
public override void WriteValue(Object value)
{
    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteValue(value);
}
```

<span data-ttu-id="1dfba-120">カスタム XAML ライターを使用するには、XAML ライターのスタックでまとめて連結する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dfba-120">To use a custom XAML writer, you must chain it together in a stack of XAML writers.</span></span> <span data-ttu-id="1dfba-121">この使用方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-121">The following code shows how this can be used.</span></span>

```csharp
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);
```

## <a name="to-use-this-sample"></a><span data-ttu-id="1dfba-122">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="1dfba-122">To use this sample</span></span>

1. <span data-ttu-id="1dfba-123">Visual Studio 2010 を使用して、ViewStateCleaningWriter.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-123">Using Visual Studio 2010, open the ViewStateCleaningWriter.sln solution file.</span></span>

2. <span data-ttu-id="1dfba-124">コマンド プロンプトを開き、ViewStageCleaningWriter.exe がビルドされているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-124">Open a command prompt and navigate to the directory where the ViewStageCleaningWriter.exe is built.</span></span>

3. <span data-ttu-id="1dfba-125">Workflow1.xaml ファイルに対して ViewStateCleaningWriter.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-125">Run ViewStateCleaningWriter.exe on the Workflow1.xaml file.</span></span>

   <span data-ttu-id="1dfba-126">実行可能ファイルの構文の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-126">The syntax for the executable is shown in the following example.</span></span>

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   <span data-ttu-id="1dfba-127">これにより、XAML ファイルを出力\[出力ファイル]、削除されたすべてのビュー状態情報を持ちます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-127">This outputs a XAML file to \[outfile], which has all its view state information removed.</span></span>

> [!NOTE]
> <span data-ttu-id="1dfba-128"><xref:System.Activities.Statements.Sequence> ワークフローでは、多数の仮想化のヒントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-128">For a <xref:System.Activities.Statements.Sequence> workflow, a number of virtualization hints are removed.</span></span> <span data-ttu-id="1dfba-129">その結果、デザイナーは次回の読み込み時にレイアウトを再計算します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-129">This causes the designer to recalculate layout the next time it is loaded.</span></span> <span data-ttu-id="1dfba-130">このサンプルを <xref:System.Activities.Statements.Flowchart> に対して使用すると、すべての配置情報および線のルーティング情報が削除され、後続のデザイナーへの読み込み時にすべてのアクティビティが画面の左側に積み上げられます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-130">When you use this sample for a <xref:System.Activities.Statements.Flowchart>, all positioning and line routing information are removed and on subsequent loading into the designer, all activities are stacked on the left side of the screen.</span></span>

## <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a><span data-ttu-id="1dfba-131">このサンプルで使用するサンプル XAML ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="1dfba-131">To create a sample XAML file for use with this sample</span></span>

1. <span data-ttu-id="1dfba-132">Visual Studio 2010 を開きます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-132">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="1dfba-133">新しいワークフロー コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-133">Create a new Workflow Console Application.</span></span>

3. <span data-ttu-id="1dfba-134">いくつかのアクティビティをキャンバスにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="1dfba-134">Drag and drop a few activities onto the canvas</span></span>

4. <span data-ttu-id="1dfba-135">ワークフロー XAML ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-135">Save the workflow XAML file.</span></span>

5. <span data-ttu-id="1dfba-136">XAML ファイルを調べて、ビューステートの添付プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="1dfba-136">Inspect the XAML file to see the view state attached properties.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1dfba-137">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="1dfba-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1dfba-138">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1dfba-138">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="1dfba-139">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="1dfba-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1dfba-140">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="1dfba-140">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`
