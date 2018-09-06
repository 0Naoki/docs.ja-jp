---
title: WCF 分析トレース
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 006f8aa0bc2f32e43269aa83433e8ca7a773a1c9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43732356"
---
# <a name="wcf-analytic-tracing"></a><span data-ttu-id="dede0-102">WCF 分析トレース</span><span class="sxs-lookup"><span data-stu-id="dede0-102">WCF Analytic Tracing</span></span>
<span data-ttu-id="dede0-103">このサンプルは、Windows Communication Foundation (WCF) が ETW に書き込む分析トレースのストリームに独自のトレース イベントを追加する方法を示します[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="dede0-103">This sample demonstrates how to add your own tracing events into the stream of analytic traces that Windows Communication Foundation (WCF) writes to ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="dede0-104">分析トレースは、パフォーマンスを低下させずに簡単にサービスを確認できるようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="dede0-104">Analytic traces are meant to make it easy to get visibility into your services without paying a high performance penalty.</span></span> <span data-ttu-id="dede0-105">このサンプルは、使用する方法を示します、 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> Api を WCF サービスと統合されるイベントを記述します。</span><span class="sxs-lookup"><span data-stu-id="dede0-105">This sample shows how to use the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs to write events that integrate with WCF services.</span></span>  
  
 <span data-ttu-id="dede0-106">詳細については、 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> Api を参照してください<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="dede0-106">For more information about the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs, see <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="dede0-107">Windows でのイベント トレースの詳細についてを参照してください。[デバッグの向上およびパフォーマンス調整 ETW を](https://go.microsoft.com/fwlink/?LinkId=166488)します。</span><span class="sxs-lookup"><span data-stu-id="dede0-107">To learn more about event tracing in Windows, see [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkId=166488).</span></span>  
  
## <a name="disposing-eventprovider"></a><span data-ttu-id="dede0-108">EventProvider の破棄</span><span class="sxs-lookup"><span data-stu-id="dede0-108">Disposing EventProvider</span></span>  
 <span data-ttu-id="dede0-109">このサンプルでは、<xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> を実装した <xref:System.IDisposable?displayProperty=nameWithType> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="dede0-109">This sample uses the <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> class, which implements <xref:System.IDisposable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dede0-110">WCF サービスのトレースを実装するときに使用できる可能性がありますが、<xref:System.Diagnostics.Eventing.EventProvider>のサービスの有効期間にわたってリソース。</span><span class="sxs-lookup"><span data-stu-id="dede0-110">When implementing tracing for a WCF service, it is likely that you may use the <xref:System.Diagnostics.Eventing.EventProvider>’s resources for the lifetime of the service.</span></span> <span data-ttu-id="dede0-111">そのため、読みやすくするためにも、このサンプルでは、ラップされた <xref:System.Diagnostics.Eventing.EventProvider> を破棄しません。</span><span class="sxs-lookup"><span data-stu-id="dede0-111">For this reason, and for readability, this sample never disposes of the wrapped <xref:System.Diagnostics.Eventing.EventProvider>.</span></span> <span data-ttu-id="dede0-112">何かの理由で、サービスに対して別のトレースの要件を設定し、このリソースを破棄しなければならない場合は、アンマネージ リソースの破棄に関するベスト プラクティスに従ってこのサンプルを変更してください。</span><span class="sxs-lookup"><span data-stu-id="dede0-112">If for some reason your service has different requirements for tracing and you must dispose of this resource, then you should modify this sample in accordance with the best practices for disposing of unmanaged resources.</span></span> <span data-ttu-id="dede0-113">アンマネージ リソースを破棄に関する詳細については、次を参照してください。 [Dispose メソッドの実装](https://go.microsoft.com/fwlink/?LinkId=166436)します。</span><span class="sxs-lookup"><span data-stu-id="dede0-113">For more information about disposing unmanaged resources, see [Implementing a Dispose Method](https://go.microsoft.com/fwlink/?LinkId=166436).</span></span>  
  
## <a name="self-hosting-vs-web-hosting"></a><span data-ttu-id="dede0-114">自己ホスト型と Web ホスト</span><span class="sxs-lookup"><span data-stu-id="dede0-114">Self-Hosting vs. Web Hosting</span></span>  
 <span data-ttu-id="dede0-115">Web ホスト サービスでは、WCF の分析トレースは、"HostReference"は、サービスは、トレースの出力を識別するために使用をという名前のフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="dede0-115">For Web-hosted services, WCF’s analytic traces provide a field, called "HostReference", which is used to identify the service that is emitting the traces.</span></span> <span data-ttu-id="dede0-116">拡張可能なユーザー トレースをこのモデルに加えることができます。このサンプルで、そのためのベスト プラクティスを示します。</span><span class="sxs-lookup"><span data-stu-id="dede0-116">The extensible user traces can participate in this model and this sample demonstrates best practices for doing so.</span></span> <span data-ttu-id="dede0-117">Web ホストの形式を参照場合に、パイプ '&#124;' 文字が実際には、最終的な表示文字列は、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dede0-117">The format of a Web host reference when the pipe ‘&#124;’ character actually appears in the resulting string can be any one of the following:</span></span>  
  
-   <span data-ttu-id="dede0-118">アプリケーションがルート以外にある場合</span><span class="sxs-lookup"><span data-stu-id="dede0-118">If the application is not at the root.</span></span>  
  
     <span data-ttu-id="dede0-119">\<サイト名 >\<ApplicationVirtualPath >&#124;\<ServiceVirtualPath >&#124;\<ServiceName ></span><span class="sxs-lookup"><span data-stu-id="dede0-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
-   <span data-ttu-id="dede0-120">アプリケーションがルートにある場合</span><span class="sxs-lookup"><span data-stu-id="dede0-120">If the application is at the root.</span></span>  
  
     <span data-ttu-id="dede0-121">\<サイト名 >&#124;\<ServiceVirtualPath >&#124;\<ServiceName ></span><span class="sxs-lookup"><span data-stu-id="dede0-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
 <span data-ttu-id="dede0-122">自己ホスト型サービスは、WCF の分析トレースで"HostReference"フィールドは設定されません。</span><span class="sxs-lookup"><span data-stu-id="dede0-122">For self-hosted services, WCF’s analytic traces do not populate the "HostReference" field.</span></span> <span data-ttu-id="dede0-123">このサンプルの `WCFUserEventProvider` クラスは、自己ホスト型サービスで使用した場合も同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="dede0-123">The `WCFUserEventProvider` class in this sample behaves consistently when used by a self-hosted service.</span></span>  
  
## <a name="custom-event-details"></a><span data-ttu-id="dede0-124">カスタム イベントの詳細</span><span class="sxs-lookup"><span data-stu-id="dede0-124">Custom Event Details</span></span>  
 <span data-ttu-id="dede0-125">WCF の ETW イベント プロバイダー マニフェストでは、サービス コード内から WCF サービスの作成者によって生成されるように設計された 3 つのイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="dede0-125">WCF’s ETW Event Provider manifest defines three events that are designed to be emitted by WCF service authors from within service code.</span></span> <span data-ttu-id="dede0-126">次の表に、その 3 つのイベントの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="dede0-126">The following table shows a breakdown of the three events.</span></span>  
  
|<span data-ttu-id="dede0-127">event</span><span class="sxs-lookup"><span data-stu-id="dede0-127">Event</span></span>|<span data-ttu-id="dede0-128">説明</span><span class="sxs-lookup"><span data-stu-id="dede0-128">Description</span></span>|<span data-ttu-id="dede0-129">イベント ID</span><span class="sxs-lookup"><span data-stu-id="dede0-129">Event ID</span></span>|  
|-----------|-----------------|--------------|  
|<span data-ttu-id="dede0-130">UserDefinedInformationEventOccurred</span><span class="sxs-lookup"><span data-stu-id="dede0-130">UserDefinedInformationEventOccurred</span></span>|<span data-ttu-id="dede0-131">このイベントは、問題以外の通知すべき処理がサービスで発生した場合に生成します。</span><span class="sxs-lookup"><span data-stu-id="dede0-131">Emit this event when something of note happens in your service that is not a problem.</span></span> <span data-ttu-id="dede0-132">たとえば、データベースの呼び出しに成功した後にイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="dede0-132">For example, you might emit an event after successfully making a call to a database.</span></span>|<span data-ttu-id="dede0-133">301</span><span class="sxs-lookup"><span data-stu-id="dede0-133">301</span></span>|  
|<span data-ttu-id="dede0-134">UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="dede0-134">UserDefinedWarningOccurred</span></span>|<span data-ttu-id="dede0-135">このイベントは、後続の処理でエラーになる可能性がある問題が発生した場合に生成します。</span><span class="sxs-lookup"><span data-stu-id="dede0-135">Emit this event when a problem occurs that may result in a failure in the future.</span></span> <span data-ttu-id="dede0-136">たとえば、データベースの呼び出しが失敗したものの、冗長なデータ ストアを使用して回復できた場合に警告イベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="dede0-136">For example, you may emit a warning event when a call to a database fails but you were able to recover by falling back to a redundant data store.</span></span>|<span data-ttu-id="dede0-137">302</span><span class="sxs-lookup"><span data-stu-id="dede0-137">302</span></span>|  
|<span data-ttu-id="dede0-138">UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="dede0-138">UserDefinedErrorOccurred</span></span>|<span data-ttu-id="dede0-139">このイベントは、サービスが想定どおりに動作しなかった場合に生成します。</span><span class="sxs-lookup"><span data-stu-id="dede0-139">Emit this event when your service fails to behave as expected.</span></span> <span data-ttu-id="dede0-140">たとえば、データベースの呼び出しが失敗し、別の場所からもデータを取得できなかった場合にイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="dede0-140">For example, you might emit an event if a call to a database fails and you could not retrieve the data from elsewhere.</span></span>|<span data-ttu-id="dede0-141">303</span><span class="sxs-lookup"><span data-stu-id="dede0-141">303</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="dede0-142">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="dede0-142">To use this sample</span></span>  
  
1.  <span data-ttu-id="dede0-143">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] を使用して、WCFAnalyticTracingExtensibility.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dede0-143">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the WCFAnalyticTracingExtensibility.sln solution file.</span></span>  
  
2.  <span data-ttu-id="dede0-144">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="dede0-144">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="dede0-145">ソリューションを実行するには、Ctrl キーを押しながら F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="dede0-145">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="dede0-146">Web ブラウザーで次のようにクリックします。 **[calculator.svc]** します。</span><span class="sxs-lookup"><span data-stu-id="dede0-146">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="dede0-147">サービスの WSDL ドキュメントの URI がブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dede0-147">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="dede0-148">その URI をコピーします。</span><span class="sxs-lookup"><span data-stu-id="dede0-148">Copy that URI.</span></span>  
  
4.  <span data-ttu-id="dede0-149">WCF テスト クライアント (WcfTestClient.exe) を実行します。</span><span class="sxs-lookup"><span data-stu-id="dede0-149">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="dede0-150">WCF テスト クライアント (WcfTestClient.exe) にある、 \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir > \Common7\IDE\ WcfTestClient.exe (既定[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]インストール ディレクトリは C:\Program files \microsoft Visual Studio 10.0)。</span><span class="sxs-lookup"><span data-stu-id="dede0-150">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="dede0-151">選択して、サービスを追加、WCF テスト クライアント内で**ファイル**、し**サービスの追加**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-151">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="dede0-152">入力ボックスにエンドポイントのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="dede0-152">Add the endpoint address in the input box.</span></span>  
  
6.  <span data-ttu-id="dede0-153">クリックして**OK**ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dede0-153">Click **OK** to close the dialog.</span></span>  
  
     <span data-ttu-id="dede0-154">下の左ペインで、ICalculator サービスが追加された**マイ サービス プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-154">The ICalculator service is added in the left pane under **My Service Projects**.</span></span>  
  
7.  <span data-ttu-id="dede0-155">イベント ビューアー アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="dede0-155">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="dede0-156">サービスを呼び出す前に、イベント ビューアーを起動し、WCF サービスから生成された追跡イベントのイベント ログがリッスンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dede0-156">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
8.  <span data-ttu-id="dede0-157">**開始**メニューの **管理ツール**、し**イベント ビューアー**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-157">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span> <span data-ttu-id="dede0-158">有効にする、**分析**と**デバッグ**ログ。</span><span class="sxs-lookup"><span data-stu-id="dede0-158">Enable the **Analytic** and **Debug** logs.</span></span>  
  
9. <span data-ttu-id="dede0-159">イベント ビューアーのツリー ビューでに移動します**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、し、。**アプリケーション サーバー-アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-159">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="dede0-160">右クリックして**アプリケーション サーバー-アプリケーション**を選択します**ビュー**、し**分析およびデバッグ ログ**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-160">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="dede0-161">いることを確認、 **分析およびデバッグ ログ**オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="dede0-161">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span> <span data-ttu-id="dede0-162">有効にする、**分析**ログ。</span><span class="sxs-lookup"><span data-stu-id="dede0-162">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="dede0-163">イベント ビューアーのツリー ビューでに移動します**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、 。**アプリケーション サーバー-アプリケーション**、し**分析**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-163">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="dede0-164">右クリック**分析**選択**ログの有効化**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-164">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="dede0-165">WCF テスト クライアントを使用してサービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="dede0-165">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="dede0-166">WCF テスト クライアントでのダブルクリック**Add()** ICalculator サービス ノードの下。</span><span class="sxs-lookup"><span data-stu-id="dede0-166">In the WCF Test Client, double-click **Add()** under the ICalculator service node.</span></span>  
  
         <span data-ttu-id="dede0-167">**Add()** メソッドが 2 つのパラメーターと共に右ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dede0-167">The **Add()** method appears in the right pane with two parameters.</span></span>  
  
    2.  <span data-ttu-id="dede0-168">最初のパラメーターに「2」と入力し、2 番目のパラメーターに「3」と入力します。</span><span class="sxs-lookup"><span data-stu-id="dede0-168">Type in 2 for the first parameter and 3 for the second parameter.</span></span>  
  
    3.  <span data-ttu-id="dede0-169">クリックして**Invoke**メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dede0-169">Click **Invoke** to invoke the method.</span></span>  
  
11. <span data-ttu-id="dede0-170">移動して、**イベント ビューアー**既に開いているウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="dede0-170">Go to the **Event Viewer** window that you have already opened.</span></span> <span data-ttu-id="dede0-171">移動します**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、**アプリケーションサーバー-アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-171">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span>  
  
12. <span data-ttu-id="dede0-172">右クリックし、**分析**ノード**更新**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-172">Right-click the **Analytic** node and select **Refresh**.</span></span>  
  
     <span data-ttu-id="dede0-173">右ペインにイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dede0-173">The events appear in the right pane.</span></span>  
  
13. <span data-ttu-id="dede0-174">ID が 303 のイベントを探してダブルクリックして開き、内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="dede0-174">Locate the event with the ID of 303 and double-click it to open it up and inspect its contents.</span></span>  
  
     <span data-ttu-id="dede0-175">このイベントはによって作成された、 `Add()` ICalculator サービスのメソッドと等しく、ペイロードは"2 + 3 = 5"。</span><span class="sxs-lookup"><span data-stu-id="dede0-175">This event was emitted by the `Add()` method of the ICalculator service and has a payload equal to "2+3=5".</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="dede0-176">クリーンアップするには (省略可能)</span><span class="sxs-lookup"><span data-stu-id="dede0-176">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="dede0-177">開いている**イベント ビューアー**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-177">Open **Event Viewer**.</span></span>  
  
2.  <span data-ttu-id="dede0-178">移動します**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、し**アプリケーション サーバー-アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-178">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="dede0-179">右クリック**分析**選択**ログの無効化**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-179">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="dede0-180">移動します**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、 **アプリケーション サーバー-アプリケーション**、し**分析**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-180">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application-Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="dede0-181">右クリック**分析**選択**ログの消去**します。</span><span class="sxs-lookup"><span data-stu-id="dede0-181">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="dede0-182">クリックして**オフ**イベントを消去します。</span><span class="sxs-lookup"><span data-stu-id="dede0-182">Click **Clear** to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="dede0-183">既知の問題</span><span class="sxs-lookup"><span data-stu-id="dede0-183">Known Issue</span></span>  
 <span data-ttu-id="dede0-184">既知の問題がある、**イベント ビューアー** ETW イベントのデコードに失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dede0-184">There is a known issue in the **Event Viewer** where it may fail to decode ETW events.</span></span> <span data-ttu-id="dede0-185">示すエラー メッセージが表示する場合があります:"のイベント ID の説明\<id > ソースから Microsoft Windows のアプリケーション サーバー-アプリケーションが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="dede0-185">You may see an error message that says: "The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="dede0-186">このイベントを発生させるコンポーネントがローカル コンピューターにインストールされていないか、インストールが破損しています。</span><span class="sxs-lookup"><span data-stu-id="dede0-186">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="dede0-187">インストールしたり、ローカル コンピューターのコンポーネントを修復できます。"</span><span class="sxs-lookup"><span data-stu-id="dede0-187">You can install or repair the component on the local computer."</span></span> <span data-ttu-id="dede0-188">このエラーが発生した場合は、選択**更新**から、**アクション**メニュー。</span><span class="sxs-lookup"><span data-stu-id="dede0-188">If you encounter this error, select **Refresh** from the **Actions** menu.</span></span> <span data-ttu-id="dede0-189">これにより、イベントが正常にデコードされます。</span><span class="sxs-lookup"><span data-stu-id="dede0-189">The event should then decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dede0-190">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="dede0-190">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dede0-191">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dede0-191">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dede0-192">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="dede0-192">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dede0-193">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="dede0-193">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a><span data-ttu-id="dede0-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="dede0-194">See Also</span></span>  
 [<span data-ttu-id="dede0-195">AppFabric の監視のサンプル</span><span class="sxs-lookup"><span data-stu-id="dede0-195">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
