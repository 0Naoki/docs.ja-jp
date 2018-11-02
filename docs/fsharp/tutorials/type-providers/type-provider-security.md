---
title: 型プロバイダーのセキュリティ
description: F# では、型プロバイダーの信頼設定を変更する方法などの型プロバイダーのセキュリティについて説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 26f95ad3950b37a668c497f293b9941ed13a18c7
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2018
ms.locfileid: "43861908"
---
# <a name="type-provider-security"></a><span data-ttu-id="d6a77-103">型プロバイダーのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="d6a77-103">Type Provider Security</span></span>

<span data-ttu-id="d6a77-104">型プロバイダーは、アセンブリ (Dll)、F# プロジェクトまたはスクリプトによって参照される外部データ ソースに接続し、F# 型の環境に、この型情報を適用するコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6a77-104">Type providers are assemblies (DLLs) referenced by your F# project or script that contain code to connect to external data sources and surface this type information to the F# type environment.</span></span> <span data-ttu-id="d6a77-105">通常、コンパイル時し、コードを実行します (または、スクリプトの場合、F# Interactive にコードを送信します)、参照されたアセンブリ内のコードは実行のみです。</span><span class="sxs-lookup"><span data-stu-id="d6a77-105">Typically, code in referenced assemblies is only run when you compile and then execute the code (or in the case of a script, send the code to F# Interactive).</span></span> <span data-ttu-id="d6a77-106">ただし、型プロバイダー アセンブリは、コードがエディターで参照されるだけで、Visual Studio 内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d6a77-106">However, a type provider assembly will run inside Visual Studio when the code is merely browsed in the editor.</span></span> <span data-ttu-id="d6a77-107">これは、型プロバイダーは、クイック ヒントのツールヒント、IntelliSense 入力候補など、エディターに追加情報の追加を実行する必要があるために発生します。</span><span class="sxs-lookup"><span data-stu-id="d6a77-107">This happens because type providers need to run to add extra information to the editor, such as Quick Info tooltips, IntelliSense completions, and so on.</span></span> <span data-ttu-id="d6a77-108">その結果、型に関する追加のセキュリティの考慮事項プロバイダー アセンブリが、Visual Studio プロセス内で自動的に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="d6a77-108">As a result, there are extra security considerations for type provider assemblies, since they run automatically inside the Visual Studio process.</span></span>

## <a name="security-warning-dialog"></a><span data-ttu-id="d6a77-109">セキュリティの警告ダイアログ</span><span class="sxs-lookup"><span data-stu-id="d6a77-109">Security Warning Dialog</span></span>

<span data-ttu-id="d6a77-110">特定の型プロバイダー アセンブリを使用して、最初に、Visual Studio には、型プロバイダーを実行すると、警告を表示するセキュリティ ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6a77-110">When using a particular type provider assembly for the first time, Visual Studio displays a security dialog that warns you that the type provider is about to run.</span></span> <span data-ttu-id="d6a77-111">Visual Studio では、型プロバイダーを読み込み、前にそのするこの特定のプロバイダーを信頼しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d6a77-111">Before Visual Studio loads the type provider, it gives you the opportunity to decide if you trust this particular provider.</span></span> <span data-ttu-id="d6a77-112">型プロバイダーのソースを信頼している場合は、「この型プロバイダーが信頼されます」を選択し、</span><span class="sxs-lookup"><span data-stu-id="d6a77-112">If you trust the source of the type provider, then select "I trust this type provider."</span></span> <span data-ttu-id="d6a77-113">型プロバイダーのソースを信頼していない場合は、「は信頼できないこの型プロバイダー」を選択し、</span><span class="sxs-lookup"><span data-stu-id="d6a77-113">If you do not trust the source of the type provider, then select "I do not trust this type provider."</span></span> <span data-ttu-id="d6a77-114">プロバイダーを信頼する、Visual Studio 内で実行および IntelliSense を提供し、機能を構築できます。</span><span class="sxs-lookup"><span data-stu-id="d6a77-114">Trusting the provider enables it to run inside Visual Studio and provide IntelliSense and build features.</span></span> <span data-ttu-id="d6a77-115">型プロバイダー自体が悪意のある場合が、コンピューターを損なうおそれのコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="d6a77-115">But if the type provider itself is malicious, running its code could compromise your machine.</span></span>

<span data-ttu-id="d6a77-116">プロジェクトに参照型プロバイダーを信頼しないように、ダイアログ ボックスで選択したコードが含まれている場合、コンパイル時に、コンパイラは報告型プロバイダーが信頼されていないことを示すエラー。</span><span class="sxs-lookup"><span data-stu-id="d6a77-116">If your project contains code that references type providers that you chose in the dialog not to trust, then at compile time, the compiler will report an error that indicates that the type provider is untrusted.</span></span> <span data-ttu-id="d6a77-117">信頼されていない型のプロバイダーに依存する任意の型は、赤の波線で示されます。</span><span class="sxs-lookup"><span data-stu-id="d6a77-117">Any types that are dependent on the untrusted type provider are indicated by red squiggles.</span></span> <span data-ttu-id="d6a77-118">エディターでコードを参照しても安全です。</span><span class="sxs-lookup"><span data-stu-id="d6a77-118">It is safe to browse the code in the editor.</span></span>

<span data-ttu-id="d6a77-119">Visual Studio で直接信頼設定を変更する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6a77-119">If you decide to change the trust setting directly in Visual Studio, perform the following steps.</span></span>

### <a name="to-change-the-trust-settings-for-type-providers"></a><span data-ttu-id="d6a77-120">型プロバイダーの信頼設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="d6a77-120">To change the trust settings for type providers</span></span>

1. <span data-ttu-id="d6a77-121">`Tools`メニューの  `Options`、展開、`F# Tools`ノード。</span><span class="sxs-lookup"><span data-stu-id="d6a77-121">On the `Tools` menu, select `Options`, and expand the `F# Tools` node.</span></span>

2. <span data-ttu-id="d6a77-122">選択`Type Providers`と、型プロバイダーの一覧で信頼すると、型プロバイダーのチェック ボックスをオンにしを信頼していないもののチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d6a77-122">Select `Type Providers`, and in the list of type providers, select the check box for type providers you trust, and clear the check box for those you don't trust.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6a77-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6a77-123">See also</span></span>

- [<span data-ttu-id="d6a77-124">型プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d6a77-124">Type Providers</span></span>](index.md)
