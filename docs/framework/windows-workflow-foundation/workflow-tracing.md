---
title: ワークフロー トレース
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: 27e56933043c9eb955500cdd1c5bbd06cb33bde8
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591250"
---
# <a name="workflow-tracing"></a><span data-ttu-id="09e23-102">ワークフロー トレース</span><span class="sxs-lookup"><span data-stu-id="09e23-102">Workflow Tracing</span></span>
<span data-ttu-id="09e23-103">ワークフロー トレースでは、.NET Framework のトレース リスナーを使用して診断情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="09e23-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="09e23-104">トレースは、アプリケーションで問題が検出された場合に有効にし、その問題が解決されたら、再度無効にすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="09e23-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="09e23-105">ワークフローのデバッグ トレースを有効にする方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="09e23-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="09e23-106">また、イベント トレース ビューアーを使用してトレースを構成したり、<xref:System.Diagnostics> を使用してトレース イベントをファイルに送信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="09e23-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="09e23-107">ETW でのデバッグ トレースの有効化</span><span class="sxs-lookup"><span data-stu-id="09e23-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="09e23-108">ETW を使用してトレースを有効化するには、次の手順に従ってイベント ビューアーでデバッグ チャネルを有効化します。</span><span class="sxs-lookup"><span data-stu-id="09e23-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1.  <span data-ttu-id="09e23-109">イベント ビューアーで分析ログおよびデバッグ ログのノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="09e23-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2.  <span data-ttu-id="09e23-110">イベント ビューアーのツリー ビューでに移動します。\*\*イベント ビューアーは アプリケーションとサービス ログ Microsoft-> -> Windows アプリケーション サーバー-アプリケーション-> \*\*します。</span><span class="sxs-lookup"><span data-stu-id="09e23-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="09e23-111">右クリック**アプリケーション サーバー-アプリケーション**選択\*\*ビューでは、分析およびデバッグ ログ-> \*\*します。</span><span class="sxs-lookup"><span data-stu-id="09e23-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="09e23-112">右クリック**デバッグ**選択**ログの有効化**します。</span><span class="sxs-lookup"><span data-stu-id="09e23-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3.  <span data-ttu-id="09e23-113">ワークフローがデバッグを実行し、トレースが ETW デバッグ チャネルに出力されると、トレースをイベント ビューアーで参照できます。</span><span class="sxs-lookup"><span data-stu-id="09e23-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="09e23-114">移動します\*\*イベント ビューアーは アプリケーションとサービス ログ Microsoft->-> Windows アプリケーション サーバー-アプリケーション-> \*\*します。</span><span class="sxs-lookup"><span data-stu-id="09e23-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="09e23-115">右クリック**デバッグ**選択**更新**します。</span><span class="sxs-lookup"><span data-stu-id="09e23-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4.  <span data-ttu-id="09e23-116">既定の分析トレースのバッファー サイズは 4 KB ですが、このサイズを 32 KB に増やすことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09e23-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="09e23-117">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="09e23-117">To do this, perform the following steps.</span></span>  
  
    1.  <span data-ttu-id="09e23-118">現在のフレームワークのディレクトリ (C:\Windows\Microsoft.NET\Framework\v4.0.21203 など) で、次のコマンドを実行します。`wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="09e23-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
    2.  <span data-ttu-id="09e23-119">変更、 \<bufferSize > 32 Windows.ApplicationServer.Applications.man ファイルの値。</span><span class="sxs-lookup"><span data-stu-id="09e23-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  <span data-ttu-id="09e23-120">現在のフレームワークのディレクトリ (C:\Windows\Microsoft.NET\Framework\v4.0.21203 など) で、次のコマンドを実行します。`wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="09e23-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09e23-121">.NET Framework 4 Client Profile を使用している場合は、.NET Framework 4 ディレクトリから、次のコマンドを実行して ETW マニフェストをまず登録する必要があります。 `ServiceModelReg.exe –i –c:etw`</span><span class="sxs-lookup"><span data-stu-id="09e23-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory: `ServiceModelReg.exe –i –c:etw`</span></span>  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="09e23-122">System.Diagnostics によるデバッグ トレースの有効化</span><span class="sxs-lookup"><span data-stu-id="09e23-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="09e23-123">これらのリスナーは、ワークフロー アプリケーションの App.config ファイルまたはワークフロー サービスの Web.config ファイルで構成します。</span><span class="sxs-lookup"><span data-stu-id="09e23-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="09e23-124">この例で、 [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424)トレース情報を現在のディレクトリにある MyTraceLog.txt ファイルに保存するように構成します。</span><span class="sxs-lookup"><span data-stu-id="09e23-124">In this example, a [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424) is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="09e23-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="09e23-125">See Also</span></span>  
 [<span data-ttu-id="09e23-126">Windows Server App Fabric の監視</span><span class="sxs-lookup"><span data-stu-id="09e23-126">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="09e23-127">App Fabric でアプリケーションの監視</span><span class="sxs-lookup"><span data-stu-id="09e23-127">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
