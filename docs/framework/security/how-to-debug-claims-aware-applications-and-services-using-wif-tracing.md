---
title: '方法: WIF トレースを使用してクレーム対応アプリケーションおよびサービスをデバッグする'
ms.date: 03/30/2017
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
author: BrucePerlerMS
ms.openlocfilehash: 43fa859aa84189817dffe74ecd72253ab9b82585
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321550"
---
# <a name="how-to-debug-claims-aware-applications-and-services-using-wif-tracing"></a><span data-ttu-id="e2884-102">方法: WIF トレースを使用してクレーム対応アプリケーションおよびサービスをデバッグする</span><span class="sxs-lookup"><span data-stu-id="e2884-102">How To: Debug Claims-Aware Applications And Services Using WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="e2884-103">対象</span><span class="sxs-lookup"><span data-stu-id="e2884-103">Applies To</span></span>  
  
-   <span data-ttu-id="e2884-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="e2884-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="e2884-105">サービス トレース ビューアー ツール (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="e2884-105">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>  
  
-   <span data-ttu-id="e2884-106">WIF アプリケーションのトラブルシューティングとデバッグ</span><span class="sxs-lookup"><span data-stu-id="e2884-106">Troubleshooting and Debugging WIF Applications</span></span>  
  
## <a name="summary"></a><span data-ttu-id="e2884-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="e2884-107">Summary</span></span>  
 <span data-ttu-id="e2884-108">この方法では、WIF トレースの構成方法、トレース ログの収集方法、およびトレース ビューアー ツールを使用してトレース ログを分析する方法について、必要な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="e2884-108">This How-To describes required steps for how to configure WIF tracing, collect trace logs, and how to analyze the trace logs using Trace Viewer tool.</span></span> <span data-ttu-id="e2884-109">WIF に関連する問題をトラブルシューティングするために、必要なアクションに対してトレース エントリの全般的なマッピングを行います。</span><span class="sxs-lookup"><span data-stu-id="e2884-109">It provides general mapping for trace entries to actions needed to troubleshoot issues related to WIF.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="e2884-110">目次</span><span class="sxs-lookup"><span data-stu-id="e2884-110">Contents</span></span>  
  
-   <span data-ttu-id="e2884-111">目的</span><span class="sxs-lookup"><span data-stu-id="e2884-111">Objectives</span></span>  
  
-   <span data-ttu-id="e2884-112">手順の要約</span><span class="sxs-lookup"><span data-stu-id="e2884-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="e2884-113">手順 1 – Web.config 構成ファイルを使用して WIF のトレースを構成する</span><span class="sxs-lookup"><span data-stu-id="e2884-113">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="e2884-114">手順 2 – トレース ビューアー ツールを使用して WIF のトレース ファイルを分析する</span><span class="sxs-lookup"><span data-stu-id="e2884-114">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="e2884-115">手順 3 – WIF 関連の問題を修復するための解決策を特定する</span><span class="sxs-lookup"><span data-stu-id="e2884-115">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
-   <span data-ttu-id="e2884-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2884-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="e2884-117">目的</span><span class="sxs-lookup"><span data-stu-id="e2884-117">Objectives</span></span>  
  
-   <span data-ttu-id="e2884-118">WIF トレースを構成する。</span><span class="sxs-lookup"><span data-stu-id="e2884-118">Configure WIF tracing.</span></span>  
  
-   <span data-ttu-id="e2884-119">トレース ビューアー ツールでトレース ログを表示する。</span><span class="sxs-lookup"><span data-stu-id="e2884-119">View trace logs in the Trace Viewer tool.</span></span>  
  
-   <span data-ttu-id="e2884-120">トレース ログで WIF 関連の問題を特定する。</span><span class="sxs-lookup"><span data-stu-id="e2884-120">Identify WIF related issues in the trace logs.</span></span>  
  
-   <span data-ttu-id="e2884-121">トレース ログで検出された WIF 関連の問題に修正措置を適用する。</span><span class="sxs-lookup"><span data-stu-id="e2884-121">Apply corrective actions to WIF related issues found in the trace logs.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="e2884-122">手順の要約</span><span class="sxs-lookup"><span data-stu-id="e2884-122">Summary of Steps</span></span>  
  
-   <span data-ttu-id="e2884-123">手順 1 – Web.config 構成ファイルを使用して WIF のトレースを構成する</span><span class="sxs-lookup"><span data-stu-id="e2884-123">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="e2884-124">手順 2 – トレース ビューアー ツールを使用して WIF のトレース ファイルを分析する</span><span class="sxs-lookup"><span data-stu-id="e2884-124">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="e2884-125">手順 3 – WIF 関連の問題を修復するための解決策を特定する</span><span class="sxs-lookup"><span data-stu-id="e2884-125">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
## <a name="step-1--configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="e2884-126">手順 1 – Web.config 構成ファイルを使用して WIF のトレースを構成する</span><span class="sxs-lookup"><span data-stu-id="e2884-126">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
 <span data-ttu-id="e2884-127">この手順では、*Web.config* ファイルの構成セクションに変更を加えて、WIF がイベントをトレースしてトレース ログに格納できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e2884-127">In this step, you will add changes to configuration sections in the *Web.config* file that enable WIF to trace its events and store them in a trace log.</span></span>  
  
#### <a name="to-configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="e2884-128">Web.config 構成ファイルを使用して WIF のトレースを構成するには</span><span class="sxs-lookup"><span data-stu-id="e2884-128">To configure WIF tracing using Web.config configuration file</span></span>  
  
1. <span data-ttu-id="e2884-129">**ソリューション エクスプローラー**で、Visual Studio エディターのルートの **Web.config** または **App.config** 構成ファイルをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="e2884-129">Open the root **Web.config** or **App.config** configuration file in the Visual Studio editor by double clicking on it in **Solution Explorer**.</span></span> <span data-ttu-id="e2884-130">ソリューションに **Web.config** または **App.config** 構成ファイルがない場合は、**ソリューション エクスプローラー**でソリューションを右クリックし、**[追加]**、**[新しい項目...]** の順にクリックして追加します。</span><span class="sxs-lookup"><span data-stu-id="e2884-130">If your solution does not have **Web.config** or **App.config** configuration file, add it by right clicking on the solution in the **Solution Explorer** and clicking **Add**, then clicking **New Item…**.</span></span> <span data-ttu-id="e2884-131">**[新しい項目]** ダイアログ ボックスで、リストから **[アプリケーション構成ファイル]** (**App.config** の場合) または **[Web 構成ファイル]** (**Web.config** の場合) を選択して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2884-131">On the **New Item** dialog, Select **Application Configuration File** for **App.config** or **Web Configuration File** for **Web.config** from the list and click **OK**.</span></span>  
  
2. <span data-ttu-id="e2884-132">構成ファイルの最後にある **\<configuration>** ノード内に、以下のような構成エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="e2884-132">Add the configuration entries similar to the following to the configuration file inside **\<configuration>** node at the end of the configuration file:</span></span>  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3. <span data-ttu-id="e2884-133">上記の構成は、詳細トレース イベントを生成し、*WIFTrace.e2e* ファイルにログを記録するよう WIF に指示します。</span><span class="sxs-lookup"><span data-stu-id="e2884-133">The above configuration instructs WIF to generate verbose trace events and log them into *WIFTrace.e2e* file.</span></span> <span data-ttu-id="e2884-134">値の完全な一覧については、 **switchValue**スイッチ、次のトピックで、トレース レベルの表を参照してください。[トレースの構成](../wcf/diagnostics/tracing/configuring-tracing.md)します。</span><span class="sxs-lookup"><span data-stu-id="e2884-134">For a complete list of values for the **switchValue** switch, refer to the Trace Level table found in the following topic: [Configuring Tracing](../wcf/diagnostics/tracing/configuring-tracing.md).</span></span>  
  
## <a name="step-2--analyze-wif-trace-files-using-trace-viewer-tool"></a><span data-ttu-id="e2884-135">手順 2 – トレース ビューアー ツールを使用して WIF のトレース ファイルを分析する</span><span class="sxs-lookup"><span data-stu-id="e2884-135">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
 <span data-ttu-id="e2884-136">このステップでは、トレース ビューアー ツール (SvcTraceViewer.exe) を使用して WIF のトレース ログを分析します。</span><span class="sxs-lookup"><span data-stu-id="e2884-136">In this step, you will use the Trace Viewer Tool (SvcTraceViewer.exe) to analyze WIF trace logs.</span></span>  
  
#### <a name="to-analyze-wif-trace-logs-using-trace-viewer-tool-svctraceviewerexe"></a><span data-ttu-id="e2884-137">トレース ビューアー ツール (SvcTraceViewer.exe) を使用して WIF のトレース ログを分析するには</span><span class="sxs-lookup"><span data-stu-id="e2884-137">To analyze WIF trace logs using Trace Viewer tool (SvcTraceViewer.exe)</span></span>  
  
1. <span data-ttu-id="e2884-138">トレース ビューアー ツール (SvcTraceViewer.exe) は、Windows SDK の一部として同梱されています。</span><span class="sxs-lookup"><span data-stu-id="e2884-138">Trace Viewer tool (SvcTraceViewer.exe) ships as part of the Windows SDK.</span></span> <span data-ttu-id="e2884-139">既に Windows SDK をインストールしていない場合は、ここでダウンロードできます。[Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279)します。</span><span class="sxs-lookup"><span data-stu-id="e2884-139">If you haven’t already installed the Windows SDK, you can download it here: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span></span>  
  
2. <span data-ttu-id="e2884-140">トレース ビューアー ツール (SvcTraceViewer.exe) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2884-140">Run the Trace Viewer tool (SvcTraceViewer.exe).</span></span> <span data-ttu-id="e2884-141">通常、これはインストール パスの **Bin** フォルダーから使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2884-141">It is typically available in the **Bin** folder of the installation path.</span></span>  
  
3. <span data-ttu-id="e2884-142">たとえば、WIF トレースのログ ファイル WIFTrace.e2e を開きます。その場合、メニューで **[ファイル]**、**[開く...]** </span><span class="sxs-lookup"><span data-stu-id="e2884-142">Open the WIF trace log file, for example, WIFTrace.e2e by selecting **File**, **Open…**</span></span> <span data-ttu-id="e2884-143">オプションの順に選択するか、**Ctrl + O** ショートカット キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2884-143">option in the menu or using the **Ctrl+O** shortcut.</span></span> <span data-ttu-id="e2884-144">トレース ビューアー ツールでトレース ログ ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="e2884-144">The trace log file opens in the Trace Viewer tool.</span></span>  
  
4. <span data-ttu-id="e2884-145">**[アクティビティ]** タブでエントリを確認します。各エントリには、アクティビティの数、ログに記録されたトレースの数、アクティビティの期間および開始と終了のタイムスタンプが含まれているはずです。</span><span class="sxs-lookup"><span data-stu-id="e2884-145">Review entries in the **Activity** tab. Each entry should contain an activity number, the number of traces that were logged, duration of the activity and its start and end timestamps.</span></span>  
  
5. <span data-ttu-id="e2884-146">**[アクティビティ]** タブをクリックします。ツールのメイン領域に詳細なトレース エントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2884-146">Click on the **Activity** tab. You should see detailed trace entries in the main area of the tool.</span></span> <span data-ttu-id="e2884-147">使用して、**レベル**ドロップダウン リストで、メニューなどの特定のレベルのトレースをフィルター処理には。**すべて**、**警告**、**エラー**、**情報**など。</span><span class="sxs-lookup"><span data-stu-id="e2884-147">Use the **Level** dropdown list on the menu to filter specific level of traces, for example: **All**, **Warning**, **Errors**, **Information**, etc.</span></span>  
  
6. <span data-ttu-id="e2884-148">特定のトレース エントリをクリックすると、ツールの下部の領域で詳細をレビューできます。</span><span class="sxs-lookup"><span data-stu-id="e2884-148">Click on specific trace entries to review the details in the lower area of the tool.</span></span> <span data-ttu-id="e2884-149">詳細は、対応するタブを選択することで、**書式付き**および **XML** ビューで表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e2884-149">The details can be viewed using **Formatted** and **XML** view by choosing corresponding tabs.</span></span>  
  
## <a name="step-3--identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="e2884-150">手順 3 – WIF 関連の問題を修復するための解決策を特定する</span><span class="sxs-lookup"><span data-stu-id="e2884-150">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
 <span data-ttu-id="e2884-151">この手順では、WIF のトレース ログとトレース ビューアー ツールを使用して、WIF に関連する問題の解決方法を特定できます。</span><span class="sxs-lookup"><span data-stu-id="e2884-151">In this step, you can identify solutions for WIF-related issues identified by using the WIF trace log and Trace Viewer tool.</span></span> <span data-ttu-id="e2884-152">WIF 関連の例外と、問題をトラブルシューティングするための可能性のある解決策や必要な操作との全般的なマッピングを概説しています。</span><span class="sxs-lookup"><span data-stu-id="e2884-152">It outlines general mapping of WIF related exceptions to potential solutions or required actions to troubleshoot the issue.</span></span>  
  
#### <a name="to-identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="e2884-153">WIF 関連の問題を修復するための解決策を特定するには</span><span class="sxs-lookup"><span data-stu-id="e2884-153">To identify solutions to fix WIF related issues</span></span>  
  
1. <span data-ttu-id="e2884-154">WIF の例外と問題を修正するために必要な操作に関する次の表を確認します。</span><span class="sxs-lookup"><span data-stu-id="e2884-154">Review the following table of WIF exceptions and the required actions to correct the issues.</span></span>  
  
|**<span data-ttu-id="e2884-155">エラー ID</span><span class="sxs-lookup"><span data-stu-id="e2884-155">Error ID</span></span>**|**<span data-ttu-id="e2884-156">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="e2884-156">Error Message</span></span>**|**<span data-ttu-id="e2884-157">エラーを修復するために必要な操作</span><span class="sxs-lookup"><span data-stu-id="e2884-157">Action needed to fix the error</span></span>**|  
|-|-|-|  
|<span data-ttu-id="e2884-158">ID4175</span><span class="sxs-lookup"><span data-stu-id="e2884-158">ID4175</span></span>|<span data-ttu-id="e2884-159">セキュリティ トークンの発行者は、IssuerNameRegistry で認識されませんでした。</span><span class="sxs-lookup"><span data-stu-id="e2884-159">The issuer of the security token was not recognized by the IssuerNameRegistry.</span></span>  <span data-ttu-id="e2884-160">この発行者からのセキュリティ トークンを承認するには、この発行者の有効な名前を返すように IssuerNameRegistry を構成します。</span><span class="sxs-lookup"><span data-stu-id="e2884-160">To accept security tokens from this issuer, configure the IssuerNameRegistry to return a valid name for this issuer.</span></span>|<span data-ttu-id="e2884-161">このエラーは、MMC スナップインから拇印をコピーして、*Web.config* ファイルに貼り付けると発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2884-161">This error can be caused by copying a thumbprint from the MMC snap-in and pasting it into the *Web.config* file.</span></span> <span data-ttu-id="e2884-162">具体的には、[証明書のプロパティ] ウィンドウからコピーするときに、テキスト文字列内で余分な印刷できない文字を取得することがあります。</span><span class="sxs-lookup"><span data-stu-id="e2884-162">Specifically, you can get an extra non-printable character in the text string when copying from the certificate properties window.</span></span> <span data-ttu-id="e2884-163">この余分な文字により、拇印と失敗しますを。正しく拇印をコピーする手順をご覧[クレーム ベースのシングル サインオン-で、Web アプリケーションおよび Microsoft Azure 用](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29)します。</span><span class="sxs-lookup"><span data-stu-id="e2884-163">This extra character causes the thumbprint match to fail.The procedure for correctly copying the thumbprint can be found at [Claims-Based Single Sign-On for the Web and Microsoft Azure](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29).</span></span>|  
  
## <a name="related-items"></a><span data-ttu-id="e2884-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2884-164">Related Items</span></span>  
  
-   [<span data-ttu-id="e2884-165">サービス トレース ビューアーを使用した相関トレースの表示とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e2884-165">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
