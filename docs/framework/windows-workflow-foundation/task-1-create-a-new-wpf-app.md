---
title: タスク 1:新しい Windows Presentation Foundation アプリケーションの作成
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: dae523714862ed36d36e65b51be62acff9b17f51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193402"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="51d8b-102">タスク 1:新しい Windows Presentation Foundation アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="51d8b-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="51d8b-103">このタスクでは、WPF Application Visual Studio テンプレートを使用して空の Windows Presentation Foundation (WPF) アプリケーションを作成し、適切な参照を追加[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]ワークフロー アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="51d8b-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="51d8b-104">WPF アプリケーション プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="51d8b-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="51d8b-105">Visual Studio を起動し、**ファイル**メニューで、**新規**、順にクリックします**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="51d8b-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="51d8b-106">**新しいプロジェクト** ダイアログ ボックスで、いずれかを選択**Visual C#** または**Visual Basic**から、**インストールされたテンプレート**左側のウィンドウボックスのあります。</span><span class="sxs-lookup"><span data-stu-id="51d8b-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="51d8b-107">好みの言語が表示されない場合は、検索**他の言語**します。</span><span class="sxs-lookup"><span data-stu-id="51d8b-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="51d8b-108">選択**Windows**で、**インストールされたテンプレート**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="51d8b-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="51d8b-109">上部のペインのことを確認します (既定値) **.NET Framework 4**し、ドロップダウン リスト ボックスで、選択したされました**WPF アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="51d8b-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="51d8b-110">プロジェクトの名前を設定**HostingApplication**ウィンドウの下部にあります。</span><span class="sxs-lookup"><span data-stu-id="51d8b-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="51d8b-111">ソリューション名を設定**RehostingTheDesigner**します。</span><span class="sxs-lookup"><span data-stu-id="51d8b-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="51d8b-112">クリックして**OK**アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="51d8b-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="51d8b-113">Visual Studio では、アプリケーションの基本的な WPF UI を作成し、適切な XAML と分離コード ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="51d8b-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="51d8b-114">参照を追加**WorkflowModel**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="51d8b-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="51d8b-115">この場合に**ソリューション エクスプ ローラー**を右クリックし、 **HostingApplication**順に選択して**参照の追加**。</span><span class="sxs-lookup"><span data-stu-id="51d8b-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="51d8b-116">**参照の追加**ダイアログ ボックスで、をクリックして、 **.NET**  タブ、CTRL キーを押し、次のアセンブリを選択し、順にクリックします**OK**:</span><span class="sxs-lookup"><span data-stu-id="51d8b-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="51d8b-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="51d8b-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="51d8b-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="51d8b-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="51d8b-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="51d8b-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="51d8b-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d8b-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="51d8b-121">参照してください[タスク 2。ワークフロー デザイナーのホスティング](task-2-host-the-workflow-designer.md)をワークフロー デザイナーのデザイン キャンバスをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="51d8b-121">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51d8b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="51d8b-122">See also</span></span>

- [<span data-ttu-id="51d8b-123">ワークフロー デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="51d8b-123">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="51d8b-124">タスク 2:ワークフロー デザイナーのホスティング</span><span class="sxs-lookup"><span data-stu-id="51d8b-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
