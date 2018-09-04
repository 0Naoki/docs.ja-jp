---
title: WCF Data Services の定義
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: c0c9010a71877d2c9757a2c9cf2d5c1fec8aedf7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515538"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="8d1e2-102">WCF Data Services の定義</span><span class="sxs-lookup"><span data-stu-id="8d1e2-102">Defining WCF Data Services</span></span>

<span data-ttu-id="8d1e2-103">このセクションを作成して、データとして公開する WCF Data Services を構成する方法を説明します、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]フィードします。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-103">This section describes how to create and configure WCF Data Services to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="8d1e2-104">データ サービスを作成するために必要な基本的な手順の詳細については、次を参照してください。[サービスとしてのあなたのデータを公開する](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-104">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8d1e2-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8d1e2-105">In This Section</span></span>

 [<span data-ttu-id="8d1e2-106">データ サービスの構成</span><span class="sxs-lookup"><span data-stu-id="8d1e2-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="8d1e2-107">WCF Data Services によって提供されるデータ サービス構成オプションをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-107">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="8d1e2-108">Data Services プロバイダー</span><span class="sxs-lookup"><span data-stu-id="8d1e2-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)

 <span data-ttu-id="8d1e2-109">データ サービスとしてデータを公開するプロバイダー モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-109">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="8d1e2-110">サービス操作</span><span class="sxs-lookup"><span data-stu-id="8d1e2-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)

 <span data-ttu-id="8d1e2-111">サーバー上でメソッドを公開するサービス操作を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-111">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="8d1e2-112">フィードのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8d1e2-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)

 <span data-ttu-id="8d1e2-113">データ サービス プロバイダーおよびデータ フィードの要素によって定義されるデータ モデルのエンティティ間のマッピングを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="8d1e2-114">インターセプター</span><span class="sxs-lookup"><span data-stu-id="8d1e2-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)

 <span data-ttu-id="8d1e2-115">インターセプター メソッドを定義してデータ サービスへの要求に対してカスタム ビジネス ロジックを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="8d1e2-116">WCF Data Services の開発と配置</span><span class="sxs-lookup"><span data-stu-id="8d1e2-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="8d1e2-117">Visual Studio を使用してデータ サービスを開発および配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="8d1e2-118">WCF Data Services のセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="8d1e2-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)

 <span data-ttu-id="8d1e2-119">データ サービスの認証と承認およびセキュリティに関するその他の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-119">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="8d1e2-120">データ サービスのホスティング</span><span class="sxs-lookup"><span data-stu-id="8d1e2-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="8d1e2-121">データ サービスのホストを選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-121">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="8d1e2-122">データ サービスのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="8d1e2-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="8d1e2-123">OData の異なるバージョンを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-123">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="8d1e2-124">WCF Data Services プロトコル実装の詳細</span><span class="sxs-lookup"><span data-stu-id="8d1e2-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="8d1e2-125">WCF Data Services で現在実装されていない OData プロトコルのオプションの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1e2-125">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d1e2-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d1e2-126">See Also</span></span>

- [<span data-ttu-id="8d1e2-127">WCF Data Services クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8d1e2-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [<span data-ttu-id="8d1e2-128">データ サービス リソースへのアクセス</span><span class="sxs-lookup"><span data-stu-id="8d1e2-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="8d1e2-129">はじめに</span><span class="sxs-lookup"><span data-stu-id="8d1e2-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
