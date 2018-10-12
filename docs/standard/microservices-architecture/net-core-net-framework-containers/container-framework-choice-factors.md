---
title: 意思決定テーブル。 Docker に使用する .NET Frameworks
description: '.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ | 意思決定テーブル、Docker に使用する .NET Frameworks'
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: 74b3749077fdb375f84ddacd98221aa4afcf2f67
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2018
ms.locfileid: "47401239"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="3c302-104">意思決定テーブル: Docker に使用する .NET Frameworks</span><span class="sxs-lookup"><span data-stu-id="3c302-104">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="3c302-105">次の意思決定テーブルは、.NET Framework と .NET Core のどちらを使用するかをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="3c302-105">The following decision table summarizes whether to use .NET Framework or .NET Core.</span></span> <span data-ttu-id="3c302-106">Linux コンテナーには、Linux ベースの Docker ホスト (VM またはサーバー) が必要であり、Windows コンテナーには、Windows Server ベースの Docker ホスト (VM またはサーバー) が必要であることを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="3c302-106">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c302-107">開発用のコンピューターは、Linux または Windows の Docker ホストを 1 つ実行します。</span><span class="sxs-lookup"><span data-stu-id="3c302-107">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="3c302-108">1 つのソリューションで同時に実行してテストしたい関連するマイクロサービスは、同じコンテナー プラットフォームで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c302-108">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3c302-109"><strong>アーキテクチャ/アプリの種類</strong></span><span class="sxs-lookup"><span data-stu-id="3c302-109"><strong>Architecture / App Type</strong></span></span></th>
<th><span data-ttu-id="3c302-110"><strong>Linux コンテナー</strong></span><span class="sxs-lookup"><span data-stu-id="3c302-110"><strong>Linux containers</strong></span></span></th>
<th><span data-ttu-id="3c302-111"><strong>Windows コンテナー</strong></span><span class="sxs-lookup"><span data-stu-id="3c302-111"><strong>Windows Containers</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3c302-112">コンテナー上のマイクロサービス</span><span class="sxs-lookup"><span data-stu-id="3c302-112">Microservices on containers</span></span></td>
<td><span data-ttu-id="3c302-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-113">.NET Core</span></span></td>
<td><span data-ttu-id="3c302-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-114">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3c302-115">モノリシック アプリ</span><span class="sxs-lookup"><span data-stu-id="3c302-115">Monolithic app</span></span></td>
<td><span data-ttu-id="3c302-116">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-116">.NET Core</span></span></td>
<td><p><span data-ttu-id="3c302-117">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3c302-117">.NET Framework</span></span></p>
<p><span data-ttu-id="3c302-118">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-118">.NET Core</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3c302-119">クラス最高のパフォーマンスとスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="3c302-119">Best-in-class performance and scalability</span></span></td>
<td><span data-ttu-id="3c302-120">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-120">.NET Core</span></span></td>
<td><span data-ttu-id="3c302-121">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-121">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3c302-122">Windows Server レガシー アプリ ("ブラウンフィールド") のコンテナーへの移行</span><span class="sxs-lookup"><span data-stu-id="3c302-122">Windows Server legacy app ("brown-field") migration to containers</span></span></td>
<td>--</td>
<td><span data-ttu-id="3c302-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3c302-123">.NET Framework</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3c302-124">コンテナー ベースの新しい開発 ("グリーンフィールド")</span><span class="sxs-lookup"><span data-stu-id="3c302-124">New container-based development ("green-field")</span></span></td>
<td><span data-ttu-id="3c302-125">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-125">.NET Core</span></span></td>
<td><span data-ttu-id="3c302-126">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-126">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3c302-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-127">ASP.NET Core</span></span></td>
<td><span data-ttu-id="3c302-128">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-128">.NET Core</span></span></td>
<td><p><span data-ttu-id="3c302-129">.NET Core (推奨)</span><span class="sxs-lookup"><span data-stu-id="3c302-129">.NET Core (recommended)</span></span></p>
<p><span data-ttu-id="3c302-130">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3c302-130">.NET Framework</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3c302-131">ASP.NET 4 (MVC 5、Web API 2、Web Forms)</span><span class="sxs-lookup"><span data-stu-id="3c302-131">ASP.NET 4 (MVC 5, Web API 2, and Web Forms)</span></span></td>
<td>--</td>
<td><span data-ttu-id="3c302-132">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3c302-132">.NET Framework</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3c302-133">SignalR サービス</span><span class="sxs-lookup"><span data-stu-id="3c302-133">SignalR services</span></span></td>
<td><span data-ttu-id="3c302-134">.NET Core 2.1 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="3c302-134">.NET Core 2.1 or higher version</span></span></td>
<td><p><span data-ttu-id="3c302-135">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3c302-135">.NET Framework</span></span></p>
<p><span data-ttu-id="3c302-136">.NET Core 2.1 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="3c302-136">.NET Core 2.1 or higher version</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3c302-137">WCF、WF などのレガシ フレームワーク</span><span class="sxs-lookup"><span data-stu-id="3c302-137">WCF, WF, and other legacy frameworks</span></span></td>
<td><span data-ttu-id="3c302-138">.NET Core の WCF (WCF クライアント ライブラリのみ)</span><span class="sxs-lookup"><span data-stu-id="3c302-138">WCF in .NET Core (only the WCF client library)</span></span></td>
<td><p><span data-ttu-id="3c302-139">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3c302-139">.NET Framework</span></span></p>
<p><span data-ttu-id="3c302-140">.NET Core の WCF (WCF クライアント ライブラリのみ)</span><span class="sxs-lookup"><span data-stu-id="3c302-140">WCF in .NET Core (only the WCF client library)</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3c302-141">Azure サービスの使用</span><span class="sxs-lookup"><span data-stu-id="3c302-141">Consumption of Azure services</span></span></td>
<td><p><span data-ttu-id="3c302-142">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-142">.NET Core</span></span></p>
<p><span data-ttu-id="3c302-143">(最終的に、すべての Azure サービスは .NET Core 用クライアント SDK を提供する予定です)</span><span class="sxs-lookup"><span data-stu-id="3c302-143">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
<td><p><span data-ttu-id="3c302-144">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3c302-144">.NET Framework</span></span></p>
<p><span data-ttu-id="3c302-145">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c302-145">.NET Core</span></span></p>
<p><span data-ttu-id="3c302-146">(最終的に、すべての Azure サービスは .NET Core 用クライアント SDK を提供する予定です)</span><span class="sxs-lookup"><span data-stu-id="3c302-146">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
<span data-ttu-id="3c302-147">[前へ](net-framework-container-scenarios.md)
[次へ](net-container-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="3c302-147">[Previous](net-framework-container-scenarios.md)
[Next](net-container-os-targets.md)</span></span>
