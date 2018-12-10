---
title: 高品質な .NET ライブラリの作成の概要
description: .NET ライブラリの構築を始めましょう。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 05466de1469fc765570b8250301e8404cd5df173
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145726"
---
# <a name="get-started"></a><span data-ttu-id="db4e2-103">作業開始</span><span class="sxs-lookup"><span data-stu-id="db4e2-103">Get started</span></span>

## <a name="cross-platform-targetingcross-platform-targetingmd"></a>[<span data-ttu-id="db4e2-104">クロス プラットフォーム ターゲット</span><span class="sxs-lookup"><span data-stu-id="db4e2-104">Cross-platform targeting</span></span>](./cross-platform-targeting.md)

<span data-ttu-id="db4e2-105">.NET Standard およびマルチ ターゲットを使用してクロスプラットフォーム ライブラリを作成する方法について。</span><span class="sxs-lookup"><span data-stu-id="db4e2-105">How to use .NET Standard and multi-targeting to create cross-platform libraries.</span></span> <span data-ttu-id="db4e2-106">.NET はさまざまな場所で実行されるため、優れた .NET ライブラリは、できるだけ多くのプラットフォームと開発者をサポートするために存続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db4e2-106">.NET runs in many places, and good .NET libraries should strive to support as many platforms and developers as possible.</span></span>

## <a name="strong-namingstrong-namingmd"></a>[<span data-ttu-id="db4e2-107">厳密な名前付け</span><span class="sxs-lookup"><span data-stu-id="db4e2-107">Strong naming</span></span>](./strong-naming.md)

<span data-ttu-id="db4e2-108">厳密な名前付けとその長所と短所について説明します。</span><span class="sxs-lookup"><span data-stu-id="db4e2-108">Learn about strong naming and its advantages and disadvantages.</span></span> <span data-ttu-id="db4e2-109">.NET ライブラリの厳密な名前付けにより多くの開発者が使用できるようになるため、これは推奨されるベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="db4e2-109">Strong naming a .NET library allows the most developers to use it and is a recommended best practice.</span></span>

## <a name="nuget-and-open-source-librariesnugetmd"></a>[<span data-ttu-id="db4e2-110">NuGet およびオープン ソース ライブラリ</span><span class="sxs-lookup"><span data-stu-id="db4e2-110">NuGet and open-source libraries</span></span>](./nuget.md)

<span data-ttu-id="db4e2-111">NuGet.org で一般公開されているすべてのパッケージに推奨されるメタデータを含むオープン ソースの .NET ライブラリで NuGet パッケージを作成する最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="db4e2-111">The best way to create NuGet packages for open-source .NET libraries, including recommended metadata for all packages published publicly on NuGet.org.</span></span>

### <a name="dependenciesdependenciesmd"></a>[<span data-ttu-id="db4e2-112">依存関係</span><span class="sxs-lookup"><span data-stu-id="db4e2-112">Dependencies</span></span>](./dependencies.md)

<span data-ttu-id="db4e2-113">NuGet により、.NET ライブラリの構築時に既存のパッケージが使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="db4e2-113">NuGet makes it easy to use existing packages when building a .NET library.</span></span> <span data-ttu-id="db4e2-114">NuGet の依存関係の一般的な競合原因と、その回避方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="db4e2-114">Learn about NuGet dependencies' common sources of friction and how to avoid them.</span></span>

### <a name="sourcelinksourcelinkmd"></a>[<span data-ttu-id="db4e2-115">SourceLink</span><span class="sxs-lookup"><span data-stu-id="db4e2-115">SourceLink</span></span>](./sourcelink.md)

<span data-ttu-id="db4e2-116">SourceLink は、.NET ライブラリのユーザーがデバッグ中にそのソース コードにステップ インできるようにする優れたツールです。</span><span class="sxs-lookup"><span data-stu-id="db4e2-116">SourceLink is a great tool that allows users of your .NET library to step into its source code while debugging.</span></span> <span data-ttu-id="db4e2-117">この記事では、SourceLink とは何かと、それを使用する理由の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="db4e2-117">This article is an overview of what SourceLink is and why you should use it.</span></span>

### <a name="publishingpublish-nuget-packagemd"></a>[<span data-ttu-id="db4e2-118">発行</span><span class="sxs-lookup"><span data-stu-id="db4e2-118">Publishing</span></span>](./publish-nuget-package.md)

<span data-ttu-id="db4e2-119">NuGet.org は最も広く知られ、使用されているリポジトリで、NuGet パッケージを発行する場所は数多くあります。</span><span class="sxs-lookup"><span data-stu-id="db4e2-119">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages.</span></span> <span data-ttu-id="db4e2-120">使用可能な NuGet パッケージ リポジトリのそれぞれの違いと、.NET ライブラリを発行するためのセキュリティのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="db4e2-120">Learn about the different NuGet package repositories available, and security best practices for publishing a .NET library.</span></span>

## <a name="versioningversioningmd"></a>[<span data-ttu-id="db4e2-121">バージョン管理</span><span class="sxs-lookup"><span data-stu-id="db4e2-121">Versioning</span></span>](./versioning.md)

<span data-ttu-id="db4e2-122">優れた .NET ライブラリは時間の経過と共に進化し、機能が追加され、バグが修正され、後のリリースになるほどパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="db4e2-122">Good .NET libraries evolve over time, adding features, fixing bugs, and improving performance in later releases.</span></span> <span data-ttu-id="db4e2-123">各バージョン番号と、破壊的変更を開発者に伝える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="db4e2-123">Learn about the various version numbers and how to communicate breaking changes to developers.</span></span>

### <a name="breaking-changesbreaking-changesmd"></a>[<span data-ttu-id="db4e2-124">破壊的変更</span><span class="sxs-lookup"><span data-stu-id="db4e2-124">Breaking changes</span></span>](./breaking-changes.md)

<span data-ttu-id="db4e2-125">.NET ライブラリでは既存のユーザーに向けた安定性と将来に向けたイノベーションとの間でバランスを取ることが重要です。</span><span class="sxs-lookup"><span data-stu-id="db4e2-125">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="db4e2-126">さまざまな種類の破壊的変更と、下位互換性を維持しながら新しい機能を追加するための戦略について説明します。</span><span class="sxs-lookup"><span data-stu-id="db4e2-126">Learn about the different kinds of breaking changes and strategies for adding new features while maintaining backwards compatibility.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="db4e2-127">[前へ](index.md)
>[次へ](cross-platform-targeting.md)</span><span class="sxs-lookup"><span data-stu-id="db4e2-127">[Previous](index.md)
[Next](cross-platform-targeting.md)</span></span>