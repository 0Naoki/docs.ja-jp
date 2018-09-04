---
title: 厳密に型指定された DataSet の生成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 9accfb68c57384e12a59bae40ebe30a2d3e22877
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526489"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="f2466-102">厳密に型指定された DataSet の生成</span><span class="sxs-lookup"><span data-stu-id="f2466-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="f2466-103">XML スキーマ定義言語 (XSD) 標準に準拠する XML スキーマがあれば、<xref:System.Data.DataSet> に付属の XSD.exe ツールを使用して、厳密に型指定された [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)] を生成できます。</span><span class="sxs-lookup"><span data-stu-id="f2466-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="f2466-104">(データベース テーブルから xsd を作成するを参照してください。<xref:System.Data.DataSet.WriteXmlSchema%2A>または[Visual Studio でのデータセットの操作](https://msdn.microsoft.com/library/8bw9ksd6.aspx))。</span><span class="sxs-lookup"><span data-stu-id="f2466-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](https://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
 <span data-ttu-id="f2466-105">次のコードを生成するための構文を示しています、**データセット**このツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2466-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="f2466-106">この構文では、`/d`ディレクティブを生成するツールに指示を**データセット**、および`/l:`(たとえば、c# または Visual Basic .NET) を使用するには、どのような言語、ツールに指示します。</span><span class="sxs-lookup"><span data-stu-id="f2466-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="f2466-107">省略可能な`/eld`ディレクティブは、使用できることを指定します[!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)]に対して生成されたクエリに**データセット。**</span><span class="sxs-lookup"><span data-stu-id="f2466-107">The optional `/eld` directive specifies that you can use [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] to query against the generated **DataSet.**</span></span> <span data-ttu-id="f2466-108">このオプションは、`/d` オプションと組み合わせて指定します。</span><span class="sxs-lookup"><span data-stu-id="f2466-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="f2466-109">詳細については、次を参照してください。[型指定されたデータセットのクエリを実行する](../../../../../docs/framework/data/adonet/querying-typed-datasets.md)します。</span><span class="sxs-lookup"><span data-stu-id="f2466-109">For more information, see [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="f2466-110">省略可能な`/n:`ディレクティブもの名前空間を生成するツールに指示、**データセット**と呼ばれる**XSDSchema.Namespace**します。</span><span class="sxs-lookup"><span data-stu-id="f2466-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="f2466-111">コマンドの出力は XSDSchemaFileName.cs で、ADO.NET アプリケーションでコンパイルおよび使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2466-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="f2466-112">生成されたコードをライブラリまたはモジュールとしてコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="f2466-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="f2466-113">C# コンパイラ (csc.exe) を使用して、生成されたコードをライブラリとしてコンパイルする構文を次のコードで示します。</span><span class="sxs-lookup"><span data-stu-id="f2466-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="f2466-114">`/t:` ディレクティブはライブラリとしてコンパイルすることをツールに知らせ、`/r:` ディレクティブはコンパイルに必要な依存ライブラリを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2466-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="f2466-115">コマンドの出力は XSDSchemaFileName.dll で、`/r:` ディレクティブによる ADO.NET アプリケーションのコンパイル時にコンパイラに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2466-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="f2466-116">ADO.NET アプリケーションの XSD.exe に渡された名前空間にアクセスする構文を次のコードで示します。</span><span class="sxs-lookup"><span data-stu-id="f2466-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="f2466-117">次のコード例は、型指定された**データセット**という**CustomerDataSet**から顧客の一覧を読み込む、 **Northwind**データベース。</span><span class="sxs-lookup"><span data-stu-id="f2466-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="f2466-118">使用して、データが読み込まれると、**入力**メソッド、例は、各顧客をループ処理、**顧客**、型指定されたを使用してテーブル**CustomersRow** (**DataRow**) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f2466-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="f2466-119">これによりへの直接アクセス、 **CustomerID**を経由している列、 **DataColumnCollection**します。</span><span class="sxs-lookup"><span data-stu-id="f2466-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 <span data-ttu-id="f2466-120">例に使用された XML スキーマを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2466-120">Following is the XML Schema used for the example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2466-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2466-121">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="f2466-122">型指定されたデータセット</span><span class="sxs-lookup"><span data-stu-id="f2466-122">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="f2466-123">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="f2466-123">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="f2466-124">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="f2466-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
