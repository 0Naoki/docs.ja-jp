---
title: DataSet への XSLT 変換の適用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: b665fc9593cd73e759625bdfd537581958f8734d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595566"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a><span data-ttu-id="c4325-102">DataSet への XSLT 変換の適用</span><span class="sxs-lookup"><span data-stu-id="c4325-102">Applying an XSLT Transform to a DataSet</span></span>
<span data-ttu-id="c4325-103">**WriteXml**のメソッド、<xref:System.Data.DataSet>の内容を記述することができます、**データセット**XML データとして。</span><span class="sxs-lookup"><span data-stu-id="c4325-103">The **WriteXml** method of the <xref:System.Data.DataSet> enables you to write the contents of a **DataSet** as XML data.</span></span> <span data-ttu-id="c4325-104">一般的なタスクは、XSLT (XSL Transformation) を使用してこの XML を別の形式へ変換する操作です。</span><span class="sxs-lookup"><span data-stu-id="c4325-104">A common task is to then transform that XML to another format using XSL transformations (XSLT).</span></span> <span data-ttu-id="c4325-105">ただし、同期、**データセット**で、<xref:System.Xml.XmlDataDocument>の内容に XSLT スタイル シートを適用することができます、**データセット**最初の内容を記述することがなく、 **データセット**を使用して XML データとして**WriteXml**します。</span><span class="sxs-lookup"><span data-stu-id="c4325-105">However, synchronizing a **DataSet** with an <xref:System.Xml.XmlDataDocument> enables you to apply an XSLT stylesheet to the contents of a **DataSet** without having to first write the contents of the **DataSet** as XML data using **WriteXml**.</span></span>  
  
 <span data-ttu-id="c4325-106">次の例を**データセット**テーブルとリレーションシップでは、同期、**データセット**で、 **XmlDataDocument**、し、の一部を書き込みます**データセット**XSLT スタイル シートを使用してファイルを HTML として。</span><span class="sxs-lookup"><span data-stu-id="c4325-106">The following example populates a **DataSet** with tables and relationships, synchronizes the **DataSet** with an **XmlDataDocument**, and writes a portion of the **DataSet** as an HTML file using an XSLT stylesheet.</span></span> <span data-ttu-id="c4325-107">次のコードは、XSLT スタイルシートの内容です。</span><span class="sxs-lookup"><span data-stu-id="c4325-107">Following are the contents of the XSLT stylesheet.</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
<xsl:template match="CustomerOrders">  
  <HTML>  
  <STYLE>  
  BODY {font-family:verdana;font-size:9pt}  
  TD   {font-size:8pt}  
  </STYLE>  
    <BODY>  
    <TABLE BORDER="1">  
      <xsl:apply-templates select="Customers"/>  
    </TABLE>  
    </BODY>  
  </HTML>  
</xsl:template>  
  
<xsl:template match="Customers">  
    <TR><TD>  
      <xsl:value-of select="ContactName"/>, <xsl:value-of select="Phone"/><BR/>  
    </TD></TR>  
      <xsl:apply-templates select="Orders"/>  
</xsl:template>  
  
<xsl:template match="Orders">  
  <TABLE BORDER="1">  
    <TR><TD valign="top"><B>Order:</B></TD><TD valign="top"><xsl:value-of select="OrderID"/></TD></TR>  
    <TR><TD valign="top"><B>Date:</B></TD><TD valign="top"><xsl:value-of select="OrderDate"/></TD></TR>  
    <TR><TD valign="top"><B>Ship To:</B></TD>  
        <TD valign="top"><xsl:value-of select="ShipName"/><BR/>  
        <xsl:value-of select="ShipAddress"/><BR/>  
        <xsl:value-of select="ShipCity"/>, <xsl:value-of select="ShipRegion"/>  <xsl:value-of select="ShipPostalCode"/><BR/>  
        <xsl:value-of select="ShipCountry"/></TD></TR>  
  </TABLE>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="c4325-108">次のコードの塗りつぶし、**データセット**し、XSLT スタイル シートを適用します。</span><span class="sxs-lookup"><span data-stu-id="c4325-108">The following code fills the **DataSet** and applies the XSLT style sheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4325-109">XSLT スタイル シートを適用する場合、**データセット**リレーションを格納している、設定した場合に最適なパフォーマンスを実現する、**入れ子になった**のプロパティ、<xref:System.Data.DataRelation>に**true**ごとにリレーションシップを入れ子になった。</span><span class="sxs-lookup"><span data-stu-id="c4325-109">If you are applying an XSLT style sheet to a **DataSet** that contains relations, you achieve best performance if you set the **Nested** property of the <xref:System.Data.DataRelation> to **true** for each nested relation.</span></span> <span data-ttu-id="c4325-110">これにより、階層を自然な順番で上から下へと進みながらデータを変換する XSLT スタイル シートを利用できるようになります。パフォーマンスに大きく影響する XPath ロケーション軸 (たとえば、スタイル シートのノード テスト式での preceding-sibling や following-sibling) を使用して階層をたどる必要はなくなります。</span><span class="sxs-lookup"><span data-stu-id="c4325-110">This allows you to use XSLT style sheets that implement natural top-down processing to navigate the hierarchy and transform the data, as opposed to using performance-intensive XPath location axes (for example, preceding-sibling and following-sibling in style sheet node test expressions) to navigate it.</span></span> <span data-ttu-id="c4325-111">入れ子になったリレーションの詳細については、次を参照してください。 [Datarelation の入れ子](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)します。</span><span class="sxs-lookup"><span data-stu-id="c4325-111">For more information on nested relations, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim xslTran As XslTransform = New XslTransform  
xslTran.Load("transform.xsl")  
  
Dim writer As XmlTextWriter = New XmlTextWriter( _  
  "xslt_output.html", System.Text.Encoding.UTF8)  
  
xslTran.Transform(xmlDoc, Nothing, writer)  
writer.Close()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
DataSet custDS = new DataSet("CustomerDataSet");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(custDS, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(custDS, "Orders");  
  
connection.Close();  
  
custDS.Relations.Add("CustOrders",  
  custDS.Tables["Customers"].Columns["CustomerID"],  
                     custDS.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(custDS);   
  
XslTransform xslTran = new XslTransform();  
xslTran.Load("transform.xsl");  
  
XmlTextWriter writer = new XmlTextWriter("xslt_output.html",   
  System.Text.Encoding.UTF8);  
  
xslTran.Transform(xmlDoc, null, writer);  
writer.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4325-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4325-112">See also</span></span>
- [<span data-ttu-id="c4325-113">DataSet と XmlDataDocument の同期</span><span class="sxs-lookup"><span data-stu-id="c4325-113">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="c4325-114">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="c4325-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
