---
title: WCF での承認
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 8e7632dda1a1bd2b60b71c385ad58c23e4207534
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532104"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="2543f-102">WCF での承認</span><span class="sxs-lookup"><span data-stu-id="2543f-102">Authorization in WCF</span></span>
<span data-ttu-id="2543f-103">承認は、サービスやファイルなどのリソースへのアクセスと権限を制御するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="2543f-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="2543f-104">このセクションのトピックでは、Windows Communication Foundation (WCF) でさまざまな方法でこの基本的なタスクを実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="2543f-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2543f-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2543f-105">In This Section</span></span>  
 [<span data-ttu-id="2543f-106">アクセス制御機構</span><span class="sxs-lookup"><span data-stu-id="2543f-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="2543f-107">推奨される使用して、WCF 承認メカニズムの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="2543f-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="2543f-108">方法: PrincipalPermissionAttribute クラスでアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="2543f-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="2543f-109"><xref:System.Security.Permissions.PrincipalPermissionAttribute> を使用してサービスへのアクセスを制限するプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="2543f-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="2543f-110">方法 : ASP.NET のロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="2543f-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="2543f-111">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] のロール プロバイダー機能を使用できるようにサービスを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2543f-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="2543f-112">方法 : ASP.NET の承認マネージャー ロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="2543f-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="2543f-113"> は、承認マネージャーを使って Web サイトの承認を管理できます。</span><span class="sxs-lookup"><span data-stu-id="2543f-113"> can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="2543f-114">WCF を活用できる同様に、 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization マネージャー クライアントの承認の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="2543f-114">WCF can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="2543f-115">ID モデルを使用したクレームと承認の管理</span><span class="sxs-lookup"><span data-stu-id="2543f-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="2543f-116">ID モデル インフラストラクチャをクレーム ベースの承認に使用する際の基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="2543f-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="2543f-117">委任と偽装</span><span class="sxs-lookup"><span data-stu-id="2543f-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="2543f-118">委任と偽装の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2543f-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2543f-119">参照</span><span class="sxs-lookup"><span data-stu-id="2543f-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="2543f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2543f-120">Related Sections</span></span>  
 [<span data-ttu-id="2543f-121">認証</span><span class="sxs-lookup"><span data-stu-id="2543f-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="2543f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2543f-122">See Also</span></span>  
 [<span data-ttu-id="2543f-123">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="2543f-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="2543f-124">Windows Server App Fabric のセキュリティ モデル</span><span class="sxs-lookup"><span data-stu-id="2543f-124">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
