---
title: Regsvcs.exe (.NET サービス インストール ツール)
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dccf1b841d048ae460b89fd97da833aadb988422
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971812"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="50410-102">Regsvcs.exe (.NET サービス インストール ツール)</span><span class="sxs-lookup"><span data-stu-id="50410-102">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="50410-103">.NET サービス インストール ツールは、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="50410-103">The .NET Services Installation tool performs the following actions:</span></span>  
  
- <span data-ttu-id="50410-104">アセンブリの読み込みと登録。</span><span class="sxs-lookup"><span data-stu-id="50410-104">Loads and registers an assembly.</span></span>  
  
- <span data-ttu-id="50410-105">タイプ ライブラリの生成、登録、および指定された COM+ アプリケーションへのインストール。</span><span class="sxs-lookup"><span data-stu-id="50410-105">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
- <span data-ttu-id="50410-106">プログラムでクラスに追加したサービスの設定。</span><span class="sxs-lookup"><span data-stu-id="50410-106">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="50410-107">このツールを実行するには、Visual Studio 用開発者コマンド プロンプト (または Windows 7 の Visual Studio コマンド プロンプト) を使用します。</span><span class="sxs-lookup"><span data-stu-id="50410-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="50410-108">詳細については、「[Visual Studio 用開発者コマンド プロンプト](../../../docs/framework/tools/developer-command-prompt-for-vs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50410-108">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="50410-109">コマンド プロンプトに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="50410-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50410-110">構文</span><span class="sxs-lookup"><span data-stu-id="50410-110">Syntax</span></span>  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
## <a name="parameters"></a><span data-ttu-id="50410-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50410-111">Parameters</span></span>  
  
