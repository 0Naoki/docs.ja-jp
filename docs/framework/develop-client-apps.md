---
title: .NET Framework を使用した Windows ベースのクライアント アプリケーションの開発
ms.date: 01/09/2018
helpviewer_keywords:
- client application services
- applications [Windows Forms]
- Windows Presentation Foundation, in Visual Studio
- WPF, in Visual Studio
- Windows applications
- rich client applications
- .NET applications, Windows applications
- Visual Basic code, creating applications
- Visual C#, creating applications
- client/server applications, Windows applications
ms.assetid: 2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68
ms.openlocfilehash: 27bd71d4caf59a44a45c70217aa351cf43a5c1c7
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2018
ms.locfileid: "49349122"
---
# <a name="developing-client-applications-with-the-net-framework"></a><span data-ttu-id="53467-102">.NET Framework を使用したクライアント アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="53467-102">Developing client applications with the .NET Framework</span></span>

<span data-ttu-id="53467-103">.NET Framework で Windows ベースのアプリケーションを開発する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="53467-103">There are several ways to develop Windows-based applications with the .NET Framework.</span></span> <span data-ttu-id="53467-104">次のツールおよびフレームワークのいずれかを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="53467-104">You can use any of these tools and frameworks:</span></span> 

* [<span data-ttu-id="53467-105">ユニバーサル Windows プラットフォーム (UWP)</span><span class="sxs-lookup"><span data-stu-id="53467-105">Universal Windows Platform (UWP)</span></span>](https://developer.microsoft.com/windows/apps)
* [<span data-ttu-id="53467-106">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="53467-106">Windows Presentation Foundation (WPF)</span></span>](../../docs/framework/wpf/index.md)
* [<span data-ttu-id="53467-107">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="53467-107">Windows Forms</span></span>](../../docs/framework/winforms/index.md)

<span data-ttu-id="53467-108">このセクションには、Windows Presentation Foundation または Windows Forms を使用して Windows ベースのアプリケーションを作成する方法について説明しているトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="53467-108">This section contains topics that describe how to create Windows-based applications by using Windows Presentation Foundation or by using Windows Forms.</span></span> <span data-ttu-id="53467-109">ただし、.NET Framework を使用して Web アプリケーションを作成したり、コンピューターやデバイス向けのクライアント アプリケーションを作成したりして、Microsoft Store で公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="53467-109">However, you can also create web applications using the .NET Framework, and client applications for computers or devices that you make available through the Microsoft Store.</span></span>
 
## <a name="in-this-section"></a><span data-ttu-id="53467-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="53467-110">In this section</span></span>

[<span data-ttu-id="53467-111">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="53467-111">Windows Presentation Foundation</span></span>](../../docs/framework/wpf/index.md)  
<span data-ttu-id="53467-112">WPF を使用したアプリケーション開発の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="53467-112">Provides information about developing applications by using WPF.</span></span>

[<span data-ttu-id="53467-113">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="53467-113">Windows Forms</span></span>](../../docs/framework/winforms/index.md)  
<span data-ttu-id="53467-114">Windows フォームを使用したアプリケーション開発の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="53467-114">Provides information about developing applications by using Windows Forms.</span></span>

[<span data-ttu-id="53467-115">共通クライアント技術</span><span class="sxs-lookup"><span data-stu-id="53467-115">Common Client Technologies</span></span>](../../docs/framework/common-client-technologies/index.md)  
<span data-ttu-id="53467-116">クライアント アプリケーションを開発する場合に使用できる、その他の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53467-116">Provides information about additional technologies that can be used when developing client applications.</span></span>

## <a name="related-sections"></a><span data-ttu-id="53467-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="53467-117">Related sections</span></span>

[<span data-ttu-id="53467-118">ユニバーサル Windows プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="53467-118">Universal Windows Platform</span></span>](https://developer.microsoft.com/windows/apps)  
<span data-ttu-id="53467-119">Microsoft Store を介してユーザーが利用できる Windows 10 用のアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53467-119">Describes how to create applications for Windows 10 that you can make available to users through the Windows Store.</span></span>

[<span data-ttu-id="53467-120">UWP アプリ用 .NET</span><span class="sxs-lookup"><span data-stu-id="53467-120">.NET for UWP apps</span></span>](https://msdn.microsoft.com/library/windows/apps/mt185501.aspx)  
<span data-ttu-id="53467-121">Windows コンピューターとデバイスに展開できるストア アプリ用 .NET Framework のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="53467-121">Describes the .NET Framework support for Store apps, which can be deployed to Windows computers and devices.</span></span>

<span data-ttu-id="53467-122">[Windows Phone Silverlight 用の .NET API](https://docs.microsoft.com/previous-versions/windows/apps/jj207211\(v=vs.105\))</span><span class="sxs-lookup"><span data-stu-id="53467-122">[.NET API for Windows Phone Silverlight](https://docs.microsoft.com/previous-versions/windows/apps/jj207211\(v=vs.105\))</span></span>  
<span data-ttu-id="53467-123">Windows Phone Silverlight を使用したアプリを構築するために利用できる .NET Framework API の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="53467-123">Lists the .NET Framework APIs you can use for building apps with Windows Phone Silverlight.</span></span>
  
[<span data-ttu-id="53467-124">複数のプラットフォームの開発</span><span class="sxs-lookup"><span data-stu-id="53467-124">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
<span data-ttu-id="53467-125">複数の種類のクライアント アプリを対象にするために .NET Framework を使用できるさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53467-125">Describes the different methods you can use the .NET Framework to target multiple client app types.</span></span>

[<span data-ttu-id="53467-126">ASP.NET Web サイト入門</span><span class="sxs-lookup"><span data-stu-id="53467-126">Get Started with ASP.NET Web Sites</span></span>](https://www.asp.net/get-started/websites)  
<span data-ttu-id="53467-127">ASP.NET を使用して Web アプリを開発する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53467-127">Describes the ways you can develop web apps using ASP.NET.</span></span>

## <a name="see-also"></a><span data-ttu-id="53467-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="53467-128">See also</span></span>

[<span data-ttu-id="53467-129">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="53467-129">.NET Standard</span></span>](../../docs/standard/net-standard.md)  
[<span data-ttu-id="53467-130">概要</span><span class="sxs-lookup"><span data-stu-id="53467-130">Overview</span></span>](../../docs/framework/get-started/overview.md)  
[<span data-ttu-id="53467-131">開発ガイド</span><span class="sxs-lookup"><span data-stu-id="53467-131">Development Guide</span></span>](../../docs/framework/development-guide.md)  
[<span data-ttu-id="53467-132">Windows サービス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="53467-132">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)  
