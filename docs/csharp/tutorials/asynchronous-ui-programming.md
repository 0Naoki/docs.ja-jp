---
title: "非同期 UI プログラミング - C# のガイド"
description: "プログラミングで非同期操作を処理中に、UI の応答性を保つ手法について学ぶ"
keywords: C#, UWP, XAML
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7402b29b-1093-456d-be4c-f60ecb8926bb
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f868c798f94acfb1ef468ea91f4245520c4e14b
ms.contentlocale: ja-jp
ms.lasthandoff: 07/28/2017

---

# <a name="-asynchronous-ui-programming"></a><span data-ttu-id="af8a7-104">🔧 非同期 UI プログラミング</span><span class="sxs-lookup"><span data-stu-id="af8a7-104">🔧 Asynchronous UI Programming</span></span>

> <span data-ttu-id="af8a7-105">**注:**</span><span class="sxs-lookup"><span data-stu-id="af8a7-105">**Note**</span></span>
> 
> <span data-ttu-id="af8a7-106">このトピックはまだ作成されておりません。</span><span class="sxs-lookup"><span data-stu-id="af8a7-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="af8a7-107">適用範囲や方法を具体化するのに役立つ皆様からのご意見をお待ちしております。</span><span class="sxs-lookup"><span data-stu-id="af8a7-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="af8a7-108">GitHub で状態の追跡やこの[件](https://github.com/dotnet/docs/issues/951)に関するご意見を投稿することができます。</span><span class="sxs-lookup"><span data-stu-id="af8a7-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/951) at GitHub.</span></span>
> 
> <span data-ttu-id="af8a7-109">このトピックの初期ドラフトや概要の確認をご希望の場合は、この件の連絡先情報を含むメモを入力してください。</span><span class="sxs-lookup"><span data-stu-id="af8a7-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="af8a7-110">ご意見の投稿方法の詳細については、[GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md) でご確認ください。</span><span class="sxs-lookup"><span data-stu-id="af8a7-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

