---
title: 操作のカスタマイズ概要
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 4f13bed76ad2814d669f487b57ae9acbdc08eb74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735462"
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="05d38-102">操作のカスタマイズ概要</span><span class="sxs-lookup"><span data-stu-id="05d38-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="05d38-103">既定では、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、対応付けに基づいて、挿入、更新、および削除の各操作のための動的な SQL を生成します。</span><span class="sxs-lookup"><span data-stu-id="05d38-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="05d38-104">しかし実際には、セキュリティや検証などを目的とした独自のビジネス ロジックを追加することが必要になる場合がよくあります。</span><span class="sxs-lookup"><span data-stu-id="05d38-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="05d38-105">これらの操作をカスタマイズするための手法は、次に示します。</span><span class="sxs-lookup"><span data-stu-id="05d38-105">techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="05d38-106">読み込みオプション</span><span class="sxs-lookup"><span data-stu-id="05d38-106">Loading Options</span></span>  
 <span data-ttu-id="05d38-107">クエリで、データベースに接続するときに、メイン ターゲットに関係するデータをどれだけ取得するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="05d38-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="05d38-108">この機能は主に、<xref:System.Data.Linq.DataLoadOptions> を使用して実装します。</span><span class="sxs-lookup"><span data-stu-id="05d38-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="05d38-109">詳細については、[遅延読み込みと即時読み込み](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d38-109">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="05d38-110">部分メソッド</span><span class="sxs-lookup"><span data-stu-id="05d38-110">Partial Methods</span></span>  
 <span data-ttu-id="05d38-111">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] による既定の対応付けでは、ビジネス ロジックの実装に使用できる部分メソッドが提供されます。</span><span class="sxs-lookup"><span data-stu-id="05d38-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="05d38-112">詳細については、[を追加するビジネス ロジックでメソッドを使用して部分](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d38-112">For more information, see [Adding Business Logic By Using Partial Methods](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="05d38-113">ストアド プロシージャおよびユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="05d38-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="05d38-114">ストアド プロシージャおよびユーザー定義関数の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="05d38-114">supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="05d38-115">ストアド プロシージャは、操作のカスタマイズによく使用されます。</span><span class="sxs-lookup"><span data-stu-id="05d38-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="05d38-116">詳細については、「[ストアド プロシージャ](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d38-116">For more information, see [Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d38-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="05d38-117">See also</span></span>
- [<span data-ttu-id="05d38-118">挿入、更新、および削除の各操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="05d38-118">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
