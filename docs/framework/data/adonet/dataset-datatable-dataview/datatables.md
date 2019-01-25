---
title: DataTables
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: f0f429d7f28360fd76dfff0e7d4a4eba019e5acf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653251"
---
# <a name="datatables"></a><span data-ttu-id="f9077-102">DataTables</span><span class="sxs-lookup"><span data-stu-id="f9077-102">DataTables</span></span>
<span data-ttu-id="f9077-103"><xref:System.Data.DataSet> は、テーブル、リレーションシップ、および制約のコレクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f9077-103">A <xref:System.Data.DataSet> is made up of a collection of tables, relationships, and constraints.</span></span> <span data-ttu-id="f9077-104">ADO.NET では、<xref:System.Data.DataTable>オブジェクトは、テーブルを表すために使用する**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="f9077-104">In ADO.NET, <xref:System.Data.DataTable> objects are used to represent the tables in a **DataSet**.</span></span> <span data-ttu-id="f9077-105">A **DataTable**リレーショナル データをメモリ内の 1 つのテーブルを表すデータがローカルにします。NET ベースのアプリケーションが存在するを使用して Microsoft SQL Server などのデータ ソースからデータを読み込むことができます、 **DataAdapter**詳細については、次を参照してください[DataAdapter からの Dataset](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .</span><span class="sxs-lookup"><span data-stu-id="f9077-105">A **DataTable** represents one table of in-memory relational data; the data is local to the .NET-based application in which it resides, but can be populated from a data source such as Microsoft SQL Server using a **DataAdapter** For more information, see [Populating a DataSet from a DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).</span></span>  
  
 <span data-ttu-id="f9077-106">**DataTable**クラスのメンバーである、 **System.Data** .NET Framework クラス ライブラリ内の名前空間。</span><span class="sxs-lookup"><span data-stu-id="f9077-106">The **DataTable** class is a member of the **System.Data** namespace within the .NET Framework class library.</span></span> <span data-ttu-id="f9077-107">作成して使用することができます、 **DataTable**とは独立してまたはのメンバーとして、**データセット**、および**DataTable**オブジェクトは、その他の .NET Framework のオブジェクトと組み合わせても使用できますなど、<xref:System.Data.DataView>します。</span><span class="sxs-lookup"><span data-stu-id="f9077-107">You can create and use a **DataTable** independently or as a member of a **DataSet**, and **DataTable** objects can also be used in conjunction with other .NET Framework objects, including the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="f9077-108">内のテーブルのコレクションにアクセスする、**データセット**を通じて、**テーブル**のプロパティ、**データセット**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f9077-108">You access the collection of tables in a **DataSet** through the **Tables** property of the **DataSet** object.</span></span>  
  
 <span data-ttu-id="f9077-109">テーブルのスキーマ (構造) は、列と制約で表されます。</span><span class="sxs-lookup"><span data-stu-id="f9077-109">The schema, or structure of a table is represented by columns and constraints.</span></span> <span data-ttu-id="f9077-110">スキーマを定義する、 **DataTable**を使用して<xref:System.Data.DataColumn>オブジェクトだけでなく<xref:System.Data.ForeignKeyConstraint>と<xref:System.Data.UniqueConstraint>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f9077-110">You define the schema of a **DataTable** using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="f9077-111">テーブルの列は、データ ソースの列に割り当てたり、式で算出された値を格納したり、格納されている値を自動的にインクリメントしたり、主キー値を格納したりできます。</span><span class="sxs-lookup"><span data-stu-id="f9077-111">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="f9077-112">スキーマだけでなく、 **DataTable**行が含まれており、データを注文する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9077-112">In addition to a schema, a **DataTable** must also have rows to contain and order data.</span></span> <span data-ttu-id="f9077-113"><xref:System.Data.DataRow> クラスは、テーブルに格納される実際のデータを表します。</span><span class="sxs-lookup"><span data-stu-id="f9077-113">The <xref:System.Data.DataRow> class represents the actual data contained in a table.</span></span> <span data-ttu-id="f9077-114">使用する、 **DataRow**とそのプロパティとメソッドを取得するには、評価、およびテーブルにデータを操作します。</span><span class="sxs-lookup"><span data-stu-id="f9077-114">You use the **DataRow** and its properties and methods to retrieve, evaluate, and manipulate the data in a table.</span></span> <span data-ttu-id="f9077-115">アクセスして、行内のデータを変更すると、 **DataRow**オブジェクトは、両方の現在と元の状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="f9077-115">As you access and change the data within a row, the **DataRow** object maintains both its current and original state.</span></span>  
  
 <span data-ttu-id="f9077-116">テーブル間で 1 つ以上の列を関連付け、テーブル間の親子のリレーションシップを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f9077-116">You can create parent-child relationships between tables using one or more related columns in the tables.</span></span> <span data-ttu-id="f9077-117">間のリレーションシップを作成する**DataTable**オブジェクトを使用して、<xref:System.Data.DataRelation>します。</span><span class="sxs-lookup"><span data-stu-id="f9077-117">You create a relationship between **DataTable** objects using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="f9077-118">**DataRelation**オブジェクトは、特定の行の関連子または親の行を取得し、使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9077-118">**DataRelation** objects can then be used to return the related child or parent rows of a particular row.</span></span> <span data-ttu-id="f9077-119">詳細については、次を参照してください。 [Datarelation の追加](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)します。</span><span class="sxs-lookup"><span data-stu-id="f9077-119">For more information, see [Adding DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9077-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f9077-120">In This Section</span></span>  
 [<span data-ttu-id="f9077-121">DataTable の作成</span><span class="sxs-lookup"><span data-stu-id="f9077-121">Creating a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 <span data-ttu-id="f9077-122">作成する方法について説明します、 **DataTable**に追加し、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="f9077-122">Explains how to create a **DataTable** and add it to a **DataSet**.</span></span>  
  
 [<span data-ttu-id="f9077-123">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="f9077-123">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 <span data-ttu-id="f9077-124">作成と使用に関する情報を提供**DataColumn**オブジェクトと制約。</span><span class="sxs-lookup"><span data-stu-id="f9077-124">Provides information about creating and using **DataColumn** objects and constraints.</span></span>  
  
 [<span data-ttu-id="f9077-125">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="f9077-125">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 <span data-ttu-id="f9077-126">テーブル内のデータを追加、変更、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9077-126">Explains how to add, modify, and delete data in a table.</span></span> <span data-ttu-id="f9077-127">使用する方法について説明します**DataTable**テーブル内のデータへの変更を確認するイベントです。</span><span class="sxs-lookup"><span data-stu-id="f9077-127">Explains how to use **DataTable** events to examine changes to data in the table.</span></span>  
  
 [<span data-ttu-id="f9077-128">DataTable イベントの処理</span><span class="sxs-lookup"><span data-stu-id="f9077-128">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 <span data-ttu-id="f9077-129">使用するために使用できるイベントに関する情報を提供する**DataTable**列の値が変更され、行を追加または削除されたときにイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9077-129">Provides information about the events available for use with a **DataTable**, including events when column values are modified and rows are added or deleted.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f9077-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9077-130">Related Sections</span></span>  
 [<span data-ttu-id="f9077-131">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f9077-131">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="f9077-132">ADO.NET のアーキテクチャとコンポーネントについて説明し、ADO.NET を使用して既存のデータ ソースにアクセスしたり、アプリケーション データを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9077-132">Describes the ADO.NET architecture and components, and how to use them to access existing data sources and manage application data.</span></span>  
  
 [<span data-ttu-id="f9077-133">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="f9077-133">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="f9077-134">ADO.NET についての情報を提供します**データセット**テーブル間のリレーションシップを作成する方法などです。</span><span class="sxs-lookup"><span data-stu-id="f9077-134">Provides information about the ADO.NET **DataSet** including how to create relationships between tables.</span></span>  
  
 <xref:System.Data.Constraint>  
 <span data-ttu-id="f9077-135">参照情報を提供、**制約**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f9077-135">Provides reference information about the **Constraint** object.</span></span>  
  
 <xref:System.Data.DataColumn>  
 <span data-ttu-id="f9077-136">参照情報を提供、 **DataColumn**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f9077-136">Provides reference information about the **DataColumn** object.</span></span>  
  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="f9077-137">参照情報を提供、**データセット**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f9077-137">Provides reference information about the **DataSet** object.</span></span>  
  
 <xref:System.Data.DataTable>  
 <span data-ttu-id="f9077-138">参照情報を提供、 **DataTable**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f9077-138">Provides reference information about the **DataTable** object.</span></span>  
  
 [<span data-ttu-id="f9077-139">クラス ライブラリの概要</span><span class="sxs-lookup"><span data-stu-id="f9077-139">Class Library Overview</span></span>](../../../../../docs/standard/class-library-overview.md)  
 <span data-ttu-id="f9077-140">.NET Framework クラス ライブラリの概要を説明など、**システム**名前空間、2 番目のレベルの名前空間と**System.Data**。</span><span class="sxs-lookup"><span data-stu-id="f9077-140">Provides an overview of the .NET Framework class library, including the **System** namespace as well as its second-level namespace, **System.Data**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9077-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9077-141">See also</span></span>
- [<span data-ttu-id="f9077-142">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="f9077-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
