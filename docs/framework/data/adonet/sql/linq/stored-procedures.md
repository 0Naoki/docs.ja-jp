---
title: ストアド プロシージャ
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 9201965192f300de62679c1e5be75cf98a24e700
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917944"
---
# <a name="stored-procedures"></a><span data-ttu-id="80830-102">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="80830-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="80830-103">オブジェクト モデルのメソッドを使用して、データベース内のストアド プロシージャを表します。</span><span class="sxs-lookup"><span data-stu-id="80830-103">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="80830-104"><xref:System.Data.Linq.Mapping.FunctionAttribute> 属性、および必要に応じて <xref:System.Data.Linq.Mapping.ParameterAttribute> 属性を適用することによって、メソッドをストアド プロシージャとして指定します。</span><span class="sxs-lookup"><span data-stu-id="80830-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="80830-105">詳細については、次を参照してください。 [LINQ to SQL オブジェクト モデル](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="80830-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="80830-106">Visual Studio を使用している開発者は通常の使用、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]ストアド プロシージャにマップします。</span><span class="sxs-lookup"><span data-stu-id="80830-106">Developers using Visual Studio would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map stored procedures.</span></span> <span data-ttu-id="80830-107">このセクションのトピックでは、自分でコードを作成する場合に、アプリケーション内でこれらのメソッドを記述および呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80830-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80830-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="80830-108">In This Section</span></span>  
 [<span data-ttu-id="80830-109">方法: 行セットを返す</span><span class="sxs-lookup"><span data-stu-id="80830-109">How to: Return Rowsets</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 <span data-ttu-id="80830-110">データ行を返す方法および入力パラメーターの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80830-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="80830-111">方法: パラメーターを受け取るストアド プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="80830-111">How to: Use Stored Procedures that Take Parameters</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="80830-112">入力パラメーターおよび出力パラメーターの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80830-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="80830-113">方法: 複数の結果形状が割り当てられたストアド プロシージャを使用して、</span><span class="sxs-lookup"><span data-stu-id="80830-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="80830-114">同じストアド プロシージャで複数の形状の結果を返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80830-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="80830-115">方法: シーケンシャルな結果形状が割り当てられたストアド プロシージャを使用して、</span><span class="sxs-lookup"><span data-stu-id="80830-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="80830-116">リターン シーケンスが既知の場合に複数の形状を返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80830-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="80830-117">ストアド プロシージャによる操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="80830-117">Customizing Operations By Using Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="80830-118">ストアド プロシージャを使用して挿入、更新、および削除の操作を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80830-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="80830-119">ストアド プロシージャのみによる操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="80830-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="80830-120">ストアド プロシージャのみを使用して挿入、更新、および削除の操作を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80830-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="80830-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="80830-121">Related Sections</span></span>  
 [<span data-ttu-id="80830-122">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="80830-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="80830-123">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] オブジェクト モデルを作成および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80830-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="80830-124">チュートリアル: ストアド プロシージャ (Visual Basic) の使用のみ</span><span class="sxs-lookup"><span data-stu-id="80830-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="80830-125">Visual Basic でストアド プロシージャを使用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="80830-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="80830-126">チュートリアル: ストアド プロシージャを使用してのみ (C#)</span><span class="sxs-lookup"><span data-stu-id="80830-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="80830-127">C# でストアド プロシージャを使用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="80830-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
