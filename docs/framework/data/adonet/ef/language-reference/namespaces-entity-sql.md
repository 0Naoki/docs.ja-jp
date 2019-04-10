---
title: 名前空間 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: bef2fa96ce090a600155d68ecc3daea55b675840
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185524"
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="75db1-102">名前空間 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="75db1-102">Namespaces (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="75db1-103">型名、エンティティ セット、関数、および具合など、グローバル識別子の名前の競合を回避するために名前空間が導入されています。</span><span class="sxs-lookup"><span data-stu-id="75db1-103">introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="75db1-104">名前空間のサポートで[!INCLUDE[esql](../../../../../../includes/esql-md.md)]で名前空間のサポートに似ていますが、[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="75db1-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="75db1-105">USING 句の 2 つの形式を提供します。 (短いエイリアスは、名前空間の提供) を名前空間、および非修飾の名前空間を次の例に示すように修飾します。</span><span class="sxs-lookup"><span data-stu-id="75db1-105">provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="75db1-106">名前解決ルール</span><span class="sxs-lookup"><span data-stu-id="75db1-106">Name Resolution Rules</span></span>  
 <span data-ttu-id="75db1-107">識別子は、ローカルのスコープで解決できない場合[!INCLUDE[esql](../../../../../../includes/esql-md.md)]グローバル スコープ (名前空間) での名前を検索しようとしています。</span><span class="sxs-lookup"><span data-stu-id="75db1-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="75db1-108">最初、修飾名前空間のいずれかの識別子 (プレフィックス) の一致を試みます。</span><span class="sxs-lookup"><span data-stu-id="75db1-108">first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="75db1-109">場合は、一致がある[!INCLUDE[esql](../../../../../../includes/esql-md.md)]指定した名前空間識別子の残りの部分を解決しようと試みます。</span><span class="sxs-lookup"><span data-stu-id="75db1-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="75db1-110">一致が見つからなかった場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="75db1-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="75db1-111">次に、[!INCLUDE[esql](../../../../../../includes/esql-md.md)]すべて非修飾の名前空間 (プロローグで指定)、識別子を検索しようとしています。</span><span class="sxs-lookup"><span data-stu-id="75db1-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="75db1-112">その識別子が属している名前空間を一意に特定できた場合は、その場所が返されます。</span><span class="sxs-lookup"><span data-stu-id="75db1-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="75db1-113">同じ識別子に対して複数の名前空間が見つかった場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="75db1-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="75db1-114">場合は、識別子の名前空間が識別されない[!INCLUDE[esql](../../../../../../includes/esql-md.md)][次へ] の外側のスコープに名前を渡します (、<xref:System.Data.Common.DbCommand>または<xref:System.Data.Common.DbConnection>オブジェクト)、次の例に示すように。</span><span class="sxs-lookup"><span data-stu-id="75db1-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="75db1-115">.NET Framework との違い</span><span class="sxs-lookup"><span data-stu-id="75db1-115">Differences from the .NET Framework</span></span>  
 <span data-ttu-id="75db1-116">[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] では、部分修飾名前空間を使用できますが、</span><span class="sxs-lookup"><span data-stu-id="75db1-116">In the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], you can use partially qualified namespaces.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="75db1-117">これはできません。</span><span class="sxs-lookup"><span data-stu-id="75db1-117">does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="75db1-118">ADO.NET の使用法</span><span class="sxs-lookup"><span data-stu-id="75db1-118">ADO.NET Usage</span></span>  
 <span data-ttu-id="75db1-119">クエリは、ADO.NET の <xref:System.Data.Common.DbCommand> オブジェクトを使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="75db1-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <xref:System.Data.Common.DbCommand> <span data-ttu-id="75db1-120">オブジェクトに対して構築できる<xref:System.Data.Common.DbConnection>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="75db1-120">objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="75db1-121">名前空間を <xref:System.Data.Common.DbCommand> オブジェクトや <xref:System.Data.Common.DbConnection> オブジェクトの一部として指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="75db1-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="75db1-122">場合[!INCLUDE[esql](../../../../../../includes/esql-md.md)]識別子を解決できないクエリ自体内で、外部の名前空間が、(同様のルールに基づいて) が調査します。</span><span class="sxs-lookup"><span data-stu-id="75db1-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75db1-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="75db1-123">See also</span></span>

- [<span data-ttu-id="75db1-124">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="75db1-124">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="75db1-125">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="75db1-125">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
