---
title: 破壊的変更、.NET Framework から .NET Core 3.0 - .NET Core
description: .NET Framework から .NET Core 3.0 への Windows フォームと Windows Presentation Foundation の破壊的変更の一覧を示します。
ms.date: 09/10/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c658c5bce7a2554bba83f2779a73d9d6af01a342
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151531"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a><span data-ttu-id="92c18-103">.NET Framework から .NET Core 3.0 への移行の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="92c18-103">Breaking changes for migration from .NET Framework to .NET Core 3.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92c18-104">この記事は作成中です。</span><span class="sxs-lookup"><span data-stu-id="92c18-104">This article is under construction.</span></span> <span data-ttu-id="92c18-105">これは、.NET Core の破壊的変更の完全なリストではありません。</span><span class="sxs-lookup"><span data-stu-id="92c18-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="92c18-106">.NET Core の破壊的変更の詳細については、GitHub の dotnet/docs リポジトリで個別の[破壊的変更の問題](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)について調べてください。</span><span class="sxs-lookup"><span data-stu-id="92c18-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="92c18-107">.NET Framework から .NET Core 3.0 に Windows フォームまたは Windows Presentation Foundation のアプリケーションを移行する場合、ご使用のアプリに影響する可能性がある破壊的変更について次のトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="92c18-107">If you are migrating a Windows Forms or Windows Presentation Foundation application from .NET Framework to .NET Core 3.0, review the following topics for breaking changes that may affect your app:</span></span>

## <a name="windows-forms"></a><span data-ttu-id="92c18-108">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="92c18-108">Windows Forms</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
