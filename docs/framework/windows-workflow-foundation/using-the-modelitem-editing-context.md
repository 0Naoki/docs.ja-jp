---
title: ModelItem 編集コンテキストの使用
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a2628bbbf2f6684e5d484b05cd5a2ac622f3b664
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296888"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="926d3-102">ModelItem 編集コンテキストの使用</span><span class="sxs-lookup"><span data-stu-id="926d3-102">Using the ModelItem Editing Context</span></span>
<span data-ttu-id="926d3-103"><xref:System.Activities.Presentation.Model.ModelItem> 編集コンテキストは、ホスト アプリケーションがデザイナーとの通信に使用するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="926d3-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <xref:System.Activities.Presentation.EditingContext> <span data-ttu-id="926d3-104">2 つのメソッドを公開する<xref:System.Activities.Presentation.EditingContext.Items%2A>と<xref:System.Activities.Presentation.EditingContext.Services%2A>、使用できます。</span><span class="sxs-lookup"><span data-stu-id="926d3-104">exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="926d3-105">Items コレクション</span><span class="sxs-lookup"><span data-stu-id="926d3-105">The Items collection</span></span>  
 <span data-ttu-id="926d3-106"><xref:System.Activities.Presentation.EditingContext.Items%2A> コレクションは、ホストとデザイナー間で共有されるデータ、またはすべてのデザイナーで使用可能なデータへのアクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="926d3-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="926d3-107">このコレクションには、<xref:System.Activities.Presentation.ContextItemManager> クラスを介してアクセスされる次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="926d3-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="926d3-108">Services コレクション</span><span class="sxs-lookup"><span data-stu-id="926d3-108">The Services collection</span></span>  
 <span data-ttu-id="926d3-109"><xref:System.Activities.Presentation.EditingContext.Services%2A> コレクションは、デザイナーとホスト間の対話に使用されるサービス、またはすべてのデザイナーで使用されるサービスへのアクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="926d3-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="926d3-110">このコレクションには、重要な次のメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="926d3-110">This collection has the following methods of note:</span></span>  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="926d3-111">デザイナーへのアクティビティの割り当て</span><span class="sxs-lookup"><span data-stu-id="926d3-111">Assigning a designer an activity</span></span>  
 <span data-ttu-id="926d3-112">アクティビティで使用されるデザイナーを指定するには、Designer 属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="926d3-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="926d3-113">サービスの作成</span><span class="sxs-lookup"><span data-stu-id="926d3-113">Creating a service</span></span>  
 <span data-ttu-id="926d3-114">デザイナーとホスト間の情報のコンジットとして機能するサービスを作成するには、インターフェイスと実装を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="926d3-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="926d3-115">インターフェイスはサービスのメンバーを定義するために <xref:System.Activities.Presentation.ServiceManager.Publish%2A> メソッドによって使用され、実装にはサービスのロジックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="926d3-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="926d3-116">次のコード例では、サービス インターフェイスと実装が作成されます。</span><span class="sxs-lookup"><span data-stu-id="926d3-116">In the following code example, a service interface and implementation are created.</span></span>  
  
```  
public interface IMyService  
    {  
        IEnumerable<string> GetValues(string DisplayName);  
    }  
  
    public class MyServiceImpl : IMyService  
    {  
        public IEnumerable<string> GetValues(string DisplayName)  
        {  
            return new string[]  {   
                DisplayName + " One",   
                DisplayName + " Two",  
                "Three " + DisplayName  
            } ;  
        }  
    }  
```  
  
## <a name="publishing-a-service"></a><span data-ttu-id="926d3-117">サービスの公開</span><span class="sxs-lookup"><span data-stu-id="926d3-117">Publishing a service</span></span>  
 <span data-ttu-id="926d3-118">デザイナーでサービスを使用するには、最初に <xref:System.Activities.Presentation.ServiceManager.Publish%2A> メソッドを使用してホストで公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="926d3-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="926d3-119">サービスの定期受信</span><span class="sxs-lookup"><span data-stu-id="926d3-119">Subscribing to a service</span></span>  
 <span data-ttu-id="926d3-120">デザイナーは、<xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> メソッドの <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> メソッドを使用してサービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="926d3-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="926d3-121">次のコード スニペットは、サービスを定期受信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="926d3-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
```  
protected override void OnModelItemChanged(object newItem)  
{  
    if (!subscribed)  
    {  
        this.Context.Services.Subscribe<IMyService>(  
            servInstance =>  
            {  
                listBox1.ItemsSource = servInstance.GetValues(this.ModelItem.Properties["DisplayName"].ComputedValue.ToString());  
            }  
            );  
        subscribed = true;   
    }  
}  
```  
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="926d3-122">Items コレクションを使用したデータの共有</span><span class="sxs-lookup"><span data-stu-id="926d3-122">Sharing data using the Items collection</span></span>  
 <span data-ttu-id="926d3-123">Items コレクションの使用は Services コレクションの使用と似ていますが、Publish の代わりに <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="926d3-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="926d3-124">このコレクションは、複雑な機能よりも、デザイナーとホスト間での単純なデータの共有に適しています。</span><span class="sxs-lookup"><span data-stu-id="926d3-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="926d3-125">EditingContext ホスト項目およびサービス</span><span class="sxs-lookup"><span data-stu-id="926d3-125">EditingContext host items and services</span></span>  
 <span data-ttu-id="926d3-126">.NET Framework では、さまざまな組み込みの項目とサービスの編集コンテキストを使用してアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="926d3-126">The .NET Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="926d3-127">項目:</span><span class="sxs-lookup"><span data-stu-id="926d3-127">Items:</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem><span data-ttu-id="926d3-128">:式エディター) などのコントロールのワークフロー内で使用される参照先ローカル アセンブリの一覧を管理します。</span><span class="sxs-lookup"><span data-stu-id="926d3-128">: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState><span data-ttu-id="926d3-129">:デザイナーが読み取り専用状態かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="926d3-129">: Indicates whether the designer is in a read-only state.</span></span>  
  
