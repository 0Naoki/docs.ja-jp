---
title: コード アクセス セキュリティ ポリシーの互換性と移行
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d9281e52de43391a92262f85084715ccabd5515
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868915"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="e8400-102">コード アクセス セキュリティ ポリシーの互換性と移行</span><span class="sxs-lookup"><span data-stu-id="e8400-102">Code Access Security Policy Compatibility and Migration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="e8400-103">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] では、コード アクセス セキュリティ (CAS) のポリシー部分は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="e8400-103">The policy portion of code access security (CAS) has been made obsolete in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="e8400-104">その結果、発生するコンパイルの警告とランタイム例外、廃止されたポリシーの種類とメンバーを呼び出す場合[明示的に](#explicit_use)または[暗黙的に](#implicit_use)(を通じて他の型とメンバーを使用して)。</span><span class="sxs-lookup"><span data-stu-id="e8400-104">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>

<span data-ttu-id="e8400-105">以下のいずれかの方法で警告やエラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="e8400-105">You can avoid the warnings and errors by either:</span></span>

- <span data-ttu-id="e8400-106">[移行](#migration)を[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]廃止された呼び出しに置換します。</span><span class="sxs-lookup"><span data-stu-id="e8400-106">[Migrating](#migration) to the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] replacements for the obsolete calls.</span></span>

   <span data-ttu-id="e8400-107">\- または -</span><span class="sxs-lookup"><span data-stu-id="e8400-107">\- or -</span></span>

- <span data-ttu-id="e8400-108">使用して、 [< NetFx40_LegacySecurityPolicy > 構成要素](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)従来の CAS ポリシーの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e8400-108">Using the [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>

<span data-ttu-id="e8400-109">このトピックは、次のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="e8400-109">This topic contains the following sections:</span></span>

- [<span data-ttu-id="e8400-110">明示的な使用</span><span class="sxs-lookup"><span data-stu-id="e8400-110">Explicit Use</span></span>](#explicit_use)

- [<span data-ttu-id="e8400-111">暗黙的な使用</span><span class="sxs-lookup"><span data-stu-id="e8400-111">Implicit Use</span></span>](#implicit_use)

- [<span data-ttu-id="e8400-112">エラーと警告</span><span class="sxs-lookup"><span data-stu-id="e8400-112">Errors and Warnings</span></span>](#errors_and_warnings)

- [<span data-ttu-id="e8400-113">移行:廃止された呼び出しの置換</span><span class="sxs-lookup"><span data-stu-id="e8400-113">Migration: Replacement for Obsolete Calls</span></span>](#migration)

- [<span data-ttu-id="e8400-114">互換性:CAS ポリシーのレガシー オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8400-114">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a><span data-ttu-id="e8400-115">明示的な使用</span><span class="sxs-lookup"><span data-stu-id="e8400-115">Explicit Use</span></span>

<span data-ttu-id="e8400-116">直接セキュリティ ポリシーを操作するメンバー、または CAS ポリシーをサンドボックス化することが必要なメンバーは廃止され、既定ではエラーを発生するようになりました。</span><span class="sxs-lookup"><span data-stu-id="e8400-116">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>

<span data-ttu-id="e8400-117">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e8400-117">Examples of these are:</span></span>

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a><span data-ttu-id="e8400-118">暗黙的な使用</span><span class="sxs-lookup"><span data-stu-id="e8400-118">Implicit Use</span></span>

<span data-ttu-id="e8400-119">アセンブリの読み込みオーバーロードの中にはエラーを生成するものがあります。CAS ポリシーを暗黙的に使用することが原因です。</span><span class="sxs-lookup"><span data-stu-id="e8400-119">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="e8400-120">これらのオーバーロードはCAS ポリシーを解決するために <xref:System.Security.Policy.Evidence> パラメーターを取り、アセンブリにアクセス許可セットを提供します。</span><span class="sxs-lookup"><span data-stu-id="e8400-120">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>

<span data-ttu-id="e8400-121">以下に例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="e8400-121">Here are some examples.</span></span> <span data-ttu-id="e8400-122">パラメーターとして <xref:System.Security.Policy.Evidence> を取るオーバーロードが廃止されました。</span><span class="sxs-lookup"><span data-stu-id="e8400-122">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a><span data-ttu-id="e8400-123">エラーと警告</span><span class="sxs-lookup"><span data-stu-id="e8400-123">Errors and Warnings</span></span>

<span data-ttu-id="e8400-124">廃止された種類とメンバーが使用されると、以下のエラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e8400-124">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="e8400-125"><xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 型自体は廃止されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8400-125">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>

<span data-ttu-id="e8400-126">コンパイル時の警告:</span><span class="sxs-lookup"><span data-stu-id="e8400-126">Compile-time warning:</span></span>

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

<span data-ttu-id="e8400-127">実行時の例外:</span><span class="sxs-lookup"><span data-stu-id="e8400-127">Run-time exception:</span></span>

<span data-ttu-id="e8400-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="e8400-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="e8400-129">移行:廃止された呼び出しの置換</span><span class="sxs-lookup"><span data-stu-id="e8400-129">Migration: Replacement for Obsolete Calls</span></span>

### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="e8400-130">アセンブリの信頼レベルの判別</span><span class="sxs-lookup"><span data-stu-id="e8400-130">Determining an Assembly’s Trust Level</span></span>

<span data-ttu-id="e8400-131">CAS ポリシーは多くの場合、アセンブリ、アプリケーション ドメインのアクセス許可セット、または信頼レベルを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8400-131">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="e8400-132">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] では、セキュリティ ポリシーを解決する必要のない次の便利なプロパティが公開されています。</span><span class="sxs-lookup"><span data-stu-id="e8400-132">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes the following useful properties that do not need to resolve security policy:</span></span>

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a><span data-ttu-id="e8400-133">アプリケーション ドメインのサンドボックス化</span><span class="sxs-lookup"><span data-stu-id="e8400-133">Application Domain Sandboxing</span></span>

<span data-ttu-id="e8400-134">通常 <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> メソッドは、アプリケーション ドメイン内のアセンブリをサンド ボックス化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e8400-134">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="e8400-135">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]で公開されるメンバーを使用する必要はありませんが<xref:System.Security.Policy.PolicyLevel>この目的のためです。</span><span class="sxs-lookup"><span data-stu-id="e8400-135">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="e8400-136">詳細については、「[方法 :Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)」 (方法: サンドボックスで部分信頼コードを実行する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8400-136">For more information, see [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="e8400-137">部分的に信頼できるコードに対する安全なまたは適切なアクセス許可セットの決定</span><span class="sxs-lookup"><span data-stu-id="e8400-137">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>

<span data-ttu-id="e8400-138">多くの場合ホストでは、ホストされているコードをサンドボックス化するための適切なアクセス許可を判別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8400-138">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="e8400-139">前に、 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]、CAS ポリシーでこれを行う方法を提供する、<xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="e8400-139">Before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e8400-140">代わりに、[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]提供、<xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType>安全な標準的な権限が指定された証拠のセットを返すメソッド。</span><span class="sxs-lookup"><span data-stu-id="e8400-140">As a replacement, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="e8400-141">サンド ボックス化以外のシナリオ:アセンブリ読み込みのオーバー ロード</span><span class="sxs-lookup"><span data-stu-id="e8400-141">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>

<span data-ttu-id="e8400-142">アセンブリ読み込みオーバーロードを使用する目的は、アセンブリのサンドボックス化の代わりに、アセンブリ読み込みオーバーロードでないと使用できないパラメーターを指定することです。</span><span class="sxs-lookup"><span data-stu-id="e8400-142">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="e8400-143">以降では、[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]を必要としないアセンブリ読み込みオーバー ロードを<xref:System.Security.Policy.Evidence?displayProperty=nameWithType>オブジェクトをパラメーターとして<xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>、このシナリオを実現します。</span><span class="sxs-lookup"><span data-stu-id="e8400-143">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>

<span data-ttu-id="e8400-144">アセンブリをサンドボックス化する場合には、<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> オーバー ロードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8400-144">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="e8400-145">互換性:CAS ポリシーのレガシー オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8400-145">Compatibility: Using the CAS Policy Legacy Option</span></span>

<span data-ttu-id="e8400-146">[< NetFx40_LegacySecurityPolicy > 構成要素](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)プロセスまたはライブラリが、従来の CAS ポリシーを使用するように指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e8400-146">The [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="e8400-147">この要素を有効にすると、ポリシーと証拠のオーバーロードは、framework の以前のバージョンの場合と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="e8400-147">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>

> [!NOTE]
> <span data-ttu-id="e8400-148">CAS ポリシーの動作は特定のランタイム バージョンに固有なので、そのランタイム バージョンの CAS ポリシーを変更しても、別のバージョンの CAS ポリシーには影響しません。</span><span class="sxs-lookup"><span data-stu-id="e8400-148">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e8400-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8400-149">See also</span></span>

- [<span data-ttu-id="e8400-150">方法: サンドボックスで部分信頼コードを実行する</span><span class="sxs-lookup"><span data-stu-id="e8400-150">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="e8400-151">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="e8400-151">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
