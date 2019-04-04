---
title: 'チュートリアル: Windows Communication Foundation アプリケーションを概要します。'
description: これらのチュートリアルでは、WCF アプリケーションを作成するための概要を提供します。
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 66211cfcf2b742e43eccbefb2bc7c4bd1147b05b
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408861"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="6d8fd-103">チュートリアル: Windows Communication Foundation アプリケーションを概要します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>
<span data-ttu-id="6d8fd-104">次の一連のチュートリアルに、Windows Communication Foundation (WCF) プログラミングの経験を紹介します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="6d8fd-105">順序でこれらのチュートリアルに従って作業では、WCF アプリケーションの作成に必要な手順の概要を理解するを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="6d8fd-106">完了したら、実行中の WCF サービスと WCF クライアント サービスを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span> 

<span data-ttu-id="6d8fd-107">このチュートリアルでは、開発環境として Visual Studio を使用している前提としています。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="6d8fd-108">他の開発環境を使用している場合は、Visual Studio 固有の手順を無視します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span> 

<span data-ttu-id="6d8fd-109">サンプル WCF アプリケーションをダウンロードして実行できる、[Windows Communication Foundation サンプル](samples/index.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="6d8fd-110">サンプルの概要については、[Getting started サンプル](samples/getting-started-sample.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="6d8fd-111">サービスとクライアントの作成の詳細の詳細については、[基本的な WCF プログラミング](basic-wcf-programming.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="6d8fd-112">WCF のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="6d8fd-112">WCF tutorials</span></span>

<span data-ttu-id="6d8fd-113">最初の 3 つのチュートリアルでは、WCF サービス コントラクトを定義する方法、その実装方法、およびそれをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="6d8fd-114">作成したサービスは、コンソール アプリケーション内で自己ホスト型です。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="6d8fd-115">Microsoft インターネット インフォメーション サービス (IIS) の下のサービスをホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="6d8fd-116">詳細については、「[方法 :IIS で WCF サービスをホスト](feature-details/how-to-host-a-wcf-service-in-iis.md)します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="6d8fd-117">コードを使用して、チュートリアルでは、サービスを構成することもできます[構成ファイル内でサービスを構成する](configuring-services-using-configuration-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span> 

- [<span data-ttu-id="6d8fd-118">チュートリアル: サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="6d8fd-119">WCF コントラクトを作成するには、ユーザー定義のインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="6d8fd-120">このコントラクトは、サービスが公開する機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="6d8fd-121">チュートリアル: サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="6d8fd-122">コントラクトを定義した後は、サービス クラスを使用して実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="6d8fd-123">チュートリアル: ホストし、基本的なサービスの実行</span><span class="sxs-lookup"><span data-stu-id="6d8fd-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="6d8fd-124">サービスのエンドポイントを構成し、コンソール アプリケーションでサービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="6d8fd-125">アクティブになるサービスの場合は、構成し、ランタイム環境内でホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="6d8fd-126">この実行時環境では、サービスを作成し、そのコンテキストと有効期間を制御します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="6d8fd-127">次の 2 つのチュートリアルでは、作成、構成する方法を説明して、使用して、サービス操作を呼び出すクライアント アプリケーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="6d8fd-128">サービスは、クライアント アプリケーションがサービスと通信するために必要な情報を定義したメタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="6d8fd-129">Visual Studio では、このメタデータにアクセスするプロセスを自動化し、サービスのクライアント アプリケーションの構築に使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="6d8fd-130">Visual Studio を使用しないようにする場合は、使用、 [ServiceModel メタデータ ユーティリティ ツール (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="6d8fd-131">チュートリアル: クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="6d8fd-132">WCF サービスから、WCF クライアント プロキシを作成するためのメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="6d8fd-133">サービス参照を追加する Visual Studio を使用してメタデータを取得するか、ServiceModel メタデータ ユーティリティ ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="6d8fd-134">クライアントがサービスへのアクセスに使用するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="6d8fd-135">チュートリアル: クライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="6d8fd-136">WCF クライアント プロキシを使用して、サービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="6d8fd-137">参照</span><span class="sxs-lookup"><span data-stu-id="6d8fd-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="6d8fd-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d8fd-138">See also</span></span>

- [<span data-ttu-id="6d8fd-139">概念の概要</span><span class="sxs-lookup"><span data-stu-id="6d8fd-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="6d8fd-140">ドキュメント ガイドします。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="6d8fd-141">Windows Communication Foundation とは</span><span class="sxs-lookup"><span data-stu-id="6d8fd-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="6d8fd-142">WCF 機能の詳細</span><span class="sxs-lookup"><span data-stu-id="6d8fd-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="6d8fd-143">基本的なプログラミング ライフ サイクル</span><span class="sxs-lookup"><span data-stu-id="6d8fd-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="6d8fd-144">クライアントを構築します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="6d8fd-145">基本的な WCF プログラミング</span><span class="sxs-lookup"><span data-stu-id="6d8fd-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="6d8fd-146">方法: 双方向コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="6d8fd-147">方法: Access services と双方向コントラクト</span><span class="sxs-lookup"><span data-stu-id="6d8fd-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="6d8fd-148">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="6d8fd-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="6d8fd-149">方法: Svcutil.exe を使用してメタデータ ドキュメントをダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="6d8fd-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [<span data-ttu-id="6d8fd-150">方法: 構成ファイルを使用して、サービスのメタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="6d8fd-150">How to: Publish metadata for a service using a configuration file</span></span>](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="6d8fd-151">バインドを使用してサービスとクライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="6d8fd-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6d8fd-152">入門サンプル</span><span class="sxs-lookup"><span data-stu-id="6d8fd-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="6d8fd-153">Windows Communication Foundation サンプル</span><span class="sxs-lookup"><span data-stu-id="6d8fd-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="6d8fd-154">自己ホスト</span><span class="sxs-lookup"><span data-stu-id="6d8fd-154">Self-Host</span></span>](samples/self-host.md)


