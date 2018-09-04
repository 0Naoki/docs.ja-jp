---
title: Oracle および ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 9a60499674f0192bb7589f227bffb6f907f682d9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561750"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="56296-102">Oracle および ADO.NET</span><span class="sxs-lookup"><span data-stu-id="56296-102">Oracle and ADO.NET</span></span>
> [!NOTE]
>  <span data-ttu-id="56296-103"><xref:System.Data.OracleClient> の型は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="56296-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="56296-104">これらの型は、.NET Framework の現在のバージョンでは引き続きサポートされていますが、今後のリリースでは削除される予定です。</span><span class="sxs-lookup"><span data-stu-id="56296-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="56296-105">サードパーティの Oracle プロバイダーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="56296-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="56296-106">このセクションでは、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle 固有の機能および動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-106">This section describes features and behaviors that are specific to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="56296-107">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle では、Oracle Client ソフトウェアとして提供されている Oracle Call Interface (OCI) を使用して Oracle データベースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="56296-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="56296-108">データ プロバイダーの機能はのように設計されています、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SQL Server、OLE DB および ODBC 用データ プロバイダー。</span><span class="sxs-lookup"><span data-stu-id="56296-108">The functionality of the data provider is designed to be similar to that of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="56296-109">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle を使用するには、アプリケーションで以下のように <xref:System.Data.OracleClient> 名前空間を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56296-109">To use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="56296-110">コードをコンパイルするには、DLL への参照も必要です。</span><span class="sxs-lookup"><span data-stu-id="56296-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="56296-111">たとえば、C# プログラムをコンパイルする場合、コマンド ラインに以下のコードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="56296-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="56296-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="56296-112">In This Section</span></span>  
 [<span data-ttu-id="56296-113">システム要件</span><span class="sxs-lookup"><span data-stu-id="56296-113">System Requirements</span></span>](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="56296-114">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle を使用するための要件を説明し、その際に知っておくべきさまざまなことについて説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-114">Describes requirements for using the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="56296-115">Oracle BFILE</span><span class="sxs-lookup"><span data-stu-id="56296-115">Oracle BFILEs</span></span>](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 <span data-ttu-id="56296-116"><xref:System.Data.OracleClient.OracleBFile> クラスについて説明します。このクラスは、Oracle BFILE データ型を操作するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="56296-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="56296-117">Oracle LOB</span><span class="sxs-lookup"><span data-stu-id="56296-117">Oracle LOBs</span></span>](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 <span data-ttu-id="56296-118"><xref:System.Data.OracleClient.OracleLob> クラスについて説明します。このクラスは、Oracle LOB データ型を操作するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="56296-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="56296-119">Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="56296-119">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 <span data-ttu-id="56296-120">Oracle REF CURSOR データ型のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="56296-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="56296-121">OracleTypes</span></span>](../../../../docs/framework/data/adonet/oracletypes.md)  
 <span data-ttu-id="56296-122"><xref:System.Data.OracleClient.OracleNumber> や <xref:System.Data.OracleClient.OracleString> など、Oracle データ型を操作するために使用する構造体について説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="56296-123">Oracle シーケンス</span><span class="sxs-lookup"><span data-stu-id="56296-123">Oracle Sequences</span></span>](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 <span data-ttu-id="56296-124">サーバーによって生成されたキー値 (Oracle シーケンス) を取得するためのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="56296-125">Oracle データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="56296-125">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="56296-126">Oracle データ型およびその <xref:System.Data.OracleClient.OracleDataReader> へのマップを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="56296-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="56296-127">Oracle 分散トランザクション</span><span class="sxs-lookup"><span data-stu-id="56296-127">Oracle Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <span data-ttu-id="56296-128"><xref:System.Data.OracleClient.OracleConnection> オブジェクトが、トランザクションがアクティブであると判断した場合に、既存の分散トランザクションに自動的に参加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="56296-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="56296-129">Related Sections</span></span>  
 [<span data-ttu-id="56296-130">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="56296-130">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="56296-131">[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] を使用する場合の安全なコーディング方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-131">Describes secure coding practices when using [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
 [<span data-ttu-id="56296-132">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="56296-132">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="56296-133">`DataSets`、型指定された `DataSets`、`DataTables`、および `DataViews` の作成方法と使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="56296-134">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="56296-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="56296-135">ADO.NET でのデータの操作方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="56296-136">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="56296-136">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 <span data-ttu-id="56296-137">SQL Server 固有の機能の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="56296-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="56296-138">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="56296-139">[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] でプロバイダーに依存しないコードを記述するための汎用的なクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="56296-139">Describes generic classes that allow you to write provider-independent code in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56296-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="56296-140">See Also</span></span>  
 [<span data-ttu-id="56296-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="56296-141">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="56296-142">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="56296-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
