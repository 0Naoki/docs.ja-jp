---
title: '方法: インストールされている NET Framework セキュリティ更新プログラムおよび修正プログラムを確認する'
description: コンピューターにインストールされている NET Framework セキュリティ更新プログラムおよび修正プログラムを確認する方法について説明します。
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4c505c679c46494f7dc2534c2bbe9f50243a7dd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790066"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="8c5ae-103">方法: インストールされている NET Framework セキュリティ更新プログラムおよび修正プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="8c5ae-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="8c5ae-104">この記事では、コンピューターにインストールされている NET Framework セキュリティ更新プログラムおよび修正プログラムを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="8c5ae-105">この記事で紹介する手法にはすべて、管理特権が与えられたアカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="8c5ae-106">レジストリを利用し、インストールされている更新プログラムを見つける</span><span class="sxs-lookup"><span data-stu-id="8c5ae-106">To find installed updates using the registry</span></span>

<span data-ttu-id="8c5ae-107">コンピューターにインストールされている .NET Framework のバージョンごとのインストール済みのセキュリティ更新プログラムおよび修正プログラムは、Windows レジストリに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="8c5ae-108">レジストリ エディター (*regedit.exe*) プログラムを使用して、この情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="8c5ae-109">プログラム **regedit.exe** を開きます。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="8c5ae-110">Windows 8 以降のバージョンでは、 **[スタート]** ![Windows ロゴ](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")を右クリックし、 **[ファイル名を指定して実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-110">In Windows 8 and later versions, right-click **Start** ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="8c5ae-111">**[開く]** ボックスに「**regedit**」と入力し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="8c5ae-112">レジストリ エディターで、次のサブキーを開きます。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="8c5ae-113">インストールされている更新プログラムは、適用された .NET Framework バージョンを識別するサブキーの下に一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="8c5ae-114">各更新プログラムは、サポート技術情報の (KB) 番号で識別されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="8c5ae-115">レジストリ エディターでは、各バージョンの .NET Framework バージョンとインストールされている更新プログラムが別々のサブキーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="8c5ae-116">インストールされているバージョン番号の詳細については、「[方法: インストールされている .NET Framework バージョンを確認する](how-to-determine-which-versions-are-installed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="8c5ae-117">コードでレジストリにクエリを実行し、インストールされている更新プログラムを見つける</span><span class="sxs-lookup"><span data-stu-id="8c5ae-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="8c5ae-118">次の例では、コンピューターにインストールされている .NET Framework セキュリティ更新プログラムおよび修正プログラムをプログラミングによって判断します。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="8c5ae-119">この例では次のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-119">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="8c5ae-120">PowerShell でレジストリにクエリを実行し、インストールされている更新プログラムを見つける</span><span class="sxs-lookup"><span data-stu-id="8c5ae-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="8c5ae-121">次の例では、PowerShell を利用し、コンピューターにインストールされている .NET Framework セキュリティ更新プログラムおよび修正プログラムを判断する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

<span data-ttu-id="8c5ae-122">この例では次のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ae-122">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
Microsoft .NET Framework 4 Extended
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
```

## <a name="see-also"></a><span data-ttu-id="8c5ae-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c5ae-123">See also</span></span>

- [<span data-ttu-id="8c5ae-124">方法: インストールされている .NET Framework バージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="8c5ae-124">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="8c5ae-125">開発者向けの .NET Framework のインストール</span><span class="sxs-lookup"><span data-stu-id="8c5ae-125">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="8c5ae-126">バージョンおよび依存関係</span><span class="sxs-lookup"><span data-stu-id="8c5ae-126">Versions and dependencies</span></span>](versions-and-dependencies.md)
