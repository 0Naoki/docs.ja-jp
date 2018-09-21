---
title: 入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 73cd8a83021934de3b8e3bf494a4f59dd32e183c
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2018
ms.locfileid: "46493621"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="e2223-102">入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て</span><span class="sxs-lookup"><span data-stu-id="e2223-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="e2223-103">XML スキーマ言語定義 (XSD) スキーマでは、複数の複合型を入れ子にして指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2223-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="e2223-104">この場合、割り当て処理には既定の割り当てが適用されます。その際、<xref:System.Data.DataSet> に作成される内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e2223-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="e2223-105">複合型 (親および子) それぞれに対して 1 つのテーブル。</span><span class="sxs-lookup"><span data-stu-id="e2223-105">One table for each of the complex types (parent and child).</span></span>  
  
-   <span data-ttu-id="e2223-106">1 つ主キー列が追加テーブル定義ごとにという名前の親に unique 制約が存在しない場合*TableName*_id のデータ型、 *TableName*親テーブルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2223-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
-   <span data-ttu-id="e2223-107">主キーとして追加の列を識別する親テーブルに主キー制約 (設定して、 **IsPrimaryKey**プロパティを**True**)。</span><span class="sxs-lookup"><span data-stu-id="e2223-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="e2223-108">制約には、Constraint\# (\# は、1、2、3 など) という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="e2223-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="e2223-109">たとえば、最初の制約の既定の名前は Constraint1 となります。</span><span class="sxs-lookup"><span data-stu-id="e2223-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
-   <span data-ttu-id="e2223-110">子テーブルの外部キー制約により、追加された列が親テーブルの主キーを参照する外部キーとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="e2223-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="e2223-111">制約名が*ParentTable_ChildTable*場所*ParentTable*親テーブルの名前を指定および*ChildTable*子テーブルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2223-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
-   <span data-ttu-id="e2223-112">その結果、親テーブルと子テーブル間のデータが関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="e2223-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="e2223-113">次の例は、スキーマ、 **OrderDetail**の子要素は、**順序**します。</span><span class="sxs-lookup"><span data-stu-id="e2223-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
   <xs:complexType>  
     <xs:choice maxOccurs="unbounded">  
       <xs:element name="Order">  
         <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="e2223-114">XML スキーマの割り当て処理では、次の作成、**データセット**:</span><span class="sxs-lookup"><span data-stu-id="e2223-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
-   <span data-ttu-id="e2223-115">**順序**と**OrderDetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="e2223-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   <span data-ttu-id="e2223-116">Unique 制約、**順序**テーブル。</span><span class="sxs-lookup"><span data-stu-id="e2223-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="e2223-117">なお、 **IsPrimaryKey**プロパティに設定されて**True**します。</span><span class="sxs-lookup"><span data-stu-id="e2223-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   <span data-ttu-id="e2223-118">外部キー制約、 **OrderDetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="e2223-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   <span data-ttu-id="e2223-119">間のリレーションシップ、**順序**と**OrderDetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="e2223-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="e2223-120">**入れ子になった**このリレーションシップのプロパティに設定されて**True**ため、**順序**と**OrderDetail**スキーマで要素が入れ子になった.</span><span class="sxs-lookup"><span data-stu-id="e2223-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e2223-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2223-121">See Also</span></span>  
 [<span data-ttu-id="e2223-122">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="e2223-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="e2223-123">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="e2223-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="e2223-124">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="e2223-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
