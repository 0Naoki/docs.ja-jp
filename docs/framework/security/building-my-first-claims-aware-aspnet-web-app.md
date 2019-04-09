---
title: クレーム対応の ASP.NET Web アプリケーションを初めて構築する
ms.date: 03/30/2017
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
author: BrucePerlerMS
ms.openlocfilehash: b6be3d84a292e5f14e1cdc70a181e8fd2c065a68
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151373"
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a><span data-ttu-id="241c4-102">クレーム対応の ASP.NET Web アプリケーションを初めて構築する</span><span class="sxs-lookup"><span data-stu-id="241c4-102">Building My First Claims-Aware ASP.NET Web Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="241c4-103">対象</span><span class="sxs-lookup"><span data-stu-id="241c4-103">Applies To</span></span>  
  
-   <span data-ttu-id="241c4-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="241c4-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="241c4-105">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="241c4-105">ASP.NET</span></span>  
  
 <span data-ttu-id="241c4-106">このトピックでは、WIF を使用してクレーム対応 ASP.NET Web アプリケーションをビルドするシナリオの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="241c4-106">This topic outlines the scenario of building claims-aware ASP.NET web applications using WIF.</span></span> <span data-ttu-id="241c4-107">クレーム対応アプリケーションのシナリオには、通常、アプリケーション、エンド ユーザー、セキュリティ トークン サービス (STS) の 3 つ参加要素が存在します。</span><span class="sxs-lookup"><span data-stu-id="241c4-107">There are usually three participants in a claims-aware application scenario: the application itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="241c4-108">次の図は、このシナリオについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="241c4-108">The following figure describes this scenario:</span></span>  
  
 ![WIF 基本 Web アプリのコンポーネントを示す図。](./media/building-my-first-claims-aware-aspnet-web-app/windows-identity-foundation-basic-web-application.gif)  
  
1.  <span data-ttu-id="241c4-110">クレーム対応アプリケーションは、認証されていない要求を WIF で特定し、その要求を STS にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="241c4-110">The claims-aware application uses WIF to identify unauthenticated requests and to redirect them to the STS.</span></span>  
  
2.  <span data-ttu-id="241c4-111">エンド ユーザーは資格情報を STS に提供します。認証が正常に行われると、STS はそのユーザーに対してトークンを発行します。</span><span class="sxs-lookup"><span data-stu-id="241c4-111">The end user provides credentials to the STS and upon successful authentication the user is issued a token by the STS.</span></span>  
  
3.  <span data-ttu-id="241c4-112">ユーザーは、要求内の STS 発行のトークンと共に、STS からクレーム対応アプリケーションにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="241c4-112">The user is redirected from the STS to the claims-aware application with the STS-issued token in the request.</span></span>  
  
4.  <span data-ttu-id="241c4-113">クレーム対応アプリケーションは、STS とその STS が発行したトークンを信頼するように構成され、</span><span class="sxs-lookup"><span data-stu-id="241c4-113">The claims-aware application is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="241c4-114">WIF を使用してトークンを検証し、解析します。</span><span class="sxs-lookup"><span data-stu-id="241c4-114">The claims-aware application uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="241c4-115">開発者は、承認の実装などのアプリケーションのニーズに応じて、適切な WIF API と種類 (**ClaimsPrincpal** など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="241c4-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincpal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="241c4-116">.NET 4.5 以降、WIF は .NET Framework パッケージに含まれています。</span><span class="sxs-lookup"><span data-stu-id="241c4-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="241c4-117">.NET Framework で直接 WIF クラスを使用できるようになったため、.NET でクレームベースの ID をより深く統合できるようになり、クレームを簡単に使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="241c4-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="241c4-118">WIF 4.5 を使用すると、クレーム対応アプリケーションの開発を開始する目的で、帯域外コンポーネントをインストールする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="241c4-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="241c4-119">WIF クラスは、さまざまなアセンブリに分散されています。主なものは、System.Security.Claims、System.IdentityModel、および System.IdentityModel.Services です。</span><span class="sxs-lookup"><span data-stu-id="241c4-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="241c4-120">STS は、認証が正常に行われたときにトークンを発行するサービスです。</span><span class="sxs-lookup"><span data-stu-id="241c4-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="241c4-121">Microsoft では、2 つの業界標準 STS を提供します。</span><span class="sxs-lookup"><span data-stu-id="241c4-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   [<span data-ttu-id="241c4-122">Active Directory フェデレーション サービス (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="241c4-122">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/?LinkID=247516)
  
-   [<span data-ttu-id="241c4-123">Windows Azure の Access Control Service (ACS)</span><span class="sxs-lookup"><span data-stu-id="241c4-123">Windows Azure Access Control Service (ACS)</span></span>](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 <span data-ttu-id="241c4-124">AD FS 2.0 は、Windows Server R2 に含まれており、設置型シナリオの STS として使用できます。</span><span class="sxs-lookup"><span data-stu-id="241c4-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="241c4-125">ACS は、Microsoft Azure プラットフォームの一部として提供されるクラウド サービスです。</span><span class="sxs-lookup"><span data-stu-id="241c4-125">ACS is a cloud service, offered as part of the Windows Azure Platform.</span></span> <span data-ttu-id="241c4-126">テストまたは学習の目的で、他の STS を使用して、クレーム対応アプリケーションをビルドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="241c4-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="241c4-127">たとえばの一部であるローカルの開発用 STS を使用することができます、 [Identity and Access Tool for Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849)は自由に利用できるオンライン。</span><span class="sxs-lookup"><span data-stu-id="241c4-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="241c4-128">WIF を使用してクレーム対応 ASP.NET アプリケーションを初めてビルドするには、次のいずれかの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="241c4-128">To build your first claims-aware ASP.NET application using WIF, follow the instructions in one of the following:</span></span>  
  
-   [<span data-ttu-id="241c4-129">方法: WIF を使用してクレーム対応 ASP.NET MVC Web アプリケーションをビルドする</span><span class="sxs-lookup"><span data-stu-id="241c4-129">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [<span data-ttu-id="241c4-130">方法: WIF を使用してクレーム対応 ASP.NET Web フォーム アプリケーションをビルドする</span><span class="sxs-lookup"><span data-stu-id="241c4-130">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [<span data-ttu-id="241c4-131">方法: フォームベースの認証を使用するクレーム対応 ASP.NET アプリケーションをビルドする</span><span class="sxs-lookup"><span data-stu-id="241c4-131">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="241c4-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="241c4-132">See also</span></span>

- [<span data-ttu-id="241c4-133">WIF の概要</span><span class="sxs-lookup"><span data-stu-id="241c4-133">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
