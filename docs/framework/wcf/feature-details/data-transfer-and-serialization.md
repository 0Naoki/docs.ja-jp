---
title: データ転送とシリアル化
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 1eefd82a149d0bc215ca441e92c7d737a744b1e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61856558"
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="1b8c8-102">データ転送とシリアル化</span><span class="sxs-lookup"><span data-stu-id="1b8c8-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="1b8c8-103">接続されたシステムでは、サービスとクライアントのタスクの実行は、データの交換に依存します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="1b8c8-104">サービスまたはクライアントの開発者は、効率的かつ簡単に維持されるアプリケーションを作成するには、Windows Communication Foundation (WCF) がデータとデータのシリアル化を処理する方法も理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-104">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b8c8-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1b8c8-105">In This Section</span></span>  
 [<span data-ttu-id="1b8c8-106">サービス コントラクトでのデータ転送の指定</span><span class="sxs-lookup"><span data-stu-id="1b8c8-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="1b8c8-107">サービスでのデータ転送の基本的な概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="1b8c8-108">データ コントラクトの使用</span><span class="sxs-lookup"><span data-stu-id="1b8c8-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="1b8c8-109">データ コントラクトの定義と、その作成方法と使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="1b8c8-110">データ コントラクト シリアライザー</span><span class="sxs-lookup"><span data-stu-id="1b8c8-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="1b8c8-111"><xref:System.Runtime.Serialization.DataContractSerializer> クラス、または <xref:System.Runtime.Serialization.XmlObjectSerializer> クラスの拡張機能で、データのシリアル化を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="1b8c8-112">XmlSerializer クラスの使用</span><span class="sxs-lookup"><span data-stu-id="1b8c8-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="1b8c8-113"><xref:System.Xml.Serialization.XmlSerializer> クラスの代わりに、<xref:System.Runtime.Serialization.DataContractSerializer> クラスを使う方法とその理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="1b8c8-114">メッセージ コントラクトの使用</span><span class="sxs-lookup"><span data-stu-id="1b8c8-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="1b8c8-115">メッセージ コントラクトで SOAP メッセージを詳細に制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="1b8c8-116">メッセージ クラスの使用</span><span class="sxs-lookup"><span data-stu-id="1b8c8-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="1b8c8-117">メッセージ クラス機能の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="1b8c8-118">フィルター処理</span><span class="sxs-lookup"><span data-stu-id="1b8c8-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="1b8c8-119">各種の条件に基づいて、メッセージを事前処理できるフィルター処理について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="1b8c8-120">大規模データとストリーミング</span><span class="sxs-lookup"><span data-stu-id="1b8c8-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="1b8c8-121">バイナリ ファイルなど、大きなデータ ブロックを送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="1b8c8-122">セキュリティに関するデータの考慮事項</span><span class="sxs-lookup"><span data-stu-id="1b8c8-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="1b8c8-123">データの転送とシリアル化をプログラムするときに注意する必要のある項目について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="1b8c8-124">データ転送のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="1b8c8-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="1b8c8-125">WCF でのデータ転送の設計全体のビューについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-125">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1b8c8-126">参照</span><span class="sxs-lookup"><span data-stu-id="1b8c8-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="1b8c8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b8c8-127">Related Sections</span></span>  
 [<span data-ttu-id="1b8c8-128">エンコーダーとシリアライザーの拡張</span><span class="sxs-lookup"><span data-stu-id="1b8c8-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="1b8c8-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b8c8-129">See also</span></span>

- [<span data-ttu-id="1b8c8-130">ベスト プラクティス:データ コントラクトのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="1b8c8-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
- [<span data-ttu-id="1b8c8-131">サービスのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="1b8c8-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
