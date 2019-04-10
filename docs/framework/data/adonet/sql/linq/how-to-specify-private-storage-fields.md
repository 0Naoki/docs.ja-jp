---
title: '方法: プライベート ストレージ フィールドを指定する'
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: e0928b2f2e817c8cc936f7aa1190229842a121a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195437"
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="62b02-102">方法: プライベート ストレージ フィールドを指定する</span><span class="sxs-lookup"><span data-stu-id="62b02-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="62b02-103">使用して、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>プロパティを<xref:System.Data.Linq.Mapping.DataAttribute>属性を基になるストレージ フィールドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="62b02-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="62b02-104">コード例については、「<xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62b02-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="62b02-105">基になるストレージ フィールドの名前を指定するには</span><span class="sxs-lookup"><span data-stu-id="62b02-105">To specify the name of an underlying storage field</span></span>  
  
1.  <span data-ttu-id="62b02-106"><xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="62b02-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="62b02-107">フィールドの名前を <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> プロパティの値として代入します。</span><span class="sxs-lookup"><span data-stu-id="62b02-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b02-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="62b02-108">See also</span></span>

- [<span data-ttu-id="62b02-109">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="62b02-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="62b02-110">方法: コード エディターを使用してエンティティ クラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="62b02-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
