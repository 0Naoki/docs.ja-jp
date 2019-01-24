---
title: SQL 生成
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 1eb2830d96000e61d62b2fc934cd246df3ad3e0f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701509"
---
# <a name="sql-generation"></a><span data-ttu-id="5c3ea-102">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="5c3ea-102">SQL Generation</span></span>
<span data-ttu-id="5c3ea-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] のプロバイダーを作成する場合は、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] コマンド ツリーを特定のデータベースが認識できる SQL (たとえば、SQL Server の場合は Transact-SQL、Oracle の場合は PL/SQL) に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-103">When you write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you must translate [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="5c3ea-104">ここでは、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] プロバイダーの SQL 生成コンポーネント (SELECT クエリ用) の開発方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider.</span></span> <span data-ttu-id="5c3ea-105">挿入については、更新、およびクエリの削除を参照してください[変更 SQL 生成](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-105">For information about insert, update, and delete queries, see [Modification SQL Generation](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="5c3ea-106">このセクションの内容を理解するには、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] と ADO.NET プロバイダー モデルについての知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-106">To understand this section, you should be familiar with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the ADO.NET Provider Model.</span></span> <span data-ttu-id="5c3ea-107">また、コマンド ツリーと <xref:System.Data.Common.CommandTrees.DbExpression> について理解している必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="5c3ea-108">SQL 生成モジュールの役割</span><span class="sxs-lookup"><span data-stu-id="5c3ea-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="5c3ea-109">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] プロバイダーの SQL 生成モジュールは、指定されたクエリ コマンド ツリーを、SQL:1999 準拠のデータベースを対象とする 1 つの SQL SELECT ステートメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-109">The SQL generation module of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="5c3ea-110">生成される SQL 内の入れ子になったクエリは、できるだけ少なくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="5c3ea-111">SQL 生成モジュールによって出力クエリ コマンド ツリーを簡素化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="5c3ea-112">これは、結合の排除や連続するフィルター ノードの折りたたみなどにより、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] が実行する処理です。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-112">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="5c3ea-113"><xref:System.Data.Common.DbProviderServices> クラスは、SQL 生成レイヤーにアクセスしてコマンド ツリーを <xref:System.Data.Common.DbCommand> に変換するための開始点となります。</span><span class="sxs-lookup"><span data-stu-id="5c3ea-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c3ea-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5c3ea-114">In This Section</span></span>  
 [<span data-ttu-id="5c3ea-115">コマンド ツリーの構造</span><span class="sxs-lookup"><span data-stu-id="5c3ea-115">The Shape of the Command Trees</span></span>](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="5c3ea-116">コマンド ツリーからの SQL の生成: ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="5c3ea-116">Generating SQL from Command Trees - Best Practices</span></span>](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="5c3ea-117">サンプル プロバイダーでの SQL 生成</span><span class="sxs-lookup"><span data-stu-id="5c3ea-117">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="5c3ea-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c3ea-118">See also</span></span>
- [<span data-ttu-id="5c3ea-119">Entity Framework データ プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="5c3ea-119">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
