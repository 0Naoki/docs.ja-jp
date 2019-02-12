---
title: プログラミング ガイド
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 32e62899c13be3f2f08bef7e882d5b9c4d11fda2
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093445"
---
# <a name="programming-guide"></a><span data-ttu-id="91403-102">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="91403-102">Programming Guide</span></span>
<span data-ttu-id="91403-103">ここでは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のオブジェクト モデルを作成および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91403-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="91403-104">Visual Studio を使用している場合は、使用することも、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]これらのタスクの多くを実行します。</span><span class="sxs-lookup"><span data-stu-id="91403-104">If you are using Visual Studio, you can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="91403-105">特定の問題に関する Microsoft のドキュメントを検索することとに参加することができます、 [LINQ フォーラム](https://go.microsoft.com/fwlink/?LinkId=76488)専門家とより複雑なトピックを説明できます。</span><span class="sxs-lookup"><span data-stu-id="91403-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="91403-106">最後に、 [LINQ to SQL: リレーショナル データ用 .net 統合言語クエリ](https://go.microsoft.com/fwlink/?LinkId=93205)ホワイト ペーパーの詳細[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]テクノロジ、Visual Basic と c# のコード例を完了します。</span><span class="sxs-lookup"><span data-stu-id="91403-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91403-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="91403-107">In This Section</span></span>  
 [<span data-ttu-id="91403-108">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="91403-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="91403-109">オブジェクト モデルを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91403-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="91403-110">データベースとの通信</span><span class="sxs-lookup"><span data-stu-id="91403-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="91403-111">データベースへのコンジットとして <xref:System.Data.Linq.DataContext> オブジェクトを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91403-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="91403-112">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="91403-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="91403-113">
  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] でクエリを実行する方法を説明し、多数の例を示します。</span><span class="sxs-lookup"><span data-stu-id="91403-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="91403-114">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="91403-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="91403-115">データベース内のデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91403-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="91403-116">デバッグのサポート</span><span class="sxs-lookup"><span data-stu-id="91403-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="91403-117">
  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] プロジェクトのデバッグ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="91403-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="91403-118">背景情報</span><span class="sxs-lookup"><span data-stu-id="91403-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="91403-119">コンカレンシーの競合の解決、新しいデータベースの作成など、上級ユーザー向けの追加項目が記載されています。</span><span class="sxs-lookup"><span data-stu-id="91403-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="91403-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="91403-120">Related Sections</span></span>  
 [<span data-ttu-id="91403-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="91403-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="91403-122">
  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] テクノロジの説明および機能の解説が記載されているトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="91403-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="91403-123">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="91403-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="91403-124">ストアド プロシージャの使用手順のトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="91403-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="91403-125">LINQ の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="91403-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="91403-126">SQL を使用する LINQ について学習を開始するのに役立つリソースを提供します。C#します。</span><span class="sxs-lookup"><span data-stu-id="91403-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="91403-127">LINQ の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91403-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="91403-128">LINQ to SQL は Visual Basic を使用して学習を開始するのに役立つリソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="91403-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
