---
title: 入れ子になっている要素に指定したリレーションシップの割り当て
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: cec7be5bea466c353e5320c04c76b37764a87e1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527524"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="3b52c-102">入れ子になっている要素に指定したリレーションシップの割り当て</span><span class="sxs-lookup"><span data-stu-id="3b52c-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="3b52c-103">スキーマを含めることができます、 **msdata:Relationship**注釈を明示的にスキーマの 2 つの要素間のマッピングを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b52c-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="3b52c-104">2 つの要素で指定された**msdata:Relationship**スキーマで入れ子にできますが、する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3b52c-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="3b52c-105">マッピング プロセスを使用して**msdata:Relationship**で 2 つの列の間で主キー/外部キーのリレーションシップを生成するスキーマ。</span><span class="sxs-lookup"><span data-stu-id="3b52c-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="3b52c-106">次の例を XML スキーマを示しています、 **OrderDetail**要素の子要素は、**順序**します。</span><span class="sxs-lookup"><span data-stu-id="3b52c-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="3b52c-107">**Msdata:Relationship**この親子リレーションシップを識別することを指定して、 **OrderNumber** 、生成された**順序**テーブルに関連する、**OrderNo** 、生成された**OrderDetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="3b52c-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
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
  
 <span data-ttu-id="3b52c-108">XML スキーマの割り当て処理によって <xref:System.Data.DataSet> に作成される内容は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3b52c-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="3b52c-109">**順序**と**OrderDetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="3b52c-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   <span data-ttu-id="3b52c-110">間のリレーションシップ、**順序**と**OrderDetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="3b52c-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="3b52c-111">**入れ子になった**このリレーションシップのプロパティに設定されて**True**ため、**順序**と**OrderDetail**スキーマで要素が入れ子になった.</span><span class="sxs-lookup"><span data-stu-id="3b52c-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="3b52c-112">割り当て処理によって制約は作成されません。</span><span class="sxs-lookup"><span data-stu-id="3b52c-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b52c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b52c-113">See also</span></span>
- [<span data-ttu-id="3b52c-114">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="3b52c-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="3b52c-115">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="3b52c-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="3b52c-116">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="3b52c-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
