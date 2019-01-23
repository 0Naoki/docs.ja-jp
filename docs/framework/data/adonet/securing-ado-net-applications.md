---
title: ADO.NET アプリケーションのセキュリティ保護
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: 935d963ed19175518191006c2cc367f88d69e2aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585368"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="8461e-102">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="8461e-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="8461e-103">ユーザー入力の検証を怠るなど、コーディング時に陥りやすい基本的なミスを防ぐだけでは、安全な ADO.NET アプリケーションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="8461e-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="8461e-104">データにアクセスするアプリケーションには、機密データの取得、操作、破壊など、攻撃者に攻略される可能性がある障害点が多数あります。</span><span class="sxs-lookup"><span data-stu-id="8461e-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="8461e-105">そのため、アプリケーションの設計フェーズで行う脅威のモデリングのプロセスから、アプリケーションの最終的な配置と継続的な保守に至るまで、セキュリティのすべての側面を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8461e-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="8461e-106">.NET Framework には、データベース アプリケーションのセキュリティを確保し、管理するのに有用なクラス、サービス、およびツールが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="8461e-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="8461e-107">共通言語ランタイム (CLR) によって、コードを実行するためのタイプ セーフな環境が実現され、それと同時に、コード アクセス セキュリティ (CAS) によって、マネージド コードのアクセス許可はより制限されています。</span><span class="sxs-lookup"><span data-stu-id="8461e-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="8461e-108">攻撃者によってもたらされる可能性のある損害は、安全なデータ アクセスのためのコーディング方法に従うことによって最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="8461e-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="8461e-109">データベースなどのアンマネージ リソースを扱う場合、安全なコードを作成したとしても、自ら招いたセキュリティ ホールを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="8461e-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="8461e-110">SQL Server を含め、ほとんどのサーバー データベースには、正しく実装することによってセキュリティを強化できる独自のセキュリティ システムがあります。</span><span class="sxs-lookup"><span data-stu-id="8461e-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="8461e-111">しかし、データ ソースがいかに堅牢なセキュリティ システムを備えていたとしても、それが適切に構成されていなければ攻撃を防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="8461e-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8461e-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8461e-112">In This Section</span></span>  
 [<span data-ttu-id="8461e-113">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="8461e-113">Security Overview</span></span>](../../../../docs/framework/data/adonet/security-overview.md)  
 <span data-ttu-id="8461e-114">安全な ADO.NET アプリケーションを設計するための推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="8461e-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="8461e-115">安全なデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="8461e-115">Secure Data Access</span></span>](../../../../docs/framework/data/adonet/secure-data-access.md)  
 <span data-ttu-id="8461e-116">セキュリティで保護されたデータ ソースのデータを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8461e-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="8461e-117">安全なクライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8461e-117">Secure Client Applications</span></span>](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 <span data-ttu-id="8461e-118">クライアント アプリケーションのセキュリティに関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="8461e-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="8461e-119">コード アクセス セキュリティと ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8461e-119">Code Access Security and ADO.NET</span></span>](../../../../docs/framework/data/adonet/code-access-security.md)  
 <span data-ttu-id="8461e-120">CAS を使用して ADO.NET コードを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8461e-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="8461e-121">部分信頼の使用方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="8461e-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="8461e-122">プライバシーとデータ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8461e-122">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 <span data-ttu-id="8461e-123">ADO.NET アプリケーションの暗号化オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8461e-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8461e-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="8461e-124">Related Sections</span></span>  
 [<span data-ttu-id="8461e-125">SQL Server のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="8461e-125">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="8461e-126">開発者の観点から SQL Server のセキュリティ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="8461e-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="8461e-127">セキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="8461e-127">Security Considerations</span></span>](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 <span data-ttu-id="8461e-128">Entity Framework アプリケーションのセキュリティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8461e-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="8461e-129">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8461e-129">Security</span></span>](../../../../docs/standard/security/index.md)  
 <span data-ttu-id="8461e-130">.NET のセキュリティをあらゆる観点から説明したトピックへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8461e-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 [<span data-ttu-id="8461e-131">セキュリティ ツール</span><span class="sxs-lookup"><span data-stu-id="8461e-131">Security Tools</span></span>](https://msdn.microsoft.com/library/2a3eb98a-2de6-4fba-b41c-01a74d354c11)  
 <span data-ttu-id="8461e-132">セキュリティ保護およびセキュリティ ポリシーの管理に使用する .NET Framework ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8461e-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 [<span data-ttu-id="8461e-133">セキュリティで保護されたアプリケーションを作成するためのリソース</span><span class="sxs-lookup"><span data-stu-id="8461e-133">Resources for Creating Secure Applications</span></span>](https://msdn.microsoft.com/library/0ebf5f69-76f2-498a-a2df-83cf3443e132)  
 <span data-ttu-id="8461e-134">安全なアプリケーションを作成するためのトピックへのリンク集です。</span><span class="sxs-lookup"><span data-stu-id="8461e-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="8461e-135">セキュリティ参考文献</span><span class="sxs-lookup"><span data-stu-id="8461e-135">Security Bibliography</span></span>](/visualstudio/ide/security-bibliography)  
 <span data-ttu-id="8461e-136">オンラインまたは出版物として提供されている外部リソースへのリンク集です。</span><span class="sxs-lookup"><span data-stu-id="8461e-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8461e-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="8461e-137">See also</span></span>
- [<span data-ttu-id="8461e-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8461e-138">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="8461e-139">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="8461e-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
