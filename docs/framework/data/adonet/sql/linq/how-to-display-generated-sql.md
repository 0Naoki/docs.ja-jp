---
title: '方法: 生成された SQL を表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 8a69b3ae83d7f701428b3183f2b80e0d44a06537
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103624"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="90bf8-102">方法: 生成された SQL を表示する</span><span class="sxs-lookup"><span data-stu-id="90bf8-102">How to: Display Generated SQL</span></span>
<span data-ttu-id="90bf8-103"><xref:System.Data.Linq.DataContext.Log%2A> プロパティを使用して、クエリに対して生成された SQL コードを表示し、処理を変更できます。</span><span class="sxs-lookup"><span data-stu-id="90bf8-103">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="90bf8-104">この方法は、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の機能を理解し、特定の問題をデバッグするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="90bf8-104">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90bf8-105">例</span><span class="sxs-lookup"><span data-stu-id="90bf8-105">Example</span></span>  
 <span data-ttu-id="90bf8-106"><xref:System.Data.Linq.DataContext.Log%2A> プロパティを使用して、コードを実行する前にコンソール ウィンドウに SQL コードを表示するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="90bf8-106">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="90bf8-107">このプロパティは、query、insert、update、および delete の各コマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="90bf8-107">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="90bf8-108">コンソール ウィンドウの行は、Visual Basic を実行するときに参照またはC#次のコード。</span><span class="sxs-lookup"><span data-stu-id="90bf8-108">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="90bf8-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="90bf8-109">See also</span></span>

- [<span data-ttu-id="90bf8-110">デバッグのサポート</span><span class="sxs-lookup"><span data-stu-id="90bf8-110">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
