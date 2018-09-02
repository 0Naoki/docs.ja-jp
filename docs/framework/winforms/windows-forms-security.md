---
title: Windows フォームのセキュリティ
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: 75016e9e04cf47782add18c87f7c677931743a4e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43397251"
---
# <a name="windows-forms-security"></a><span data-ttu-id="92e2d-102">Windows フォームのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="92e2d-102">Windows Forms Security</span></span>
<span data-ttu-id="92e2d-103">Windows フォームには、コード ベース (セキュリティ レベルは、コードを実行しているユーザーに関係なく、コードの設定) であるセキュリティ モデルが機能します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="92e2d-104">これは既に、コンピューター システム上の場所に可能性のあるすべてのセキュリティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="92e2d-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="92e2d-105">これらは、(など、ゾーン ベースのセキュリティ Internet Explorer で使用可能なブラウザーやオペレーティング システム (Windows NT の資格情報に基づくセキュリティ) などを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="92e2d-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92e2d-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="92e2d-106">In This Section</span></span>  
 [<span data-ttu-id="92e2d-107">Windows フォームのセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="92e2d-107">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 <span data-ttu-id="92e2d-108">.NET Framework のセキュリティ モデルと、アプリケーションで Windows フォームのために必要な基本的な手順は、セキュリティで保護された、について説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="92e2d-109">Windows フォームにおけるファイルおよびデータへのより安全なアクセス</span><span class="sxs-lookup"><span data-stu-id="92e2d-109">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="92e2d-110">部分的に信頼された環境でファイルとデータにアクセスする方法をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="92e2d-111">Windows フォームでのより安全な印刷</span><span class="sxs-lookup"><span data-stu-id="92e2d-111">More Secure Printing in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="92e2d-112">部分的に信頼された環境での印刷機能にアクセスする方法をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="92e2d-113">Windows フォームのセキュリティに関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="92e2d-113">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="92e2d-114">ウィンドウ操作の実行、部分的に信頼された環境でのクリップボードの使用とアンマネージ コードへの呼び出しについて説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="92e2d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="92e2d-115">Related Sections</span></span>  
 [<span data-ttu-id="92e2d-116">NIB: 既定のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="92e2d-116">NIB: Default Security Policy</span></span>](https://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 <span data-ttu-id="92e2d-117">完全な信頼、ローカルのイントラネットとインターネットのアクセス許可セットで付与される既定のアクセス許可を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 [<span data-ttu-id="92e2d-118">NIB: 一般的なセキュリティ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="92e2d-118">NIB: General Security Policy Administration</span></span>](https://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 <span data-ttu-id="92e2d-119">.NET Framework のセキュリティ ポリシーの管理とアクセス許可の昇格についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="92e2d-120">危険なアクセス許可とポリシー管理</span><span class="sxs-lookup"><span data-stu-id="92e2d-120">Dangerous Permissions and Policy Administration</span></span>](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="92e2d-121">セキュリティ システムが回避される可能性があることができますの.net Framework のアクセス許可の一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="92e2d-122">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="92e2d-122">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="92e2d-123">安全に .NET Framework に対してコードを記述するためのベスト プラクティスを説明するトピックへのリンク。</span><span class="sxs-lookup"><span data-stu-id="92e2d-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 [<span data-ttu-id="92e2d-124">NIB: アクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-124">NIB: Requesting Permissions</span></span>](https://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 <span data-ttu-id="92e2d-125">どのようなアクセス許可をコードの実行に必要なランタイムに知らせるために属性の使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="92e2d-126">セキュリティの基本概念</span><span class="sxs-lookup"><span data-stu-id="92e2d-126">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="92e2d-127">コード セキュリティの基本的な側面を説明するトピックへのリンク。</span><span class="sxs-lookup"><span data-stu-id="92e2d-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="92e2d-128">コード アクセス セキュリティの基礎</span><span class="sxs-lookup"><span data-stu-id="92e2d-128">Code Access Security Basics</span></span>](../../../docs/framework/misc/code-access-security-basics.md)  
 <span data-ttu-id="92e2d-129">実行時のセキュリティ ポリシー、.NET Framework の操作の基礎について説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 [<span data-ttu-id="92e2d-130">NIB: がセキュリティ ポリシーを変更するタイミングを決定します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-130">NIB: Determining When to Modify Security Policy</span></span>](https://msdn.microsoft.com/library/af749b17-e461-409d-84b9-a3d44789db16)  
 <span data-ttu-id="92e2d-131">アプリケーションは、既定のセキュリティ ポリシーから分岐する必要がある場合を判断する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 [<span data-ttu-id="92e2d-132">NIB: セキュリティ ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-132">NIB: Deploying Security Policy</span></span>](https://msdn.microsoft.com/library/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 <span data-ttu-id="92e2d-133">セキュリティ ポリシーの変更をデプロイするための推奨される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="92e2d-133">Discusses the best manner for deploying security policy changes.</span></span>