-   <xref:System.Activities.Presentation.View.Selection><span data-ttu-id="926d3-130">:現在選択されているオブジェクトのコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="926d3-130">: Defines the collection of objects that are currently selected.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem><span data-ttu-id="926d3-131">:</span><span class="sxs-lookup"><span data-stu-id="926d3-131">:</span></span>  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem><span data-ttu-id="926d3-132">:現在の編集セッションが基づくファイルについてを説明します。</span><span class="sxs-lookup"><span data-stu-id="926d3-132">: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="926d3-133">サービス:</span><span class="sxs-lookup"><span data-stu-id="926d3-133">Services:</span></span>  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService><span data-ttu-id="926d3-134">:プロパティは、現在のインスタンスに追加することができますを使用して<xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>します。</span><span class="sxs-lookup"><span data-stu-id="926d3-134">: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.View.DesignerView><span data-ttu-id="926d3-135">:デザイナー キャンバスのプロパティにアクセスをできます。</span><span class="sxs-lookup"><span data-stu-id="926d3-135">: Allows access to the properties of the designer canvas.</span></span>  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService><span data-ttu-id="926d3-136">:更新するツールボックスの内容を使用できます。</span><span class="sxs-lookup"><span data-stu-id="926d3-136">: Allows the contents of the toolbox to be updated.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService><span data-ttu-id="926d3-137">:カスタム指定されたサービスの実装とデザイナー コマンド (コンテキスト メニューなど) を統合するために使用します。</span><span class="sxs-lookup"><span data-stu-id="926d3-137">: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView><span data-ttu-id="926d3-138">:デザイナーのデバッガーの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="926d3-138">: Provides functionality for the designer debugger.</span></span>  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService><span data-ttu-id="926d3-139">:式エディター ダイアログへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="926d3-139">: Provides access to the Expression Editor dialog.</span></span>  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService><span data-ttu-id="926d3-140">:統合ヘルプ機能を備えた、デザイナーを提供します。</span><span class="sxs-lookup"><span data-stu-id="926d3-140">: Provides the designer with integrated help functionality.</span></span>  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService><span data-ttu-id="926d3-141">:使用して検証エラーにアクセスできる<xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>します。</span><span class="sxs-lookup"><span data-stu-id="926d3-141">: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService><span data-ttu-id="926d3-142">:データを格納および取得の内部のサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="926d3-142">: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="926d3-143">このサービスは、.NET Framework で内部的に使用し、外部使用のためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="926d3-143">This service is used internally by the .NET Framework, and is not intended for external use.</span></span>  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService><span data-ttu-id="926d3-144">:XAML 読み込みエラー コレクションを使用して、アクセスできるように<xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>します。</span><span class="sxs-lookup"><span data-stu-id="926d3-144">: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.Services.ModelService><span data-ttu-id="926d3-145">:編集されているワークフローのモデルと対話するデザイナーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="926d3-145">: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager><span data-ttu-id="926d3-146">:使用してモデル アイテム ツリーのルートへのアクセスを提供します。<xref:System.Activities.Presentation.Model.ModelItem.Root%2A>します。</span><span class="sxs-lookup"><span data-stu-id="926d3-146">: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.UndoEngine><span data-ttu-id="926d3-147">:提供元に戻すと、機能を再実行します。</span><span class="sxs-lookup"><span data-stu-id="926d3-147">: Provides undo and redo functionality.</span></span>  
  
-   <xref:System.Activities.Presentation.Services.ViewService><span data-ttu-id="926d3-148">:視覚的要素を基になるモデル アイテムにマップします。</span><span class="sxs-lookup"><span data-stu-id="926d3-148">: Maps visual elements to underlying model items.</span></span>  
  
-   <xref:System.Activities.Presentation.View.ViewStateService><span data-ttu-id="926d3-149">:ストアでは、モデル項目の状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="926d3-149">: Stores view states for model items.</span></span>  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService><span data-ttu-id="926d3-150">:仮想コンテナーの UI 動作をカスタマイズするために使用します。</span><span class="sxs-lookup"><span data-stu-id="926d3-150">: Used to customize the virtual container UI behavior.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService><span data-ttu-id="926d3-151">:登録およびイベント通知用のデリゲートを登録解除するために使用します。</span><span class="sxs-lookup"><span data-stu-id="926d3-151">: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="926d3-152">ウィンドウ所有者も設定できます。</span><span class="sxs-lookup"><span data-stu-id="926d3-152">Also allows a window owner to be set.</span></span>
