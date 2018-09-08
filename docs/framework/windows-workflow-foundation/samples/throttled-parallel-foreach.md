---
title: 制限された並列 ForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 7149e6db8992bff5b436ffae4a77d985ec255986
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44215987"
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="b9f18-102">制限された並列 ForEach</span><span class="sxs-lookup"><span data-stu-id="b9f18-102">Throttled Parallel ForEach</span></span>
<span data-ttu-id="b9f18-103">`ThrottleParallelForEach`アクティビティと似ています、 <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach`アクティビティが 1 つの例外を使用できることを同時実行要因を設定を実行する同時分岐の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="b9f18-103">The `ThrottleParallelForEach` activity is similar to the <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="b9f18-104">`ThrottleParallelForEach` アクティビティは、<xref:System.Activities.NativeActivity> クラスを介してのみアクセスできる他のアクティビティ (子アクティビティ) をスケジュールする必要があるため、<xref:System.Activities.NativeActivityContext> クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="b9f18-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>  
  
## <a name="projects"></a><span data-ttu-id="b9f18-105">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="b9f18-105">Projects</span></span>  
  
|<span data-ttu-id="b9f18-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="b9f18-106">**ProjectName**</span></span>|<span data-ttu-id="b9f18-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="b9f18-107">**Description**</span></span>|<span data-ttu-id="b9f18-108">**メイン ファイル**</span><span class="sxs-lookup"><span data-stu-id="b9f18-108">**Main Files**</span></span>|  
|-|-|-|  
|<span data-ttu-id="b9f18-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="b9f18-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="b9f18-110">`ThrottledParallelForEach` アクティビティとそのデザイナーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9f18-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="b9f18-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="b9f18-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="b9f18-112">`ThrottledParallelForEach` アクティビティ定義。</span><span class="sxs-lookup"><span data-stu-id="b9f18-112">The `ThrottledParallelForEach` activity definition.</span></span>|  
|<span data-ttu-id="b9f18-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="b9f18-113">CodeTestClient</span></span>|<span data-ttu-id="b9f18-114">命令型コードを使用して、`ThrottledParallelForEach` を含むワークフローを構成および実行するサンプル クライアント アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="b9f18-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="b9f18-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="b9f18-115">Program.cs</span></span><br /><br /> <span data-ttu-id="b9f18-116">サンプル ワークフローのインスタンスを定義および実行します。</span><span class="sxs-lookup"><span data-stu-id="b9f18-116">Defines and runs an instance of the sample workflow.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b9f18-117">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="b9f18-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="b9f18-118">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、ThrottledParallelForEach.sln ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9f18-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ThrottledParallelForEach.sln file.</span></span>  
  
2.  <span data-ttu-id="b9f18-119">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b9f18-119">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b9f18-120">ソリューションを実行するには、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b9f18-120">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b9f18-121">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9f18-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b9f18-122">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b9f18-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b9f18-123">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="b9f18-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b9f18-124">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b9f18-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`