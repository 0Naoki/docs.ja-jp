---
title: '方法: クエリでラムダ式を使用する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: 18f8823327719a120888df580779125be5d07b2c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965632"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a><span data-ttu-id="6b86e-102">方法: クエリでラムダ式を使用する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6b86e-102">How to: Use Lambda Expressions in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="6b86e-103">クエリ構文でラムダ式を直接使うことはありませんが、メソッドの呼び出しで使い、クエリ式はメソッドの呼び出しを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="6b86e-103">You do not use lambda expressions directly in query syntax, but you do use them in method calls, and query expressions can contain method calls.</span></span> <span data-ttu-id="6b86e-104">実際、一部のクエリ操作はメソッド構文でのみ表現できます。</span><span class="sxs-lookup"><span data-stu-id="6b86e-104">In fact, some query operations can only be expressed in method syntax.</span></span> <span data-ttu-id="6b86e-105">クエリ構文とメソッド構文の違いについて詳しくは、「[LINQ でのクエリ構文とメソッド構文](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b86e-105">For more information about the difference between query syntax and method syntax, see [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b86e-106">例</span><span class="sxs-lookup"><span data-stu-id="6b86e-106">Example</span></span>  
 <span data-ttu-id="6b86e-107">次の例を見ると、<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 標準クエリ演算子を使用することにより、メソッド ベースのクエリでラムダ式を使用する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="6b86e-107">The following example demonstrates how to use a lambda expression in a method-based query by using the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> standard query operator.</span></span> <span data-ttu-id="6b86e-108">この例の <xref:System.Linq.Enumerable.Where%2A> メソッドにはデリゲート型 <xref:System.Func%601> の入力パラメーターがあり、そのデリゲートは入力として整数を受け取ってブール値を返すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b86e-108">Note that the <xref:System.Linq.Enumerable.Where%2A> method in this example has an input parameter of the delegate type <xref:System.Func%601> and that delegate takes an integer as input and returns a Boolean.</span></span> <span data-ttu-id="6b86e-109">ラムダ式は、そのデリゲートに変換できます。</span><span class="sxs-lookup"><span data-stu-id="6b86e-109">The lambda expression can be converted to that delegate.</span></span> <span data-ttu-id="6b86e-110">これが <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> メソッドを使用する [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] のクエリであったなら、パラメーターの型は `Expression<Func<int,bool>>` になりますが、ラムダ式の表現はまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="6b86e-110">If this were a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query that used the <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> method, the parameter type would be an `Expression<Func<int,bool>>` but the lambda expression would look exactly the same.</span></span> <span data-ttu-id="6b86e-111">式の型の詳細については、<xref:System.Linq.Expressions.Expression?displayProperty=nameWithType> に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b86e-111">For more information on the Expression type, see <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#1)]  
  
## <a name="example"></a><span data-ttu-id="6b86e-112">例</span><span class="sxs-lookup"><span data-stu-id="6b86e-112">Example</span></span>  
 <span data-ttu-id="6b86e-113">次の例では、クエリ式のメソッド呼び出しでラムダ式を使う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b86e-113">The following example demonstrates how to use a lambda expression in a method call of a query expression.</span></span> <span data-ttu-id="6b86e-114"><xref:System.Linq.Enumerable.Sum%2A> 標準クエリ演算子はクエリ構文を使って呼び出すことができないため、ラムダが必要です。</span><span class="sxs-lookup"><span data-stu-id="6b86e-114">The lambda is necessary because the <xref:System.Linq.Enumerable.Sum%2A> standard query operator cannot be invoked by using query syntax.</span></span>  
  
 <span data-ttu-id="6b86e-115">このクエリは最初に、`GradeLevel` 列挙型で定義されている成績レベルに従って、学生をグループ分けします。</span><span class="sxs-lookup"><span data-stu-id="6b86e-115">The query first groups the students according to their grade level, as defined in the `GradeLevel` enum.</span></span> <span data-ttu-id="6b86e-116">その後、各グループについて、各学生の合計点数を追加します。</span><span class="sxs-lookup"><span data-stu-id="6b86e-116">Then for each group it adds the total scores for each student.</span></span> <span data-ttu-id="6b86e-117">これには、2 つの `Sum` 演算が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b86e-117">This requires two `Sum` operations.</span></span> <span data-ttu-id="6b86e-118">内側の `Sum` は各学生の合計点数を計算し、外側の `Sum` はグループ内のすべての学生の集計中の合計を保持します。</span><span class="sxs-lookup"><span data-stu-id="6b86e-118">The inner `Sum` calculates the total score for each student, and the outer `Sum` keeps a running, combined total for all students in the group.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6b86e-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6b86e-119">Compiling the Code</span></span>  
 <span data-ttu-id="6b86e-120">このコードを実行するには、メソッドをコピーして `StudentClass` (これは「[方法: オブジェクトのコレクションを照会する](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md)」で提供されています) に貼り付けた後、`Main` メソッドからそれを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6b86e-120">To run this code, copy and paste the method into the `StudentClass` that is provided in [How to: Query a Collection of Objects](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) and call it from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b86e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b86e-121">See also</span></span>

- [<span data-ttu-id="6b86e-122">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="6b86e-122">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="6b86e-123">式ツリー (C#)</span><span class="sxs-lookup"><span data-stu-id="6b86e-123">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
