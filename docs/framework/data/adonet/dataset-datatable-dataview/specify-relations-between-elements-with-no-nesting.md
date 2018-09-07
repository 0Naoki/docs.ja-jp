---
title: 入れ子になっていない要素間のリレーションの指定
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: d04a3d946b87c7203497313c6e21a75ef69f50eb
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44080105"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="86534-102">入れ子になっていない要素間のリレーションの指定</span><span class="sxs-lookup"><span data-stu-id="86534-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="86534-103">要素が入れ子になっていない場合、暗黙的なリレーションは作成されません。</span><span class="sxs-lookup"><span data-stu-id="86534-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="86534-104">使用して入れ子にされていない要素間のリレーションを明示的に指定することができます、ただし、 **msdata:Relationship**注釈。</span><span class="sxs-lookup"><span data-stu-id="86534-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="86534-105">次の例を XML スキーマを示しています、 **msdata:Relationship**間で注釈が指定されて、**順序**と**OrderDetail**である要素がありません入れ子になった。</span><span class="sxs-lookup"><span data-stu-id="86534-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="86534-106">**Msdata:Relationship**の子要素として注釈が指定されて、**スキーマ**要素。</span><span class="sxs-lookup"><span data-stu-id="86534-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
             xmlns:xs="http://www.w3.org/2001/XMLSchema"   
             xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"   
                            msdata:child="OrderDetail"   
                            msdata:parentkey="OrderNumber"   
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 <span data-ttu-id="86534-107">XML スキーマ定義言語 (XSD) スキーマのマッピング プロセスを作成、<xref:System.Data.DataSet>で**順序**と**OrderDetail**テーブルとリレーションシップが次に示すようにこれら 2 つのテーブル間で指定します。</span><span class="sxs-lookup"><span data-stu-id="86534-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="86534-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="86534-108">See Also</span></span>  
 [<span data-ttu-id="86534-109">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="86534-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="86534-110">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="86534-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="86534-111">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="86534-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
