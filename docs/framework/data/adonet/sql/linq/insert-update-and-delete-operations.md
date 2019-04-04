---
title: 挿入、更新、および削除の各操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: 7dd2eb64a9320d88c7bc3b5feb6578d70f5910b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503665"
---
# <a name="insert-update-and-delete-operations"></a><span data-ttu-id="45a28-102">挿入、更新、および削除の各操作</span><span class="sxs-lookup"><span data-stu-id="45a28-102">Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="45a28-103">オブジェクト モデルに対してオブジェクトの追加、変更、および削除を行うには、`Insert` で `Update`、`Delete`、および [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の各操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="45a28-103">You perform `Insert`, `Update`, and `Delete` operations in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] by adding, changing, and removing objects in your object model.</span></span> <span data-ttu-id="45a28-104">既定では、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によって SQL に対する操作が変換され、変更内容がデータベースに送信されます。</span><span class="sxs-lookup"><span data-stu-id="45a28-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your actions to SQL and submits the changes to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="45a28-105">操作して、オブジェクトに加えた変更の保持に最大限の柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="45a28-105">offers maximum flexibility in manipulating and persisting changes that you made to your objects.</span></span> <span data-ttu-id="45a28-106">クエリによって取得するか新規に作成することによりエンティティ オブジェクトが使用可能になった後で、通常のオブジェクトと同じようにそれらのオブジェクトをアプリケーションで変更できます。</span><span class="sxs-lookup"><span data-stu-id="45a28-106">As soon as entity objects are available (either by retrieving them through a query or by constructing them anew), you can change them as typical objects in your application.</span></span> <span data-ttu-id="45a28-107">つまり、その値を変更することができます、自分のコレクションに追加することができます、コレクションから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="45a28-107">That is, you can change their values, you can add them to your collections, and you can remove them from your collections.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="45a28-108">では変更履歴が保持されるため、<xref:System.Data.Linq.DataContext.SubmitChanges%2A> を呼び出すと、変更内容をデータベースに送信できます。</span><span class="sxs-lookup"><span data-stu-id="45a28-108">tracks your changes and is ready to transmit them back to the database when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="45a28-109">は連鎖削除操作をサポートせず、認識もしません。</span><span class="sxs-lookup"><span data-stu-id="45a28-109">does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="45a28-110">設定する必要がありますこれに対する制約を持つテーブルの行を削除する場合、`ON DELETE CASCADE`データベース内の外部キー制約でルールまたは独自のコードを使用して、まず親オブジェクトが削除されないようにする子オブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="45a28-110">If you want to delete a row in a table that has constraints against it, you must either set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database, or use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span> <span data-ttu-id="45a28-111">それ以外の場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="45a28-111">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="45a28-112">詳細については、「[方法 :データベースから行を削除](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="45a28-112">For more information, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="45a28-113">次の例では、Northwind サンプル データベースの `Customer` クラスと `Order` クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="45a28-113">The following excerpts use the `Customer` and `Order` classes from the Northwind sample database.</span></span> <span data-ttu-id="45a28-114">簡潔にするため、ここではクラス定義を省いています。</span><span class="sxs-lookup"><span data-stu-id="45a28-114">Class definitions are not shown for brevity.</span></span>  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 <span data-ttu-id="45a28-115"><xref:System.Data.Linq.DataContext.SubmitChanges%2A> を呼び出すと、変更内容をデータベースに送信する SQL コマンドが [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によって自動的に生成され、実行されます。</span><span class="sxs-lookup"><span data-stu-id="45a28-115">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatically generates and executes the SQL commands that it must have to transmit your changes back to the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45a28-116">独自に作成したロジック (通常はストアド プロシージャ) を使用して、この動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="45a28-116">You can override this behavior by using your own custom logic, typically by way of a stored procedure.</span></span> <span data-ttu-id="45a28-117">詳細については、[開発者でオーバーライドする既定の動作の責任](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45a28-117">For more information, see [Responsibilities of the Developer In Overriding Default Behavior](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).</span></span>  
>   
>  <span data-ttu-id="45a28-118">Visual Studio を使用して開発者が使用できる、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]この目的のストアド プロシージャを開発します。</span><span class="sxs-lookup"><span data-stu-id="45a28-118">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for this purpose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a28-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="45a28-119">See also</span></span>
- [<span data-ttu-id="45a28-120">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="45a28-120">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="45a28-121">挿入、更新、および削除の各操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="45a28-121">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
