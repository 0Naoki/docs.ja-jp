---
title: モデル アイテム ツリーのプログラミング
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: a24e52ec2b7cab10471d756a721611c6dd10516e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393489"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="8d6a4-102">モデル アイテム ツリーのプログラミング</span><span class="sxs-lookup"><span data-stu-id="8d6a4-102">Programming Model Item Tree</span></span>
<span data-ttu-id="8d6a4-103">このサンプルでは、移動、<xref:System.Activities.Presentation.Model.ModelItem>宣言型データ バインディング、Windows Presentation Foundation (WPF) のツリー ビューを使用してツリーします。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="8d6a4-104">サンプルの詳細</span><span class="sxs-lookup"><span data-stu-id="8d6a4-104">Sample Details</span></span>  
 <span data-ttu-id="8d6a4-105"><xref:System.Activities.Presentation.Model.ModelItem> ツリーは、編集する基のインスタンスに関するデータを公開するために [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] のインフラストラクチャで使用される抽象表現です。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="8d6a4-106">次の図は、[!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]のインフラストラクチャのさまざまな層を表しています。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-106">The following illustration is a depiction of the various layers of infrastructure within the [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>  
  
 <span data-ttu-id="8d6a4-107">![ワークフロー デザイナーのアーキテクチャ](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")</span><span class="sxs-lookup"><span data-stu-id="8d6a4-107">![Workflow Designer Architecture](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")</span></span>  
  
 <span data-ttu-id="8d6a4-108"><xref:System.Activities.Presentation.Model.ModelItem> は、基になる値へのポインターと、<xref:System.Activities.Presentation.Model.ModelProperty> オブジェクトのコレクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="8d6a4-109"><xref:System.Activities.Presentation.Model.ModelProperty> オブジェクトはさらに、プロパティの名前や型などのデータと、また別の <xref:System.Activities.Presentation.Model.ModelItem> である値へのポインターで構成されています。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="8d6a4-110"><xref:System.Activities.Presentation.Model.ModelItem> から返される一部の <xref:System.Activities.Presentation.Model.ModelProperty> に対しては、ツリー ビューに正しく表示されるように操作するために値コンバーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="8d6a4-111">このサンプルでは、次の例のような命令構文を使用して <xref:System.Activities.Presentation.Model.ModelItem> ツリーを命令型プログラミングで操作する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>  
  
```csharp  
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;  
ModelProperty mp = mi.Properties["Activities"];  
mp.Collection.Add(new Persist());  
ModelItem justAdded = mp.Collection.Last();  
justAdded.Properties["DisplayName"].SetValue("new name");  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="8d6a4-112">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="8d6a4-112">To use this sample</span></span>  
  
1.  <span data-ttu-id="8d6a4-113">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] で ProgrammingModelItemTree.sln ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-113">Open the ProgrammingModelItemTree.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="8d6a4-114">選択すると、ソリューションをビルド**ソリューションのビルド**から、**ビルド**メニュー。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="8d6a4-115">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-115">Press F5 to run the application.</span></span> <span data-ttu-id="8d6a4-116">[!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] フォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-116">The [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] form is then displayed.</span></span>  
  
4.  <span data-ttu-id="8d6a4-117">をクリックして、 **Load WF**を読み込む ボタン、<xref:System.Activities.Presentation.Model.ModelItem>ツリー ビューにバインドします。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>  
  
5.  <span data-ttu-id="8d6a4-118">クリックすると、 **Change Model Item Tree**ボタン、ツリーにアイテムを追加し、プロパティを設定するには、上記のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8d6a4-119">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8d6a4-120">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8d6a4-121">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8d6a4-122">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8d6a4-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="8d6a4-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d6a4-123">See Also</span></span>  
 <xref:System.Windows.Data.IValueConverter>
