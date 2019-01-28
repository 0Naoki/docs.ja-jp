---
title: CorFlags.exe (CorFlags 変換ツール)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae2efe619d9c6ebcf2c570b5a63d569faf3b3343
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690749"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="bcd88-102">CorFlags.exe (CorFlags 変換ツール)</span><span class="sxs-lookup"><span data-stu-id="bcd88-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="bcd88-103">CorFlags 変換ツールを使用して、ポータブル実行可能 (PE) ファイル イメージのヘッダー内の CorFlags セクションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bcd88-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="bcd88-104">このツールは、Visual Studio と共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bcd88-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="bcd88-105">このツールを実行するには、Visual Studio 用開発者コマンド プロンプト (または Windows 7 の Visual Studio コマンド プロンプト) を使用します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="bcd88-106">詳細については、「[Visual Studio 用開発者コマンド プロンプト](../../../docs/framework/tools/developer-command-prompt-for-vs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcd88-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="bcd88-107">コマンド プロンプトに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd88-108">構文</span><span class="sxs-lookup"><span data-stu-id="bcd88-108">Syntax</span></span>  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcd88-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcd88-109">Parameters</span></span>  
  
|<span data-ttu-id="bcd88-110">必須パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcd88-110">Required parameter</span></span>|<span data-ttu-id="bcd88-111">説明</span><span class="sxs-lookup"><span data-stu-id="bcd88-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="bcd88-112">CorFlags を設定するアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="bcd88-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="bcd88-113">オプション</span><span class="sxs-lookup"><span data-stu-id="bcd88-113">Option</span></span>|<span data-ttu-id="bcd88-114">説明</span><span class="sxs-lookup"><span data-stu-id="bcd88-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bcd88-115">**32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="bcd88-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="bcd88-116">32BITREQUIRED フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="bcd88-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="bcd88-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="bcd88-118">32BITREQUIRED フラグをクリアします。</span><span class="sxs-lookup"><span data-stu-id="bcd88-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="bcd88-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="bcd88-119">**/32BITPREF+**</span></span>|<span data-ttu-id="bcd88-120">32BITPREFERRED フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="bcd88-121">アプリは、64 ビット プラットフォーム上でも 32 ビット プロセスとして実行します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="bcd88-122">このフラグは、EXE ファイルでのみ設定します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="bcd88-123">このフラグを DLL で設定した場合、64 ビット プロセスで DLL を読み込むことができず、<xref:System.BadImageFormatException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="bcd88-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="bcd88-124">このフラグを設定した EXE ファイルは、64 ビット プロセスで読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="bcd88-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="bcd88-125">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] の新機能。</span><span class="sxs-lookup"><span data-stu-id="bcd88-125">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="bcd88-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="bcd88-126">**/32BITPREF-**</span></span>|<span data-ttu-id="bcd88-127">32BITPREFERRED フラグをクリアします。</span><span class="sxs-lookup"><span data-stu-id="bcd88-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="bcd88-128">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] の新機能。</span><span class="sxs-lookup"><span data-stu-id="bcd88-128">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="bcd88-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="bcd88-129">**/?**</span></span>|<span data-ttu-id="bcd88-130">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="bcd88-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="bcd88-131">**/Force**</span></span>|<span data-ttu-id="bcd88-132">厳密な名前が付けられているアセンブリであっても、強制的に更新します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="bcd88-133">**重要:** 厳密な名前が付けられているアセンブリを更新する場合は、そのコードを実行する前に再署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcd88-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="bcd88-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="bcd88-134">**/help**</span></span>|<span data-ttu-id="bcd88-135">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="bcd88-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="bcd88-136">**/ILONLY+**</span></span>|<span data-ttu-id="bcd88-137">ILONLY フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="bcd88-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="bcd88-138">**/ILONLY-**</span></span>|<span data-ttu-id="bcd88-139">ILONLY フラグをクリアします。</span><span class="sxs-lookup"><span data-stu-id="bcd88-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="bcd88-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="bcd88-140">**/nologo**</span></span>|<span data-ttu-id="bcd88-141">Microsoft 著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="bcd88-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="bcd88-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="bcd88-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="bcd88-143">CLR ヘッダー バージョンを 2.0 に戻します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="bcd88-144">**/UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="bcd88-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="bcd88-145">CLR ヘッダー バージョンを 2.5 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="bcd88-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="bcd88-146">**注:** アセンブリをネイティブに実行するには、CLR ヘッダー バージョン 2.5 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="bcd88-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcd88-147">コメント</span><span class="sxs-lookup"><span data-stu-id="bcd88-147">Remarks</span></span>  
 <span data-ttu-id="bcd88-148">オプションが何も指定されていない場合、CorFlags 変換ツールは指定されているアセンブリのフラグを表示します。</span><span class="sxs-lookup"><span data-stu-id="bcd88-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd88-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcd88-149">See also</span></span>
- [<span data-ttu-id="bcd88-150">ツール</span><span class="sxs-lookup"><span data-stu-id="bcd88-150">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="bcd88-151">64 ビット アプリケーション</span><span class="sxs-lookup"><span data-stu-id="bcd88-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)
- [<span data-ttu-id="bcd88-152">Visual Studio 用開発者コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="bcd88-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
