---
title: '方法: クラス メンバーとして列を表す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 7a772de27583f35b18a4fa5854e61768443e5ba5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652561"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="a7753-102">方法: クラス メンバーとして列を表す</span><span class="sxs-lookup"><span data-stu-id="a7753-102">How to: Represent Columns as Class Members</span></span>
<span data-ttu-id="a7753-103">使用して、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute>フィールドまたはプロパティをデータベース列に関連付ける属性。</span><span class="sxs-lookup"><span data-stu-id="a7753-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="a7753-104">フィールドまたはプロパティをデータベース列に対応付けるには</span><span class="sxs-lookup"><span data-stu-id="a7753-104">To map a field or property to a database column</span></span>  
  
-   <span data-ttu-id="a7753-105">プロパティまたはフィールドの宣言に <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="a7753-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7753-106">例</span><span class="sxs-lookup"><span data-stu-id="a7753-106">Example</span></span>  
 <span data-ttu-id="a7753-107">次の例では、`CustomerID` クラス内の `Customer` フィールドを `CustomerID` データベース テーブル内の `Customers` 列に対応付けます。</span><span class="sxs-lookup"><span data-stu-id="a7753-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="a7753-108">名前が推論できる場合は、<xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> プロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a7753-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="a7753-109">名前を指定しない場合は、プロパティまたはフィールドと同じ名前であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="a7753-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7753-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7753-110">See also</span></span>
- [<span data-ttu-id="a7753-111">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="a7753-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="a7753-112">方法: コード エディターを使用してエンティティ クラスをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="a7753-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
