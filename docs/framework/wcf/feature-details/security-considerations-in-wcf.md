---
title: WCF でのセキュリティの考慮事項
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
author: BrucePerlerMS
ms.openlocfilehash: f26369a567e89fc502f777383c22e74b96fe503c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47109512"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="04c2d-102">WCF でのセキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="04c2d-102">Security Considerations in WCF</span></span>
<span data-ttu-id="04c2d-103">このセクションのトピックでは、Windows Communication Foundation (WCF) アプリケーションを設計するときに考慮すべきさまざまなセキュリティ関連の項目を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="04c2d-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04c2d-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="04c2d-104">In This Section</span></span>  
 [<span data-ttu-id="04c2d-105">情報の漏えい</span><span class="sxs-lookup"><span data-stu-id="04c2d-105">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 <span data-ttu-id="04c2d-106">情報が開示または攻撃されるさまざまな方法、およびそれを軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c2d-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="04c2d-107">権限の昇格</span><span class="sxs-lookup"><span data-stu-id="04c2d-107">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 <span data-ttu-id="04c2d-108">最初に付与されたものよりも高い承認アクセス許可を攻撃者に与えることの影響、およびそれを軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c2d-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="04c2d-109">サービス拒否</span><span class="sxs-lookup"><span data-stu-id="04c2d-109">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 <span data-ttu-id="04c2d-110">システムがメッセージを適切に処理できない場合の影響、およびそれを軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c2d-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="04c2d-111">改変</span><span class="sxs-lookup"><span data-stu-id="04c2d-111">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 <span data-ttu-id="04c2d-112">メッセージの改ざんやメッセージの配信先の変更、およびそれを軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c2d-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="04c2d-113">リプレイ攻撃</span><span class="sxs-lookup"><span data-stu-id="04c2d-113">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 <span data-ttu-id="04c2d-114">攻撃者がメッセージのストリームを送受信者間でコピーし、そのストリームを 1 つ以上の第三者に対してリプレイすることによる影響、およびそれを軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c2d-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="04c2d-115">セキュリティで保護されたセッションに関するセキュリティの検討</span><span class="sxs-lookup"><span data-stu-id="04c2d-115">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="04c2d-116">セキュリティで保護されたセッションを実装する場合に、セキュリティに影響を及ぼす次の項目について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c2d-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="04c2d-117">サポートされていないシナリオ:</span><span class="sxs-lookup"><span data-stu-id="04c2d-117">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 <span data-ttu-id="04c2d-118">セキュリティの特定の側面がサポートされないため、避けたり配慮したりする必要のあるさまざまなシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="04c2d-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="04c2d-119">参照</span><span class="sxs-lookup"><span data-stu-id="04c2d-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="04c2d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="04c2d-120">Related Sections</span></span>  
 [<span data-ttu-id="04c2d-121">セキュリティ ガイドラインとベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="04c2d-121">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="04c2d-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="04c2d-122">See Also</span></span>  
 [<span data-ttu-id="04c2d-123">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="04c2d-123">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
