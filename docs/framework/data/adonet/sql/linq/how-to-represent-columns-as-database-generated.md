---
title: '方法: データベース生成として列を表す'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 572da93c216694b496dc5220af66bc00229ccd00
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518346"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="755b2-102">方法: データベース生成として列を表す</span><span class="sxs-lookup"><span data-stu-id="755b2-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="755b2-103">使用して、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>プロパティを<xref:System.Data.Linq.Mapping.ColumnAttribute>データベース生成列を表すフィールドまたはプロパティを指定する属性。</span><span class="sxs-lookup"><span data-stu-id="755b2-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="755b2-104">コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="755b2-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="755b2-105">データベース生成列を表すフィールドまたはプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="755b2-105">To designate a field or property as representing a database-generated column</span></span>  
  
1.  <span data-ttu-id="755b2-106"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="755b2-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="755b2-107">プロパティ値を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="755b2-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="755b2-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="755b2-108">See also</span></span>
- [<span data-ttu-id="755b2-109">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="755b2-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="755b2-110">方法: コード エディターを使用してエンティティ クラスをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="755b2-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
