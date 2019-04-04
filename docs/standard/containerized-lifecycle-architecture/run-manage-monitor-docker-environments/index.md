---
title: Docker 実稼働環境の実行、管理、および監視
description: Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 7c470a2d24b8807bdda10e1816bc5a430a5c63f1
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56834941"
---
# <a name="run-manage-and-monitor-docker-production-environments"></a><span data-ttu-id="759e7-103">Docker 実稼働環境の実行、管理、および監視</span><span class="sxs-lookup"><span data-stu-id="759e7-103">Run, manage, and monitor Docker production environments</span></span>

<span data-ttu-id="759e7-104">ビジョン:エンタープライズ アプリケーションを高可用性と高スケーラビリティを実行する必要があります。IT 運用は、環境とアプリケーション自体を管理および監視できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="759e7-104">Vision: Enterprise applications need to run with high availability and high scalability; IT operations need to be able to manage and monitor the environments and the applications themselves.</span></span>

<span data-ttu-id="759e7-105">コンテナー化された Docker アプリケーションのライフ サイクルのこの最後の柱の焦点は、拡張性と可用性の高い (HA) 実稼働環境で、アプリケーションをどのように実行、管理、および監視するかです。</span><span class="sxs-lookup"><span data-stu-id="759e7-105">This last pillar in the containerized Docker applications life cycle is centered on how you can run, manage, and monitor your applications in scalable, high availability (HA) production environments.</span></span>

<span data-ttu-id="759e7-106">(インフラストラクチャ アーキテクチャとプラットフォーム テクノロジ) を運用環境でコンテナー化されたアプリケーションを実行する方法は非常に関連し、選択したこの電子書籍の第 1 章で説明したアーキテクチャと開発プラットフォームにします。</span><span class="sxs-lookup"><span data-stu-id="759e7-106">The way you run your containerized applications in production (infrastructure architecture and platform technologies) is very much related and based on the chosen architecture and development platforms discussed in Chapter 1 of this e-book.</span></span>

<span data-ttu-id="759e7-107">この章は、特定の製品およびマイクロソフトのテクノロジを調査し、効果的に拡張性が高く、実行に使用できるベンダーの他の HA 分散アプリケーション、および管理し、IT の視点から監視する方法。</span><span class="sxs-lookup"><span data-stu-id="759e7-107">This chapter examines specific products and technologies from Microsoft and other vendors that you can use to effectively run scalable, HA distributed applications plus how you can manage and monitor them from the IT perspective.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="759e7-108">[前へ](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
>[次へ](run-microservices-based-applications-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="759e7-108">[Previous](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
[Next](run-microservices-based-applications-in-production.md)</span></span>
