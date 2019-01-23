---
title: クエリ結果のページング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 11bf7e1021c3bb65e4d736e83d2631ae05c274f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630420"
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="0b301-102">クエリ結果のページング</span><span class="sxs-lookup"><span data-stu-id="0b301-102">Paging Through a Query Result</span></span>
<span data-ttu-id="0b301-103">クエリ結果のページングとは、クエリ結果をデータの小さなサブセット、つまりページに分けて返すプロセスです。</span><span class="sxs-lookup"><span data-stu-id="0b301-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="0b301-104">クエリ結果のページングは、結果を管理しやすい小さな単位でユーザーに表示するために行われる一般的な処理です。</span><span class="sxs-lookup"><span data-stu-id="0b301-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="0b301-105">**DataAdapter**のオーバー ロードによって、データのページのみを返す機能が提供、**入力**メソッド。</span><span class="sxs-lookup"><span data-stu-id="0b301-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="0b301-106">ただし、このできない可能性がありますので、大規模なクエリ結果のページングの最適な選択肢ですが、 **DataAdapter**ターゲットを塗りつぶします<xref:System.Data.DataTable>または<xref:System.Data.DataSet>のみ、要求されたレコードを返すリソースで、クエリ全体は引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b301-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="0b301-107">クエリ全体を返す必要があるリソースを使用せずにデータ ソースから 1 ページ分のデータを返すには、必要な行だけ返すように限定する抽出条件をクエリに追加します。</span><span class="sxs-lookup"><span data-stu-id="0b301-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="0b301-108">使用する、**入力**、データのページを返す方法を指定する、 **startRecord**パラメーター、データのページの最初のレコードと**maxRecords**パラメーターの数データのページのレコード。</span><span class="sxs-lookup"><span data-stu-id="0b301-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="0b301-109">次のコード例を使用する方法を示しています、**入力**ページ サイズが 5 つのレコードをクエリ結果の最初のページを返します。</span><span class="sxs-lookup"><span data-stu-id="0b301-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="0b301-110">前の例では、**データセット**だけが 5 つのレコードが全体に格納されます**注文**テーブルが返されます。</span><span class="sxs-lookup"><span data-stu-id="0b301-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="0b301-111">入力する、**データセット**それら同じ 5 つのレコードが、5 つのレコードだけを返すと、TOP を使用して、次のコード例のように、SQL ステートメントの WHERE 句。</span><span class="sxs-lookup"><span data-stu-id="0b301-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")   
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 <span data-ttu-id="0b301-112">この方法でクエリ結果をページングするときは、次のレコード ページを返すコマンドに一意の ID を渡すために、行を順序付けする固有の識別子を保存する必要があります。次のコード サンプルで示します。</span><span class="sxs-lookup"><span data-stu-id="0b301-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="0b301-113">オーバー ロードを使用してレコードの次のページを返す、**入力**を受け取るメソッド、 **startRecord**と**maxRecords**パラメーターによって、現在のレコード インデックスをインクリメントします。ページ サイズと塗りつぶしテーブル。</span><span class="sxs-lookup"><span data-stu-id="0b301-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="0b301-114">レコードの 1 つだけのページが追加された場合でも、データベース サーバーで全体のクエリ結果を返すことに注意してください、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="0b301-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="0b301-115">次のデータ ページを格納する前にテーブル行をクリアするコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0b301-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="0b301-116">データベース サーバーとのやり取りを減らすために、ローカルのキャッシュに、返された一定数の行を保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b301-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="0b301-117">データベース サーバーによってクエリ全体を返さずに次のレコード ページを返すには、SELECT ステートメントに限定的な抽出条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="0b301-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="0b301-118">上の例では最後に返されたレコードが保存されますが、次のコード サンプルに示すようにそのレコードを WHERE 句で使用するとクエリの開始点を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0b301-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b301-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b301-119">See also</span></span>
- [<span data-ttu-id="0b301-120">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="0b301-120">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="0b301-121">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="0b301-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
