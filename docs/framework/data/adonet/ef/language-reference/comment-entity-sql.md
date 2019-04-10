---
title: -- (コメント) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: c10b17931c6024e2a9e947083747435d8aa54fa2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339516"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="13ee8-102">-- (コメント) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="13ee8-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="13ee8-103">クエリは、コメントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="13ee8-103">queries can contain comments.</span></span> <span data-ttu-id="13ee8-104">コメント行の先頭には、2 個のダッシュ (`--`) を付けます。</span><span class="sxs-lookup"><span data-stu-id="13ee8-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13ee8-105">構文</span><span class="sxs-lookup"><span data-stu-id="13ee8-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="13ee8-106">引数</span><span class="sxs-lookup"><span data-stu-id="13ee8-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="13ee8-107">コメントのテキストを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="13ee8-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13ee8-108">例</span><span class="sxs-lookup"><span data-stu-id="13ee8-108">Example</span></span>  
 <span data-ttu-id="13ee8-109">次の Entity SQL クエリは、コメントの使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="13ee8-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="13ee8-110">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="13ee8-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="13ee8-111">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="13ee8-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="13ee8-112">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="13ee8-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="13ee8-113">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="13ee8-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="13ee8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="13ee8-114">See also</span></span>

- [<span data-ttu-id="13ee8-115">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="13ee8-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="13ee8-116">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="13ee8-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
