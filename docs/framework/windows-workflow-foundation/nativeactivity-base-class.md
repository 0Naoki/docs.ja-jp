---
title: NativeActivity の基本クラス
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: d746bb92dab79e7e68075ad003c420e7e37ed683
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637510"
---
# <a name="nativeactivity-base-class"></a><span data-ttu-id="09f53-102">NativeActivity の基本クラス</span><span class="sxs-lookup"><span data-stu-id="09f53-102">NativeActivity Base Class</span></span>

<span data-ttu-id="09f53-103"><xref:System.Activities.NativeActivity> はプロテクト コンストラクターを持つ抽象クラスです。</span><span class="sxs-lookup"><span data-stu-id="09f53-103"><xref:System.Activities.NativeActivity> is an abstract class with a protected constructor.</span></span> <span data-ttu-id="09f53-104"><xref:System.Activities.CodeActivity> と同様に、<xref:System.Activities.NativeActivity> は、<xref:System.Activities.NativeActivity.Execute%2A> メソッドを実装して、強制的な動作を記述するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="09f53-104">Like <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> is used for writing imperative behavior by implementing an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span> <span data-ttu-id="09f53-105"><xref:System.Activities.CodeActivity> とは異なり、<xref:System.Activities.NativeActivity> からは、<xref:System.Activities.NativeActivityContext> メソッドに渡される <xref:System.Activities.NativeActivity.Execute%2A> オブジェクトを介して、ワークフロー ランタイムの公開されているすべての機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="09f53-105">Unlike <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> has access to all of the exposed features of the workflow runtime through the <xref:System.Activities.NativeActivityContext> object passed to the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

## <a name="using-nativeactivitycontext"></a><span data-ttu-id="09f53-106">NativeActivityContext の使用</span><span class="sxs-lookup"><span data-stu-id="09f53-106">Using NativeActivityContext</span></span>
 <span data-ttu-id="09f53-107">ワークフロー ランタイムの機能は、<xref:System.Activities.NativeActivity.Execute%2A> 型の `context` パラメーターを使用して、<xref:System.Activities.NativeActivityContext> メソッド内からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="09f53-107">Features of the workflow runtime can be accessed from within the <xref:System.Activities.NativeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.NativeActivityContext>.</span></span> <span data-ttu-id="09f53-108"><xref:System.Activities.NativeActivityContext> を介して、以下のような機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="09f53-108">The features available through <xref:System.Activities.NativeActivityContext> include the following:</span></span>

- <span data-ttu-id="09f53-109">引数と変数を取得および設定する。</span><span class="sxs-lookup"><span data-stu-id="09f53-109">Getting and setting of arguments and variables.</span></span>

- <span data-ttu-id="09f53-110"><xref:System.Activities.NativeActivityContext.ScheduleActivity%2A> を使用して子のアクティビティのスケジュールを設定する。</span><span class="sxs-lookup"><span data-stu-id="09f53-110">Scheduling child activities with <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span></span>

- <span data-ttu-id="09f53-111"><xref:System.Activities.NativeActivityContext.Abort%2A> を使用してアクティビティの実行を中止する。</span><span class="sxs-lookup"><span data-stu-id="09f53-111">Aborting activity execution using <xref:System.Activities.NativeActivityContext.Abort%2A>.</span></span>

- <span data-ttu-id="09f53-112"><xref:System.Activities.NativeActivityContext.CancelChild%2A> および <xref:System.Activities.NativeActivityContext.CancelChildren%2A> を使用して子の実行を取り消す。</span><span class="sxs-lookup"><span data-stu-id="09f53-112">Canceling child execution using <xref:System.Activities.NativeActivityContext.CancelChild%2A> and <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span></span>

- <span data-ttu-id="09f53-113"><xref:System.Activities.NativeActivityContext.CreateBookmark%2A>、<xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>、および <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A> などのメソッドを使用して、アクティビティのブックマークにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="09f53-113">Access to activity bookmarks using such methods as <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, and <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span></span>

