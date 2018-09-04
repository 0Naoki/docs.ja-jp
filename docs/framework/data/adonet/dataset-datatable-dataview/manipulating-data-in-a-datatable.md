---
title: DataTable 内のデータの操作
ms.date: 03/30/2017
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
ms.openlocfilehash: a09edc6ce3098ab135d8c27ba0f6ad56cceed159
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521309"
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="68ab0-102">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="68ab0-102">Manipulating Data in a DataTable</span></span>
<span data-ttu-id="68ab0-103"><xref:System.Data.DataTable> 内に <xref:System.Data.DataSet> を作成した後で、データベース内のテーブルを使用する場合と同じ操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="68ab0-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="68ab0-104">テーブル内のデータの追加、表示、編集、および削除を実行したり、エラーとイベントを監視したり、テーブル内のデータを照会したりできます。</span><span class="sxs-lookup"><span data-stu-id="68ab0-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="68ab0-105">内のデータを変更するときに、 **DataTable**変更が正確ですと、プログラムによって受け入れるか変更を拒否するかどうかを判断するかどうかを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="68ab0-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68ab0-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="68ab0-106">In This Section</span></span>  
 [<span data-ttu-id="68ab0-107">DataTable へのデータの追加</span><span class="sxs-lookup"><span data-stu-id="68ab0-107">Adding Data to a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-data-to-a-datatable.md)  
 <span data-ttu-id="68ab0-108">新しい行を作成してテーブルに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68ab0-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="68ab0-109">DataTable 内のデータの表示</span><span class="sxs-lookup"><span data-stu-id="68ab0-109">Viewing Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/viewing-data-in-a-datatable.md)  
 <span data-ttu-id="68ab0-110">元のバージョンのデータや現在のバージョンのデータを含め、行内のデータにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68ab0-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="68ab0-111">Load メソッド</span><span class="sxs-lookup"><span data-stu-id="68ab0-111">The Load Method</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/the-load-method.md)  
 <span data-ttu-id="68ab0-112">使用について説明します、**ロード**メソッドで設定する、 **DataTable**行。</span><span class="sxs-lookup"><span data-stu-id="68ab0-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="68ab0-113">DataTable の編集</span><span class="sxs-lookup"><span data-stu-id="68ab0-113">DataTable Edits</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-edits.md)  
 <span data-ttu-id="68ab0-114">提示された変更が検証され、受け入れられるまで行への実際の変更を保留しておく方法も含め、行内のデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68ab0-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="68ab0-115">行の状態とバージョン</span><span class="sxs-lookup"><span data-stu-id="68ab0-115">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 <span data-ttu-id="68ab0-116">行のさまざまな状態について説明します。</span><span class="sxs-lookup"><span data-stu-id="68ab0-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="68ab0-117">DataRow の削除</span><span class="sxs-lookup"><span data-stu-id="68ab0-117">DataRow Deletion</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarow-deletion.md)  
 <span data-ttu-id="68ab0-118">テーブルから行を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68ab0-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="68ab0-119">行エラー情報</span><span class="sxs-lookup"><span data-stu-id="68ab0-119">Row Error Information</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 <span data-ttu-id="68ab0-120">アプリケーション内でのデータに関する問題を解決するために、行ごとのエラー情報を挿入する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68ab0-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="68ab0-121">AcceptChange と RejectChange</span><span class="sxs-lookup"><span data-stu-id="68ab0-121">AcceptChanges and RejectChanges</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="68ab0-122">行への変更を受け入れたり拒否したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68ab0-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ab0-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="68ab0-123">See Also</span></span>  
 [<span data-ttu-id="68ab0-124">DataTables</span><span class="sxs-lookup"><span data-stu-id="68ab0-124">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="68ab0-125">DataTable イベントの処理</span><span class="sxs-lookup"><span data-stu-id="68ab0-125">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="68ab0-126">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="68ab0-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
