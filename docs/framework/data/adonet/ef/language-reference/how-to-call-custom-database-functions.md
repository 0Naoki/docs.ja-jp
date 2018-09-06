---
title: カスタム データベース関数を呼び出す方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: 4e7c94dce5b50fe93f00aaaa72206be3394faf62
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43788663"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="cd4d5-102">カスタム データベース関数を呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="cd4d5-102">How to: Call Custom Database Functions</span></span>
<span data-ttu-id="cd4d5-103">ここでは、データベースで定義されたカスタム関数を LINQ Entities クエリから呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="cd4d5-104">LINQ to Entities クエリから呼び出されるデータベース関数は、データベース内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="cd4d5-105">データベース内で関数を実行すると、アプリケーションのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-105">Executing functions in the database can improve application performance.</span></span>  
  
 <span data-ttu-id="cd4d5-106">下に示す手順は、カスタム データベース関数を呼び出す方法の概要をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="cd4d5-107">各手順の詳しい説明は、その後の例で示します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-107">The example that follows provides more detail about the steps in the procedure.</span></span>  
  
### <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="cd4d5-108">データベースで定義されるカスタム関数を呼び出すには</span><span class="sxs-lookup"><span data-stu-id="cd4d5-108">To call custom functions that are defined in the database</span></span>  
  
1.  <span data-ttu-id="cd4d5-109">データベースにカスタム関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-109">Create a custom function in your database.</span></span>  
  
     <span data-ttu-id="cd4d5-110">SQL Server でカスタム関数を作成する方法の詳細については、次を参照してください。 [CREATE FUNCTION (Transact SQL)](https://go.microsoft.com/fwlink/?LinkID=139871)します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span></span>  
  
2.  <span data-ttu-id="cd4d5-111">関数を .edmx ファイルのストア スキーマ定義言語 (SSDL) で宣言します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="cd4d5-112">関数の名前は、データベースで宣言される関数と同じ名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-112">The name of the function must be the same as the name of the function declared in the database.</span></span>  
  
     <span data-ttu-id="cd4d5-113">詳細については、次を参照してください。[関数要素 (SSDL)](https://msdn.microsoft.com/library/b60cfc3d-8b93-423e-8c99-b867256640a4)します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-113">For more information, see [Function Element (SSDL)](https://msdn.microsoft.com/library/b60cfc3d-8b93-423e-8c99-b867256640a4).</span></span>  
  
3.  <span data-ttu-id="cd4d5-114">対応するメソッドをアプリケーション コードのクラスに追加して、<xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> をそのメソッドに適用する必要があります。属性の <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> パラメーターと <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> パラメーターが、それぞれ概念モデルの名前空間名と概念モデルの関数名であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="cd4d5-115">LINQ の関数名解決では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-115">Function name resolution for LINQ is case sensitive.</span></span>  
  
4.  <span data-ttu-id="cd4d5-116">LINQ to Entities クエリからメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-116">Call the method in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd4d5-117">例</span><span class="sxs-lookup"><span data-stu-id="cd4d5-117">Example</span></span>  
 <span data-ttu-id="cd4d5-118">次の例は、カスタム データベース関数を LINQ to Entities クエリから呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="cd4d5-119">この例では、School モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-119">The example uses the School model.</span></span> <span data-ttu-id="cd4d5-120">School モデルについては、次を参照してください。 [School サンプル データベースの作成](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)と[School .edmx ファイルを生成する](https://msdn.microsoft.com/library/c48b3907-a8be-4fe6-884c-e95af1852758)します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-120">For information about the School model, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) and [Generating the School .edmx File](https://msdn.microsoft.com/library/c48b3907-a8be-4fe6-884c-e95af1852758).</span></span>  
  
 <span data-ttu-id="cd4d5-121">次のコードは、`AvgStudentGrade` 関数を School のサンプル データベースに追加しています。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd4d5-122">カスタム データベース関数を呼び出す手順は、データベース サーバーとは無関係にすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="cd4d5-123">ただし、下に示すコードは、SQL Server データベースで関数を作成する方法に固有のものです。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="cd4d5-124">他のデータベース サーバーでカスタム関数を作成する場合には、コードは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-124">The code for creating a custom function in other database servers might differ.</span></span>  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## <a name="example"></a><span data-ttu-id="cd4d5-125">例</span><span class="sxs-lookup"><span data-stu-id="cd4d5-125">Example</span></span>  
 <span data-ttu-id="cd4d5-126">次に、関数を .edmx ファイルのストア スキーマ定義言語 (SSDL) で宣言します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-126">Next, declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="cd4d5-127">次のコードは、`AvgStudentGrade` 関数を SSDL で宣言しています。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-127">the following code declares the `AvgStudentGrade` function in SSDL:</span></span>  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## <a name="example"></a><span data-ttu-id="cd4d5-128">例</span><span class="sxs-lookup"><span data-stu-id="cd4d5-128">Example</span></span>  
 <span data-ttu-id="cd4d5-129">次に、メソッドを作成して、SSDL で宣言された関数にマップします。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-129">Now create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="cd4d5-130">次のクラスのメソッドは、<xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> を使用して SSDL (上を参照) で定義される関数にマップされます。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="cd4d5-131">このメソッドが呼び出されると、データベース内の対応する関数が実行されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-131">When this method is called, the corresponding function in the database is executed.</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="cd4d5-132">例</span><span class="sxs-lookup"><span data-stu-id="cd4d5-132">Example</span></span>  
 <span data-ttu-id="cd4d5-133">最後に、メソッドを LINQ to Entities クエリで呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="cd4d5-134">次のコードは、学生の姓と平均の成績をコンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="cd4d5-134">The following code displays students' last names and average grades to the console:</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="cd4d5-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd4d5-135">See Also</span></span>  
 [<span data-ttu-id="cd4d5-136">.edmx ファイルの概要</span><span class="sxs-lookup"><span data-stu-id="cd4d5-136">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="cd4d5-137">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="cd4d5-137">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
