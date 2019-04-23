---
title: 診断用の WMI (Windows Management Instrumentation) の使用
ms.date: 03/30/2017
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
ms.openlocfilehash: 9acb1b280248f8552680ea3fbba831b3de53b2c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308589"
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a><span data-ttu-id="367dd-102">診断用の WMI (Windows Management Instrumentation) の使用</span><span class="sxs-lookup"><span data-stu-id="367dd-102">Using Windows Management Instrumentation for Diagnostics</span></span>
<span data-ttu-id="367dd-103">Windows Communication Foundation (WCF) は、WCF Windows Management Instrumentation (WMI) プロバイダーを介して実行時のサービスの検査データを公開します。</span><span class="sxs-lookup"><span data-stu-id="367dd-103">Windows Communication Foundation (WCF) exposes inspection data of a service at runtime through a WCF Windows Management Instrumentation (WMI) provider.</span></span>  
  
## <a name="enabling-wmi"></a><span data-ttu-id="367dd-104">WMI の有効化</span><span class="sxs-lookup"><span data-stu-id="367dd-104">Enabling WMI</span></span>  
 <span data-ttu-id="367dd-105">WMI は、Web ベースのエンタープライズ管理 (WBEM) 標準をマイクロソフトが実装したものです。</span><span class="sxs-lookup"><span data-stu-id="367dd-105">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="367dd-106">WMI SDK の詳細については、次を参照してください。 [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page)します。</span><span class="sxs-lookup"><span data-stu-id="367dd-106">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="367dd-107">WBEM は、アプリケーションが Management Instrumentation を外部管理ツールに開示する業界標準の方法です。</span><span class="sxs-lookup"><span data-stu-id="367dd-107">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="367dd-108">WMI プロバイダーは、WBEM と互換性のあるインターフェイスを通して実行時にインストルメンテーションを公開するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="367dd-108">A WMI provider is a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="367dd-109">これは、属性と値のペアを持つ WMI オブジェクトのセットで構成されます。</span><span class="sxs-lookup"><span data-stu-id="367dd-109">It consists of a set of WMI objects that have attribute/value pairs.</span></span> <span data-ttu-id="367dd-110">ペアには多くの単純型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="367dd-110">Pairs can be of a number of simple types.</span></span> <span data-ttu-id="367dd-111">管理ツールは、実行時にインターフェイスを介してサービスに接続できます。</span><span class="sxs-lookup"><span data-stu-id="367dd-111">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="367dd-112">WCF では、アドレス、バインディング、動作、およびリスナーなどのサービスの属性を公開します。</span><span class="sxs-lookup"><span data-stu-id="367dd-112">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="367dd-113">組み込みの WMI プロバイダーは、アプリケーションの構成ファイルでアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="367dd-113">The built-in WMI provider can be activated in the configuration file of the application.</span></span> <span data-ttu-id="367dd-114">これを行う、`wmiProviderEnabled`の属性、 [\<診断 >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)で、 [ \<system.serviceModel >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)セクションで、次の例に示すように構成します。</span><span class="sxs-lookup"><span data-stu-id="367dd-114">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration.</span></span>  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 <span data-ttu-id="367dd-115">この構成エントリには、WMI インターフェイスが開示されます。</span><span class="sxs-lookup"><span data-stu-id="367dd-115">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="367dd-116">管理アプリケーションはこのインターフェイスを通して接続し、アプリケーションの Management Instrumentation にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="367dd-116">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="accessing-wmi-data"></a><span data-ttu-id="367dd-117">WMI データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="367dd-117">Accessing WMI Data</span></span>  
 <span data-ttu-id="367dd-118">WMI データには、複数の異なる方法でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="367dd-118">WMI data can be accessed in many different ways.</span></span> <span data-ttu-id="367dd-119">マイクロソフトでは、WMI Api を提供するスクリプト、Visual Basic アプリケーション、C++ アプリケーションでは、および[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="367dd-119">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="367dd-120">詳細については、次を参照してください。 [WMI を使用した](https://go.microsoft.com/fwlink/?LinkId=95183)します。</span><span class="sxs-lookup"><span data-stu-id="367dd-120">For more information, see [Using WMI](https://go.microsoft.com/fwlink/?LinkId=95183).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="367dd-121">.NET Framework 提供のメソッドを使用し、プログラムで WMI データにアクセスする場合、そのようなメソッドは接続確立時に例外をスローする場合があることを認識しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-121">If you use the .NET Framework provided methods to programmatically access WMI data, you should be aware that such methods may throw exceptions when the connection is established.</span></span> <span data-ttu-id="367dd-122">接続は、<xref:System.Management.ManagementObject> インスタンスの構築中に確立されませんが、実際のデータ交換が含まれた最初の要求時に確立されます。</span><span class="sxs-lookup"><span data-stu-id="367dd-122">The connection is not established during the construction of the <xref:System.Management.ManagementObject> instance, but on the first request involving actual data exchange.</span></span> <span data-ttu-id="367dd-123">したがって、`try..catch` ブロックを使用して例外をキャッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-123">Therefore, you should use a `try..catch` block to catch the possible exceptions.</span></span>  
  
 <span data-ttu-id="367dd-124">トレース レベルやメッセージ ログ レベルだけでなく、WMI の `System.ServiceModel` トレース ソースのメッセージ ログ オプションも変更できます。</span><span class="sxs-lookup"><span data-stu-id="367dd-124">You can change the trace and message logging level, as well as message logging options for the `System.ServiceModel` trace source in WMI.</span></span> <span data-ttu-id="367dd-125">これを行うへのアクセス、 [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md)インスタンスで、これらのブール型プロパティを公開します: `LogMessagesAtServiceLevel`、 `LogMessagesAtTransportLevel`、 `LogMalformedMessages`、および`TraceLevel`します。</span><span class="sxs-lookup"><span data-stu-id="367dd-125">This can be done by accessing the [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) instance, which exposes these Boolean properties: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, and `TraceLevel`.</span></span> <span data-ttu-id="367dd-126">そのため、メッセージ ログ用のトレース リスナーを構成していても、これらのオプションを構成で `false` に設定している場合は、後でアプリケーションを実行しているときに `true` に変更できます。</span><span class="sxs-lookup"><span data-stu-id="367dd-126">Therefore, if you configure a trace listener for message logging, but set these options to `false` in configuration, you can later change them to `true` when the application is running.</span></span> <span data-ttu-id="367dd-127">これで、メッセージ ログが実行時に有効になります。</span><span class="sxs-lookup"><span data-stu-id="367dd-127">This will effectively enable message logging at runtime.</span></span> <span data-ttu-id="367dd-128">同様に、構成ファイルでメッセージ ログを有効にしている場合は、実行時に WMI を使用して無効にできます。</span><span class="sxs-lookup"><span data-stu-id="367dd-128">Similarly, if you enable message logging in your configuration file, you can disable it at runtime using WMI.</span></span>  
  
 <span data-ttu-id="367dd-129">構成ファイルで、メッセージ ログのメッセージ ログ トレース リスナーまたはトレースの `System.ServiceModel` トレース リスナーが指定されていない場合、WMI が変更を受け入れても変更は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="367dd-129">You should be aware that if no message logging trace listeners for message logging, or no `System.ServiceModel` trace listeners for tracing are specified in the configuration file, none of your changes are taken into effect, even though the changes are accepted by WMI.</span></span> <span data-ttu-id="367dd-130">各リスナーを正しく設定の詳細については、次を参照してください。[メッセージ ログの構成](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)と[トレースの構成](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)します。</span><span class="sxs-lookup"><span data-stu-id="367dd-130">For more information on properly setting up the respective listeners, see [Configuring Message Logging](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) and [Configuring Tracing](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).</span></span> <span data-ttu-id="367dd-131">構成で設定された他のすべてのトレース ソースのトレース レベルは、アプリケーションが開始されると有効になり変更できません。</span><span class="sxs-lookup"><span data-stu-id="367dd-131">The trace level of all other trace sources specified by configuration is effective when the application starts, and cannot be changed.</span></span>  
  
 <span data-ttu-id="367dd-132">WCF の公開、`GetOperationCounterInstanceName`スクリプト メソッド。</span><span class="sxs-lookup"><span data-stu-id="367dd-132">WCF exposes a `GetOperationCounterInstanceName` method for scripting.</span></span> <span data-ttu-id="367dd-133">このメソッドに操作名を指定した場合、このメソッドはパフォーマンス カウンターのインスタンス名を返します。</span><span class="sxs-lookup"><span data-stu-id="367dd-133">This method returns a performance counter instance name if you provide it with an operation name.</span></span> <span data-ttu-id="367dd-134">ただし、このメソッドは入力を検証しません。</span><span class="sxs-lookup"><span data-stu-id="367dd-134">However, it does not validate your input.</span></span> <span data-ttu-id="367dd-135">したがって、正しくない操作名を指定した場合、正しくないカウンター名が返されます。</span><span class="sxs-lookup"><span data-stu-id="367dd-135">Therefore, if you provide an incorrect operation name, an incorrect counter name is returned.</span></span>  
  
 <span data-ttu-id="367dd-136">`OutgoingChannel`のプロパティ、`Service`インスタンス内で目的のサービスに WCF クライアントが作成されていない場合は、別のサービスに接続するためのサービスによって開かれたチャネルをカウントしません、`Service`メソッド。</span><span class="sxs-lookup"><span data-stu-id="367dd-136">The `OutgoingChannel` property of the `Service` instance does not count channels opened by a service to connect to another service, if the WCF client to the destination service is not created within the `Service` method.</span></span>  
  
 <span data-ttu-id="367dd-137">**注意**WMI のみをサポート、<xref:System.TimeSpan>最大 3 つの 10 進数のポイントの値します。</span><span class="sxs-lookup"><span data-stu-id="367dd-137">**Caution** WMI only supports a <xref:System.TimeSpan> value up to 3 decimal points.</span></span> <span data-ttu-id="367dd-138">たとえば、サービスでプロパティの 1 つを <xref:System.TimeSpan.MaxValue> に設定した場合、WMI ではその値を小数点以下 3 桁より下を切り捨て表示します。</span><span class="sxs-lookup"><span data-stu-id="367dd-138">For example, if your service sets one of its properties to <xref:System.TimeSpan.MaxValue>, its value is truncated after 3 decimal points when viewed through WMI.</span></span>  
  
## <a name="security"></a><span data-ttu-id="367dd-139">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="367dd-139">Security</span></span>  
 <span data-ttu-id="367dd-140">WCF WMI プロバイダーでは、環境でサービスの検出ができる、のでへのアクセスを許可するための十分な注意を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-140">Because the WCF WMI provider allows the discovery of services in an environment, you should exercise extreme caution for granting access to it.</span></span> <span data-ttu-id="367dd-141">既定の "管理者のみ" のアクセスを緩めた場合、信頼性の低いパーティに環境内の機密性のあるデータへのアクセスを許可する場合があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-141">If you relax the default administrator-only access, you may allow less-trusted parties access to sensitive data in your environment.</span></span> <span data-ttu-id="367dd-142">特にリモート WMI アクセスに対するアクセス許可を緩めた場合、大量の攻撃を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-142">Specifically, if you loosen permissions on remote WMI access, flooding attacks can occur.</span></span> <span data-ttu-id="367dd-143">過剰の WMI 要求により大量の処理が発生した場合、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-143">If a process is flooded by excessive WMI requests, its performance can be degraded.</span></span>  
  
 <span data-ttu-id="367dd-144">さらに、MOF ファイルに対するアクセス許可を緩めた場合、信頼性の低いパーティが WMI の動作を操作して WMI スキーマに読み込まれるオブジェクトを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="367dd-144">In addition, if you relax access permissions for the MOF file, less-trusted parties can manipulate the behavior of WMI and alter the objects that are loaded in the WMI schema.</span></span> <span data-ttu-id="367dd-145">たとえば、フィールドを削除して、重要データを管理者から隠したり、例外を設定しないかまたは例外の原因とならないフィールドを追加したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="367dd-145">For example, fields can be removed such that critical data is concealed from the administrator or that fields that do not populate or cause exceptions are added to the file.</span></span>  
  
 <span data-ttu-id="367dd-146">既定では、WCF WMI プロバイダー execute が付与されます"メソッド"、「プロバイダーによる書き込み」、および「アカウントの有効化」権限が管理者、および ASP.NET、Local Service、およびネットワーク サービスの「アカウントの有効化」権限。</span><span class="sxs-lookup"><span data-stu-id="367dd-146">By default, the WCF WMI provider grants "execute method", "provider write", and "enable account" permission for Administrator, and "enable account" permission for ASP.NET, Local Service and Network Service.</span></span> <span data-ttu-id="367dd-147">特に、[!INCLUDE[wv](../../../../../includes/wv-md.md)] 以外のプラットフォームでは、ASP.NET アカウントは WMI ServiceModel 名前空間に対して読み取りアクセスが可能です。</span><span class="sxs-lookup"><span data-stu-id="367dd-147">In particular, on non-[!INCLUDE[wv](../../../../../includes/wv-md.md)] platforms, the ASP.NET account has read access to the WMI ServiceModel namespace.</span></span> <span data-ttu-id="367dd-148">特定のユーザー グループに対してこれらの権限を付与したくない場合は、WMI プロバイダーを非アクティブにするか (既定では無効に設定されています)、特定のユーザー グループのアクセスを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-148">If you do not want to grant these privileges to a particular user group, you should either deactivate the WMI provider (it is disabled by default), or disable access for the specific user group.</span></span>  
  
 <span data-ttu-id="367dd-149">また、構成を使用して WMI を有効にする場合、ユーザー権限が不十分のため WMI が有効にならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-149">In addition, when you attempt to enable WMI through configuration, WMI may not be enabled due to insufficient user privilege.</span></span> <span data-ttu-id="367dd-150">ただし、このエラーを記録するイベントはイベント ログに書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="367dd-150">However, no event is written to the event log to record this failure.</span></span>  
  
 <span data-ttu-id="367dd-151">ユーザー権限のレベルを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="367dd-151">To modify user privilege levels, use the following steps.</span></span>  
  
1. <span data-ttu-id="367dd-152">[開始] をクリックしておよび実行し、入力**compmgmt.msc**します。</span><span class="sxs-lookup"><span data-stu-id="367dd-152">Click Start and then Run and type **compmgmt.msc**.</span></span>  
  
2. <span data-ttu-id="367dd-153">右クリックして**サービスとアプリケーション WMI コントロール**を選択する**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="367dd-153">Right-click **Services and Application/WMI Controls** to select **Properties**.</span></span>  
  
3. <span data-ttu-id="367dd-154">選択、**セキュリティ** タブに移動し、 **Root/servicemodel**名前空間。</span><span class="sxs-lookup"><span data-stu-id="367dd-154">Select the **Security** Tab, and navigate to the **Root/ServiceModel** namespace.</span></span> <span data-ttu-id="367dd-155">をクリックして、**セキュリティ**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="367dd-155">Click the **Security** button.</span></span>  
  
4. <span data-ttu-id="367dd-156">特定のグループまたはアクセスを制御し、使用するユーザーを選択、**許可**または**Deny**アクセス許可を構成するチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="367dd-156">Select the specific group or user that you want to control access and use the **Allow** or **Deny** checkbox to configure permissions.</span></span>  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a><span data-ttu-id="367dd-157">追加ユーザーへの WCF WMI 登録権限の付与</span><span class="sxs-lookup"><span data-stu-id="367dd-157">Granting WCF WMI Registration Permissions to Additional Users</span></span>  
 <span data-ttu-id="367dd-158">WCF は管理データを WMI に公開します。</span><span class="sxs-lookup"><span data-stu-id="367dd-158">WCF exposes management data to WMI.</span></span> <span data-ttu-id="367dd-159">これには、「分離プロバイダー」とも呼ばれる、インプロセス WMI プロバイダーをホストします。</span><span class="sxs-lookup"><span data-stu-id="367dd-159">It does so by hosting an in-process WMI provider, sometimes called a "decoupled provider".</span></span> <span data-ttu-id="367dd-160">管理データを公開するには、このプロバイダーを登録するアカウントに適切な権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="367dd-160">For the management data to be exposed, the account that registers this provider must have the appropriate permissions.</span></span> <span data-ttu-id="367dd-161">Windows では、権限を持つアカウントの少数のセットのみが、既定で分離プロバイダーを登録できます。</span><span class="sxs-lookup"><span data-stu-id="367dd-161">In Windows, only a small set of privileged accounts can register decoupled providers by default.</span></span> <span data-ttu-id="367dd-162">ユーザーは通常、既定のセットではないアカウントで実行している WCF サービスから WMI データを公開するので、これは問題です。</span><span class="sxs-lookup"><span data-stu-id="367dd-162">This is a problem because users commonly want to expose WMI data from a WCF service running under an account that is not in the default set.</span></span>  
  
 <span data-ttu-id="367dd-163">このアクセスを提供するために、管理者は、次の権限を追加のアカウントに次の順序で付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-163">To provide this access, an administrator must grant the following permissions to the additional account in the following order:</span></span>  
  
1. <span data-ttu-id="367dd-164">WCF WMI 名前空間へのアクセス権限</span><span class="sxs-lookup"><span data-stu-id="367dd-164">Permission to access to the WCF WMI Namespace.</span></span>  
  
2. <span data-ttu-id="367dd-165">WCF 分離 WMI プロバイダーの登録権限</span><span class="sxs-lookup"><span data-stu-id="367dd-165">Permission to register the WCF Decoupled WMI Provider.</span></span>  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a><span data-ttu-id="367dd-166">WMI 名前空間へのアクセス権限を付与するには</span><span class="sxs-lookup"><span data-stu-id="367dd-166">To grant WMI namespace access permission</span></span>  
  
1. <span data-ttu-id="367dd-167">次の PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="367dd-167">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting Access to root/servicemodel WMI namespace to built in users group"  
    write-host ""  
  
    # Create the binary representation of the permissions to grant in SDDL  
    $newPermissions = "O:BAG:BAD:P(A;CI;CCDCLCSWRPWPRCWD;;;BA)(A;CI;CC;;;NS)(A;CI;CC;;;LS)(A;CI;CC;;;BU)"  
    $converter = new-object system.management.ManagementClass Win32_SecurityDescriptorHelper  
    $binarySD = $converter.SDDLToBinarySD($newPermissions)  
    $convertedPermissions = ,$binarySD.BinarySD  
  
    # Get the object used to set the permissions  
    $security = gwmi -namespace root/servicemodel -class __SystemSecurity  
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "Previous ACL: "$outsddl.SDDL  
  
    # Change the Access Control List (ACL) using SDDL  
    $result = $security.PsBase.InvokeMethod("SetSD",$convertedPermissions)   
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "New ACL:      "$outsddl.SDDL  
    write-host ""  
    ```  
  
     <span data-ttu-id="367dd-168">この PowerShell スクリプトでは、組み込みのユーザー グループで、"root/servicemodel"WMI 名前空間へのアクセスを付与するのにセキュリティ記述子定義言語 (SDDL) を使用します。</span><span class="sxs-lookup"><span data-stu-id="367dd-168">This PowerShell script uses Security Descriptor Definition Language (SDDL) to grant the Built-In Users group access to the "root/servicemodel" WMI namespace.</span></span> <span data-ttu-id="367dd-169">次の ACL が指定されます。</span><span class="sxs-lookup"><span data-stu-id="367dd-169">It specifies the following ACLs:</span></span>  
  
    -   <span data-ttu-id="367dd-170">組み込みの管理者 (BA) – 既にアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="367dd-170">Built-In Administrator (BA) - Already Had Access.</span></span>  
  
    -   <span data-ttu-id="367dd-171">ネットワーク サービス (NS) - 既にアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="367dd-171">Network Service (NS) - Already Had Access.</span></span>  
  
    -   <span data-ttu-id="367dd-172">ローカル システム (LS) - 既にアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="367dd-172">Local System (LS) - Already Had Access.</span></span>  
  
    -   <span data-ttu-id="367dd-173">組み込みのユーザー – アクセス権を付与するグループ。</span><span class="sxs-lookup"><span data-stu-id="367dd-173">Built-In Users - The group to grant access to.</span></span>  
  
#### <a name="to-grant-provider-registration-access"></a><span data-ttu-id="367dd-174">プロバイダーに登録アクセス権を付与するには</span><span class="sxs-lookup"><span data-stu-id="367dd-174">To grant provider registration access</span></span>  
  
1. <span data-ttu-id="367dd-175">次の PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="367dd-175">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting WCF provider registration access to built in users group"  
    write-host ""  
    # Set security on ServiceModel provider  
    $provider = get-WmiObject -namespace "root\servicemodel" __Win32Provider  
  
    write-host "Previous ACL: "$provider.SecurityDescriptor  
    $result = $provider.SecurityDescriptor = "O:BUG:BUD:(A;;0x1;;;BA)(A;;0x1;;;NS)(A;;0x1;;;LS)(A;;0x1;;;BU)"  
  
    # Commit the changes and display it to the console  
    $result = $provider.Put()  
    write-host "New ACL:      "$provider.SecurityDescriptor  
    write-host ""  
    ```  
  
### <a name="granting-access-to-arbitrary-users-or-groups"></a><span data-ttu-id="367dd-176">任意のユーザーまたはグループへのアクセス権の付与</span><span class="sxs-lookup"><span data-stu-id="367dd-176">Granting Access to Arbitrary Users or Groups</span></span>  
 <span data-ttu-id="367dd-177">このセクションの例では、すべてのローカル ユーザーに WMI プロバイダー登録権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="367dd-177">The example in this section grants WMI Provider registration privileges to all local users.</span></span> <span data-ttu-id="367dd-178">組み込まれていないユーザーまたはグループにアクセス権を付与する場合は、そのユーザーまたはグループのセキュリティ識別子 (SID) を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-178">If you want to grant access to a user or group that is not built in, then you must obtain that user or group’s Security Identifier (SID).</span></span> <span data-ttu-id="367dd-179">任意のユーザーの SID を取得する簡単な方法はありません。</span><span class="sxs-lookup"><span data-stu-id="367dd-179">There is no simple way to get the SID for an arbitrary user.</span></span> <span data-ttu-id="367dd-180">1 つの方法としては、目的のユーザーとしてログオンし、次のシェル コマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="367dd-180">One method is to log on as the desired user and then issue the following shell command.</span></span>  
  
```  
Whoami /user  
```  
  
 <span data-ttu-id="367dd-181">これにより、現在のユーザーの SID が提供されますが、この方法を使用して任意のユーザーで SID を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="367dd-181">This provides the SID of the current user, but this method cannot be used to get the SID on any arbitrary user.</span></span> <span data-ttu-id="367dd-182">SID を取得するもう 1 つのメソッドは、使用する、 [getsid.exe](https://go.microsoft.com/fwlink/?LinkId=186467)ツールから、[管理タスク用の Windows 2000 リソース キット ツール](https://go.microsoft.com/fwlink/?LinkId=178660)します。</span><span class="sxs-lookup"><span data-stu-id="367dd-182">Another method to get the SID is to use the [getsid.exe](https://go.microsoft.com/fwlink/?LinkId=186467) tool from the [Windows 2000 Resource Kit Tools for administrative tasks](https://go.microsoft.com/fwlink/?LinkId=178660).</span></span> <span data-ttu-id="367dd-183">このツールは、2 人のユーザー (ローカルまたはドメイン) の SID を比較し、副作用として、2 つの SID をコマンド ラインに出力します。</span><span class="sxs-lookup"><span data-stu-id="367dd-183">This tool compares the SID of two users (local or domain), and as a side effect prints the two SIDs to the command line.</span></span> <span data-ttu-id="367dd-184">詳細については、次を参照してください。 [Well Known Sid](https://go.microsoft.com/fwlink/?LinkId=186468)します。</span><span class="sxs-lookup"><span data-stu-id="367dd-184">For more information, see [Well Known SIDs](https://go.microsoft.com/fwlink/?LinkId=186468).</span></span>  
  
## <a name="accessing-remote-wmi-object-instances"></a><span data-ttu-id="367dd-185">リモート WMI オブジェクトのインスタンスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="367dd-185">Accessing Remote WMI Object Instances</span></span>  
 <span data-ttu-id="367dd-186">リモート コンピューター上の WCF WMI インスタンスにアクセスする必要がある場合は、パケットのプライバシーへのアクセスに使用するツールを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="367dd-186">If you need to access WCF WMI instances on a remote machine, you must enable packet privacy on the tools that you use for access.</span></span> <span data-ttu-id="367dd-187">次のセクションでは、WMI CIM Studio、Windows Management Instrumentation テスト、および .NET SDK 2.0 を使用してこれらを実現する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="367dd-187">The following section describes how to achieve these using the WMI CIM Studio, Windows Management Instrumentation Tester, as well as .NET SDK 2.0.</span></span>  
  
### <a name="wmi-cim-studio"></a><span data-ttu-id="367dd-188">WMI CIM Studio</span><span class="sxs-lookup"><span data-stu-id="367dd-188">WMI CIM Studio</span></span>  
 <span data-ttu-id="367dd-189">インストールした場合[WMI Administrative Tools](https://go.microsoft.com/fwlink/?LinkId=95185)、WMI インスタンスのアクセスに、WMI CIM Studio を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="367dd-189">If you have installed [WMI Administrative Tools](https://go.microsoft.com/fwlink/?LinkId=95185), you can use the WMI CIM Studio to access WMI instances.</span></span> <span data-ttu-id="367dd-190">このツールは次のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="367dd-190">The tools are in the following folder</span></span>  
  
 <span data-ttu-id="367dd-191">**%windir%\Program Files\WMI Tools\\**</span><span class="sxs-lookup"><span data-stu-id="367dd-191">**%windir%\Program Files\WMI Tools\\**</span></span>  
  
1. <span data-ttu-id="367dd-192">**名前空間への接続:** ウィンドウで、「 **「root \servicemodel」**  をクリック**ok をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="367dd-192">In the **Connect to namespace:** window, type **root\ServiceModel** and click **OK.**</span></span>  
  
2. <span data-ttu-id="367dd-193">**WMI CIM Studio Login**ウィンドウで、をクリックして、**オプション >>** ボタン ウィンドウを展開します。</span><span class="sxs-lookup"><span data-stu-id="367dd-193">In the **WMI CIM Studio Login** window, click the **Options >>** button to expand the window.</span></span> <span data-ttu-id="367dd-194">選択**パケットのプライバシー**の**認証レベル**、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="367dd-194">Select **Packet privacy** for **Authentication level**, and click **OK**.</span></span>  
  
### <a name="windows-management-instrumentation-tester"></a><span data-ttu-id="367dd-195">Windows Management Instrumentation テスト</span><span class="sxs-lookup"><span data-stu-id="367dd-195">Windows Management Instrumentation Tester</span></span>  
 <span data-ttu-id="367dd-196">このツールは Windows によりインストールされます。</span><span class="sxs-lookup"><span data-stu-id="367dd-196">This tool is installed by Windows.</span></span> <span data-ttu-id="367dd-197">これを実行するには、」と入力してコマンド コンソールを起動**cmd.exe**で、**開始/実行** ダイアログ ボックスをクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="367dd-197">To run it, launch a command console by typing **cmd.exe** in the **Start/Run** dialog box and click **OK**.</span></span> <span data-ttu-id="367dd-198">次に、入力**wbemtest.exe**コマンド ウィンドウにします。</span><span class="sxs-lookup"><span data-stu-id="367dd-198">Then, type **wbemtest.exe** in the command window.</span></span> <span data-ttu-id="367dd-199">Windows Management Instrumentation テスト ツールが起動します。</span><span class="sxs-lookup"><span data-stu-id="367dd-199">The Windows Management Instrumentation Tester tool is then launched.</span></span>  
  
1. <span data-ttu-id="367dd-200">をクリックして、 **Connect**ウィンドウの右上隅のボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="367dd-200">Click the **Connect** button on the top right corner of the window.</span></span>  
  
2. <span data-ttu-id="367dd-201">新しいウィンドウで次のように入力します。 **「root \servicemodel」** の、 **Namespace**フィールド、および選択**パケットのプライバシー**の**認証レベル**します。</span><span class="sxs-lookup"><span data-stu-id="367dd-201">In the new window, enter **root\ServiceModel** for the **Namespace** field, and select **Packet privacy** for **Authentication level**.</span></span> <span data-ttu-id="367dd-202">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="367dd-202">Click **Connect**.</span></span>  
  
### <a name="using-managed-code"></a><span data-ttu-id="367dd-203">マネージド コードの使用</span><span class="sxs-lookup"><span data-stu-id="367dd-203">Using Managed Code</span></span>  
 <span data-ttu-id="367dd-204"><xref:System.Management> 名前空間が提供するクラスを使用して、リモートの WMI インスタンスにプログラムでアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="367dd-204">You can also access remote WMI instances programmatically by using classes provided by the <xref:System.Management> namespace.</span></span> <span data-ttu-id="367dd-205">これを実行する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="367dd-205">The following code sample demonstrates how to do this.</span></span>  
  
```csharp
String wcfNamespace = $@"\\{this.serviceMachineName}\Root\ServiceModel");
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
