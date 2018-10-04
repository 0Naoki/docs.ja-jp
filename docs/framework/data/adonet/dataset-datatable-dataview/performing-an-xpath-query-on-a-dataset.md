---
title: DataSet に対する XPath クエリの実行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: a1718429360d79c4628e9948eb1b052c3ac01964
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266131"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="595a4-102">DataSet に対する XPath クエリの実行</span><span class="sxs-lookup"><span data-stu-id="595a4-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="595a4-103">同期済みの間のリレーションシップ<xref:System.Data.DataSet>と<xref:System.Xml.XmlDataDocument>XML を使用するのには、アクセス、XML Path Language (XPath) クエリなどのサービス、 **XmlDataDocument**特定の機能を実行できます簡単にアクセスするよりも、**データセット**直接します。</span><span class="sxs-lookup"><span data-stu-id="595a4-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="595a4-104">使用してではなく、たとえば、**選択**のメソッド、<xref:System.Data.DataTable>内の他のテーブルにリレーションシップをナビゲートする、**データセット**で XPath クエリを実行することができます、 **XmlDataDocument**と同期される、**データセット**の形式で XML 要素の一覧を取得する、<xref:System.Xml.XmlNodeList>します。</span><span class="sxs-lookup"><span data-stu-id="595a4-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="595a4-105">内のノード、 **XmlNodeList**としてキャスト<xref:System.Xml.XmlElement>ノードに渡すことができます、 **GetRowFromElement**のメソッド、 **XmlDataDocument**を一致を返す<xref:System.Data.DataRow>は同期済みテーブルの行への参照**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="595a4-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="595a4-106">たとえば、次に示すコード サンプルでは孫 XPath クエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="595a4-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="595a4-107">**データセット**は 3 つのテーブルで塗りつぶされます:**顧客**、**注文**、および**OrderDetails**します。</span><span class="sxs-lookup"><span data-stu-id="595a4-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="595a4-108">サンプルでは、親子関係が最初に作成の間、**顧客**と**注文**テーブル、および、**注文**と**OrderDetails**テーブル。</span><span class="sxs-lookup"><span data-stu-id="595a4-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="595a4-109">返す XPath クエリが実行を**XmlNodeList**の**顧客**ノードが、孫**OrderDetails**ノードには、 **ProductID**43 の値を持つノード。</span><span class="sxs-lookup"><span data-stu-id="595a4-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="595a4-110">基本的には、サンプルを使用して、XPath クエリを持つ製品を注文した顧客を特定、 **ProductID** 43 の。</span><span class="sxs-lookup"><span data-stu-id="595a4-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="595a4-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="595a4-111">See Also</span></span>  
 [<span data-ttu-id="595a4-112">DataSet と XmlDataDocument の同期</span><span class="sxs-lookup"><span data-stu-id="595a4-112">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [<span data-ttu-id="595a4-113">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="595a4-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