|<span data-ttu-id="50410-112">引数</span><span class="sxs-lookup"><span data-stu-id="50410-112">Argument</span></span>|<span data-ttu-id="50410-113">説明</span><span class="sxs-lookup"><span data-stu-id="50410-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="50410-114">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="50410-114">*assemblyFile.dll*</span></span>|<span data-ttu-id="50410-115">ソース アセンブリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="50410-115">The source assembly file.</span></span> <span data-ttu-id="50410-116">アセンブリは、厳密な名前で署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50410-116">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="50410-117">詳しくは、「[厳密な名前でのアセンブリへの署名](../../standard/assembly/sign-strong-name.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50410-117">For more information, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span>|  
  
|<span data-ttu-id="50410-118">オプション</span><span class="sxs-lookup"><span data-stu-id="50410-118">Option</span></span>|<span data-ttu-id="50410-119">説明</span><span class="sxs-lookup"><span data-stu-id="50410-119">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="50410-120">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="50410-120">**/appdir:** *path*</span></span>|<span data-ttu-id="50410-121">アプリケーションのルート ディレクトリを示します。</span><span class="sxs-lookup"><span data-stu-id="50410-121">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="50410-122">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="50410-122">**/appname:** *applicationName*</span></span>|<span data-ttu-id="50410-123">検索または作成する COM+ アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="50410-123">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="50410-124">**/c**</span><span class="sxs-lookup"><span data-stu-id="50410-124">**/c**</span></span>|<span data-ttu-id="50410-125">ターゲット アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="50410-125">Creates the target application.</span></span>|  
|<span data-ttu-id="50410-126">**/componly**</span><span class="sxs-lookup"><span data-stu-id="50410-126">**/componly**</span></span>|<span data-ttu-id="50410-127">コンポーネントだけを設定します。メソッドとインターフェイスは無視されます。</span><span class="sxs-lookup"><span data-stu-id="50410-127">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="50410-128">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="50410-128">**/exapp**</span></span>|<span data-ttu-id="50410-129">このツールが既存のアプリケーションを要求するように指定します。</span><span class="sxs-lookup"><span data-stu-id="50410-129">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="50410-130">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="50410-130">**/extlb**</span></span>|<span data-ttu-id="50410-131">既存のタイプ ライブラリを使用します。</span><span class="sxs-lookup"><span data-stu-id="50410-131">Uses an existing type library.</span></span>|  
|<span data-ttu-id="50410-132">**/fc**</span><span class="sxs-lookup"><span data-stu-id="50410-132">**/fc**</span></span>|<span data-ttu-id="50410-133">対象アプリケーションを検索または作成します。</span><span class="sxs-lookup"><span data-stu-id="50410-133">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="50410-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="50410-134">**/help**</span></span>|<span data-ttu-id="50410-135">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="50410-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="50410-136">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="50410-136">**/noreconfig**</span></span>|<span data-ttu-id="50410-137">既存の対象アプリケーションを再設定しません。</span><span class="sxs-lookup"><span data-stu-id="50410-137">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="50410-138">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="50410-138">**/nologo**</span></span>|<span data-ttu-id="50410-139">Microsoft 著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="50410-139">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="50410-140">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="50410-140">**/parname:** *name*</span></span>|<span data-ttu-id="50410-141">検索または作成する COM+ アプリケーションの名前または ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="50410-141">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="50410-142">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="50410-142">**/reconfig**</span></span>|<span data-ttu-id="50410-143">既存の対象アプリケーションを再設定します。</span><span class="sxs-lookup"><span data-stu-id="50410-143">Reconfigures an existing target application.</span></span> <span data-ttu-id="50410-144">既定値です。</span><span class="sxs-lookup"><span data-stu-id="50410-144">This is the default.</span></span>|  
|<span data-ttu-id="50410-145">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="50410-145">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="50410-146">インストールするタイプ ライブラリ ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="50410-146">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="50410-147">**/u**</span><span class="sxs-lookup"><span data-stu-id="50410-147">**/u**</span></span>|<span data-ttu-id="50410-148">対象アプリケーションをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="50410-148">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="50410-149">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="50410-149">**/quiet**</span></span>|<span data-ttu-id="50410-150">クワイエット モードを指定します。ロゴと成功メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="50410-150">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="50410-151">**/?**</span><span class="sxs-lookup"><span data-stu-id="50410-151">**/?**</span></span>|<span data-ttu-id="50410-152">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="50410-152">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50410-153">解説</span><span class="sxs-lookup"><span data-stu-id="50410-153">Remarks</span></span>  
 <span data-ttu-id="50410-154">Regsvcs.exe には、*assemblyFile.dll* で指定されているソース アセンブリ ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="50410-154">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="50410-155">このアセンブリは、厳密な名前で署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50410-155">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="50410-156">厳密な名前での署名について詳しくは、「[厳密な名前でのアセンブリへの署名](../../standard/assembly/sign-strong-name.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50410-156">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span> <span data-ttu-id="50410-157">対象アプリケーションおよびタイプ ライブラリの名前は、オプションです。</span><span class="sxs-lookup"><span data-stu-id="50410-157">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="50410-158">引数 *applicationName* はソース アセンブリ ファイルから生成できます。存在しない場合は、Regsvcs.exe によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="50410-158">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="50410-159">引数 *typelibraryfile* にはタイプ ライブラリ名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="50410-159">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="50410-160">タイプ ライブラリ名を指定しない場合、Regsvcs.exe は既定値としてアセンブリ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="50410-160">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="50410-161">Regsvcs.exe がコンポーネントのメソッドを登録する場合は、それらのメソッドに対する[確認要求](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100))と[リンク確認要求](../../../docs/framework/misc/link-demands.md)の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="50410-161">When Regsvcs.exe registers a component's methods, it is subject to the [demands](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../../../docs/framework/misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="50410-162">このツールは完全に信頼された環境で実行されるため、アクセス許可に対するほとんどの確認要求は成功します。</span><span class="sxs-lookup"><span data-stu-id="50410-162">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="50410-163">ただし、Regsvcs.exe では、<xref:System.Security.Permissions.StrongNameIdentityPermission> または <xref:System.Security.Permissions.PublisherIdentityPermission> に対する確認要求やリンク確認要求によって保護されたメソッドを含むコンポーネントを登録することはできません。</span><span class="sxs-lookup"><span data-stu-id="50410-163">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="50410-164">Regsvcs.exe を使用するには、ローカル コンピューターの管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="50410-164">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="50410-165">上記のアクションの実行中に Regsvcs.exe が異常終了した場合は、対応するエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50410-165">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="50410-166">使用例</span><span class="sxs-lookup"><span data-stu-id="50410-166">Examples</span></span>  
 <span data-ttu-id="50410-167">`myTest.dll` に含まれるすべてのパブリック クラスを `myTargetApp` (既存の COM+ アプリケーション) に追加し、タイプ ライブラリ `myTest.tlb` を生成するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="50410-167">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="50410-168">`myTest.dll` に含まれるすべてのパブリック クラスを `myTargetApp` (既存の COM+ アプリケーション) に追加し、タイプ ライブラリ `newTest.tlb` を生成するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="50410-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="50410-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="50410-169">See also</span></span>

- [<span data-ttu-id="50410-170">ツール</span><span class="sxs-lookup"><span data-stu-id="50410-170">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="50410-171">方法: 厳密な名前でアセンブリに署名する</span><span class="sxs-lookup"><span data-stu-id="50410-171">How to: Sign an Assembly with a Strong Name</span></span>](../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="50410-172">Visual Studio 用開発者コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="50410-172">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
