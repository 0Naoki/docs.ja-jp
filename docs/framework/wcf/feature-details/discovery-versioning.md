---
title: 探索機能のバージョン指定
ms.date: 03/30/2017
ms.assetid: f91c6d0a-3af2-45c5-9a5c-e75390619836
ms.openlocfilehash: 3f90fc5183e974b9045c156e0ae74099abfbc41a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626961"
---
# <a name="discovery-versioning"></a><span data-ttu-id="09a90-102">探索機能のバージョン指定</span><span class="sxs-lookup"><span data-stu-id="09a90-102">Discovery Versioning</span></span>
<span data-ttu-id="09a90-103">ここでは、新しい探索機能の実装の概要について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="09a90-103">This topic provides a brief overview of the implementation of some new discovery features.</span></span> <span data-ttu-id="09a90-104">使用する探索バージョンを選択する方法の概要も示します。</span><span class="sxs-lookup"><span data-stu-id="09a90-104">It also gives an overview on how to select the discovery version to use.</span></span>  
  
## <a name="discovery-versioning"></a><span data-ttu-id="09a90-105">探索機能のバージョン指定</span><span class="sxs-lookup"><span data-stu-id="09a90-105">Discovery Versioning</span></span>  
 <span data-ttu-id="09a90-106">探索機能は、WS_Discovery プロトコルの 3 つのバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="09a90-106">The discovery feature includes support for three versions of the WS_Discovery protocol.</span></span> <span data-ttu-id="09a90-107">探索 API を使用すると、使用するプロトコルのバージョンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="09a90-107">The discovery APIs allow you to select which version of the protocol you want to use.</span></span> <span data-ttu-id="09a90-108">このドキュメントでは、バージョン指定に関連する設定について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="09a90-108">This document briefly describes the versioning-related settings.</span></span>  
  
 <span data-ttu-id="09a90-109">次の Discovery クラスには <xref:System.ServiceModel.Discovery.DiscoveryVersion> プロパティがあり、コンストラクターで <xref:System.ServiceModel.Discovery.DiscoveryVersion> 引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="09a90-109">The following Discovery classes now have a <xref:System.ServiceModel.Discovery.DiscoveryVersion> property and take a <xref:System.ServiceModel.Discovery.DiscoveryVersion> argument in their constructors:</span></span>  
  
- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
  
- <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
  
- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
  
### <a name="discoveryversionwsdiscoveryapril2005"></a><span data-ttu-id="09a90-110">DiscoveryVersion.WSDiscoveryApril2005</span><span class="sxs-lookup"><span data-stu-id="09a90-110">DiscoveryVersion.WSDiscoveryApril2005</span></span>  
 <span data-ttu-id="09a90-111">提供する<xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005>コンス トラクターとパラメーターにより、実装で、Ws-discovery プロトコルの April2005 バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="09a90-111">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> as a constructor parameter makes the implementation use the April2005 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="09a90-112">このバージョンは、WS-Discovery プロトコル仕様の発行済みバージョンに対応します。</span><span class="sxs-lookup"><span data-stu-id="09a90-112">This version corresponds to the published version of the WS-Discovery protocol specification.</span></span> <span data-ttu-id="09a90-113">このバージョンは、WS-Discovery の April2005 バージョンを利用しているレガシ アプリケーションとの相互運用時に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a90-113">This version should be used to interoperate with legacy application utilizing the April2005 version of WS-Discovery.</span></span>  
  
### <a name="discoveryversionwsdiscovery11"></a><span data-ttu-id="09a90-114">DiscoveryVersion.WSDiscovery11</span><span class="sxs-lookup"><span data-stu-id="09a90-114">DiscoveryVersion.WSDiscovery11</span></span>  
 <span data-ttu-id="09a90-115">Api で使用される既定の探索バージョンは<xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>します。</span><span class="sxs-lookup"><span data-stu-id="09a90-115">The default discovery version used by the APIs is <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>.</span></span> <span data-ttu-id="09a90-116">これは、現在標準化されている WS-Discovery プロトコルのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="09a90-116">This is the current standardized version of the WS-Discovery protocol.</span></span>  
  
## <a name="discoveryversionwsdiscoverycd1"></a><span data-ttu-id="09a90-117">DiscoveryVersion.WSDiscoveryCD1</span><span class="sxs-lookup"><span data-stu-id="09a90-117">DiscoveryVersion.WSDiscoveryCD1</span></span>  
 <span data-ttu-id="09a90-118">コンストラクターのパラメーターとして <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> を使用することで、WS-Discovery プロトコルの Committee Draft 1 バージョンが実装で使用されます。</span><span class="sxs-lookup"><span data-stu-id="09a90-118">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> as a constructor parameter makes the implementation use the committee draft 1 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="09a90-119">このバージョンのプロトコルは、WS-Discovery プロトコルの CD1 バージョンを利用している実装との相互運用時に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a90-119">This version of the protocol should be used to interoperate with implementations running the CD1 version of the WS-Discovery protocol.</span></span>  
  
## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a><span data-ttu-id="09a90-120">単一のサービス ホスト上にある異なる探索バージョン用の複数の UDP 探索エンドポイントのサポート</span><span class="sxs-lookup"><span data-stu-id="09a90-120">Supporting Multiple UDP Discovery Endpoints for Different Discovery Versions on a Single Service Host</span></span>  
 <span data-ttu-id="09a90-121">単一のサービス ホスト上にある、異なる探索バージョン用の複数の UDP 探索エンドポイントを公開する場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a90-121">You may want to expose multiple UDP Discovery Endpoints for different discovery versions on a single service host.</span></span> <span data-ttu-id="09a90-122">このような場合、UDP 探索エンドポイントごとに一意のアドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a90-122">To do this you must specify a unique address for each UDP discovery endpoint.</span></span> <span data-ttu-id="09a90-123">その方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="09a90-123">The following example shows how to do this.</span></span>  
  
```  
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);  
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
  
newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");  
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionAril2005");  
  
serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);  
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);  
```