- <span data-ttu-id="09f53-114"><xref:System.Activities.CodeActivityContext.Track%2A> を使用したカスタムの追跡機能。</span><span class="sxs-lookup"><span data-stu-id="09f53-114">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="09f53-115"><xref:System.Activities.CodeActivityContext.GetProperty%2A> および <xref:System.Activities.NativeActivityContext.GetValue%2A> を使用して、アクティビティの実行プロパティと値プロパティにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="09f53-115">Access to the activity’s execution properties and value properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A> and <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span></span>

- <span data-ttu-id="09f53-116"><xref:System.Activities.NativeActivityContext.ScheduleAction%2A> および <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A> を使用してアクティビティのアクションと機能のスケジュールを設定する。</span><span class="sxs-lookup"><span data-stu-id="09f53-116">Scheduling activity actions and functions using <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> and <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span></span>

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a><span data-ttu-id="09f53-117">NativeActivity から継承するカスタム アクティビティを作成するには</span><span class="sxs-lookup"><span data-stu-id="09f53-117">To create a custom activity that inherits from NativeActivity</span></span>

1. <span data-ttu-id="09f53-118">OpenVisual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="09f53-118">OpenVisual Studio 2010.</span></span>

2. <span data-ttu-id="09f53-119">選択**ファイル**、**新しい**、し**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="09f53-119">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="09f53-120">選択**Workflow 4.0**  **Visual c#** で、**プロジェクトの種類**ウィンドウ、および選択、 **v2010**ノード。</span><span class="sxs-lookup"><span data-stu-id="09f53-120">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="09f53-121">選択**アクティビティ ライブラリ**で、**テンプレート**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="09f53-121">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="09f53-122">新しいプロジェクトに HelloActivity という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="09f53-122">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="09f53-123">HelloActivity プロジェクトの Activity1.xaml を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="09f53-123">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="09f53-124">HelloActivity プロジェクトを右クリックして**追加**、し**クラス**します。</span><span class="sxs-lookup"><span data-stu-id="09f53-124">Right-click the HelloActivity project and select **Add**, and then **Class**.</span></span> <span data-ttu-id="09f53-125">新しいクラスに HelloActivity.cs という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="09f53-125">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="09f53-126">HelloActivity.cs ファイルで、次の `using` ディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="09f53-126">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="09f53-127">クラス宣言に基本クラスを追加することにより、新しいクラスで <xref:System.Activities.NativeActivity> から継承します。</span><span class="sxs-lookup"><span data-stu-id="09f53-127">Make the new class inherit from <xref:System.Activities.NativeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. <span data-ttu-id="09f53-128"><xref:System.Activities.NativeActivity.Execute%2A> メソッドを追加して、このクラスに機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="09f53-128">Add functionality to the class by adding an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="09f53-129"><xref:System.Activities.NativeActivity.CacheMetadata%2A> メソッドをオーバーライドして適切な Add メソッドを呼び出し、カスタム アクティビティの変数、引数、子およびデリゲートについてワークフロー ランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="09f53-129">Override the <xref:System.Activities.NativeActivity.CacheMetadata%2A> method and call the appropriate Add method to let the workflow runtime know about the custom activity’s variables, arguments, children, and delegates.</span></span> <span data-ttu-id="09f53-130">詳細については、<xref:System.Activities.NativeActivityMetadata> クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09f53-130">For more information see the <xref:System.Activities.NativeActivityMetadata> class.</span></span>

9. <span data-ttu-id="09f53-131"><xref:System.Activities.NativeActivityContext> オブジェクトを使用してブックマークをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="09f53-131">Use the <xref:System.Activities.NativeActivityContext> object to schedule a bookmark.</span></span> <span data-ttu-id="09f53-132">ブックマークを作成、スケジュール、および再開する方法の詳細については、「<xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09f53-132">See <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> for details on how to create, schedule, and resume a bookmark.</span></span>

    ```
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```
