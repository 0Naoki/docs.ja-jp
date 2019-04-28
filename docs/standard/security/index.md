---
title: .NET でのセキュリティ
ms.date: 06/04/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, security
- security [.NET], about security
- application development [.NET], security
- security [.NET Framework]
- security [.NET]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e60f463d5a691cb84a30c169e471aa905b2db17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61860556"
---
# <a name="security-in-net"></a><span data-ttu-id="13b28-102">.NET でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="13b28-102">Security in .NET</span></span>
<span data-ttu-id="13b28-103">共通言語ランタイムと .NET は、保護されたリソースの多くの便利なクラスと開発者がセキュリティで保護されたコードを簡単に記述し、システム管理者にアクセスできるように、コードに付与されるアクセス許可のカスタマイズを有効にするサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="13b28-103">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="13b28-104">さらに、ランタイムと .NET は、暗号化とロールベースのセキュリティの使用を容易にする便利なクラスおよびサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="13b28-104">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13b28-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="13b28-105">In This Section</span></span>  

 [<span data-ttu-id="13b28-106">セキュリティの基本概念</span><span class="sxs-lookup"><span data-stu-id="13b28-106">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="13b28-107">共通言語ランタイムのセキュリティ機能の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="13b28-107">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="13b28-108">このセクションは開発者およびシステム管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="13b28-108">This section is of interest to developers and system administrators.</span></span>  
  
 [<span data-ttu-id="13b28-109">ロール ベースのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="13b28-109">Role-Based Security</span></span>](../../../docs/standard/security/role-based-security.md)  
 <span data-ttu-id="13b28-110">コード内でロール ベースのセキュリティと対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="13b28-110">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="13b28-111">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="13b28-111">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="13b28-112">暗号モデル</span><span class="sxs-lookup"><span data-stu-id="13b28-112">Cryptography Model</span></span>](../../../docs/standard/security/cryptography-model.md)  
 <span data-ttu-id="13b28-113">.NET によって提供される暗号化サービスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="13b28-113">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="13b28-114">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="13b28-114">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="13b28-115">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="13b28-115">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="13b28-116">信頼性の高い .NET アプリケーションを作成するためのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="13b28-116">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="13b28-117">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="13b28-117">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="13b28-118">アンマネージ コードの安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="13b28-118">Secure Coding Guidelines for Unmanaged Code</span></span>](../../../docs/framework/security/secure-coding-guidelines-for-unmanaged-code.md)  
 <span data-ttu-id="13b28-119">アンマネージ コードを呼び出す際のベスト プラクティスとセキュリティに関する注意事項について、いくつか説明します。</span><span class="sxs-lookup"><span data-stu-id="13b28-119">Describes some of the best practices and security concerns when calling unmanaged code.</span></span>  
  
 [<span data-ttu-id="13b28-120">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="13b28-120">Windows Identity Foundation</span></span>](../../../docs/framework/security/index.md)  
 <span data-ttu-id="13b28-121">アプリケーションでクレーム ベースの ID を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="13b28-121">Describes how you can implement claims-based identity in your applications.</span></span>  

<span data-ttu-id="13b28-122">[セキュリティの変更](../../../docs/framework/security/security-changes.md).NET Framework セキュリティ システムの重要な変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="13b28-122">[Security Changes](../../../docs/framework/security/security-changes.md) Describes important changes to the .NET Framework security system.</span></span>

## <a name="related-sections"></a><span data-ttu-id="13b28-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="13b28-123">Related Sections</span></span>  
 [<span data-ttu-id="13b28-124">開発ガイド</span><span class="sxs-lookup"><span data-stu-id="13b28-124">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
 <span data-ttu-id="13b28-125">アプリケーションの作成、構成、デバッグ、セキュリティ、配置、および動的プログラミング、相互運用性、拡張性、メモリ管理、スレッド処理に関する情報を含む、アプリケーション開発用の主要な技術領域とタスクのすべてについての手引書です。</span><span class="sxs-lookup"><span data-stu-id="13b28-125">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
