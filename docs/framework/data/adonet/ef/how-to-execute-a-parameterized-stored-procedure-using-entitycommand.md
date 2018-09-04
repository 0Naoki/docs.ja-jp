---
title: EntityCommand を使用してパラメーター化されたストアド プロシージャを実行する方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: 973a1f3980c979b201b083eed3eb20a64461a3cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507414"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="fa6bf-102">EntityCommand を使用してパラメーター化されたストアド プロシージャを実行する方法</span><span class="sxs-lookup"><span data-stu-id="fa6bf-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="fa6bf-103">このトピックでは、<xref:System.Data.EntityClient.EntityCommand> クラスを使用して、パラメーター化されたストアド プロシージャを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fa6bf-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="fa6bf-104">この例のコードを実行するには</span><span class="sxs-lookup"><span data-stu-id="fa6bf-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="fa6bf-105">追加、 [School モデル](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)をプロジェクトに使用するプロジェクトを構成して、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="fa6bf-105">Add the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="fa6bf-106">詳細については、次を参照してください。[方法: Entity Data Model ウィザードを使用して、](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)します。</span><span class="sxs-lookup"><span data-stu-id="fa6bf-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="fa6bf-107">アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="fa6bf-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="fa6bf-108">`GetStudentGrades` ストアド プロシージャをインポートし、戻り値の型として `CourseGrade` エンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="fa6bf-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="fa6bf-109">ストアド プロシージャをインポートする方法については、次を参照してください。[方法: ストアド プロシージャをインポート](https://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d)します。</span><span class="sxs-lookup"><span data-stu-id="fa6bf-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](https://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa6bf-110">例</span><span class="sxs-lookup"><span data-stu-id="fa6bf-110">Example</span></span>  
 <span data-ttu-id="fa6bf-111">次のコードでは、`GetStudentGrades` ストアド プロシージャが実行されます。`StudentId` は必須パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="fa6bf-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="fa6bf-112">結果は <xref:System.Data.EntityClient.EntityDataReader> によって読み取られます。</span><span class="sxs-lookup"><span data-stu-id="fa6bf-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="fa6bf-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa6bf-113">See Also</span></span>  
 [<span data-ttu-id="fa6bf-114">Entity Framework 用の EntityClient プロバイダー</span><span class="sxs-lookup"><span data-stu-id="fa6bf-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
