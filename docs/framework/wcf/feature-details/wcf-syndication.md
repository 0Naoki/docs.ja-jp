---
title: WCF 配信
ms.date: 03/30/2017
helpviewer_keywords:
- syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
ms.openlocfilehash: c7fefb49cf70b9f3c55937e7be06eca212af364d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530906"
---
# <a name="wcf-syndication"></a><span data-ttu-id="914e8-102">WCF 配信</span><span class="sxs-lookup"><span data-stu-id="914e8-102">WCF Syndication</span></span>
<span data-ttu-id="914e8-103">Windows Communication Foundation (WCF) は、Atom、RSS、または他のカスタム形式で配信フィードを簡単に操作を使用すると、読み取りと作成だけでなく、サービス エンドポイントで公開するサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="914e8-103">Windows Communication Foundation (WCF) provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="914e8-104">このセクションのトピックでは、配信用のこのプログラミング モデルについて詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="914e8-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="914e8-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="914e8-105">In This Section</span></span>  
 [<span data-ttu-id="914e8-106">WCF 配信の概要</span><span class="sxs-lookup"><span data-stu-id="914e8-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="914e8-107">WCF で提供される配信サポートの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="914e8-107">Provides an overview of syndication support provided by WCF.</span></span>  
  
 [<span data-ttu-id="914e8-108">配信のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="914e8-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="914e8-109">オブジェクト モデルのクラスと配信の拡張について説明します。</span><span class="sxs-lookup"><span data-stu-id="914e8-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="914e8-110">WCF 配信オブジェクト モデルを Atom や RSS に割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="914e8-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="914e8-111">WCF 配信オブジェクト モデルにおけるフィードの表現方法と RSS フィードおよび ATOM フィードへの変換方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="914e8-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="914e8-112">方法: 基本的な RSS フィードを作成します。</span><span class="sxs-lookup"><span data-stu-id="914e8-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="914e8-113">基本的な RSS フィードを利用できるようにするサービスの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="914e8-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="914e8-114">方法: 基本的な Atom フィードを作成します。</span><span class="sxs-lookup"><span data-stu-id="914e8-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="914e8-115">基本的な ATOM フィードを利用できるようにするサービスの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="914e8-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="914e8-116">方法: Atom の両方としてフィードを公開および RSS</span><span class="sxs-lookup"><span data-stu-id="914e8-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="914e8-117">ATOM と RSS で同じフィードを利用できるようにするサービスの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="914e8-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="914e8-118">配信の拡張</span><span class="sxs-lookup"><span data-stu-id="914e8-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="914e8-119">カスタム要素と属性を配信フィードに追加するメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="914e8-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="914e8-120">参照</span><span class="sxs-lookup"><span data-stu-id="914e8-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="914e8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="914e8-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="914e8-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="914e8-122">See also</span></span>
- [<span data-ttu-id="914e8-123">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="914e8-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="914e8-124">部分信頼</span><span class="sxs-lookup"><span data-stu-id="914e8-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
