---
title: '方法: プロシージャ (Visual Basic) を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 06fed04a0ebe7a0b3111a94308d15d01bcf47c1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636535"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="1b839-102">方法: プロシージャ (Visual Basic) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1b839-102">How to: Create a Procedure (Visual Basic)</span></span>
<span data-ttu-id="1b839-103">開始の宣言ステートメントの間のプロシージャを囲む (`Sub`または`Function`) と終了の宣言ステートメント (`End Sub`または`End Function`)。</span><span class="sxs-lookup"><span data-stu-id="1b839-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="1b839-104">すべての手順のコードは、これらのステートメントの範囲です。</span><span class="sxs-lookup"><span data-stu-id="1b839-104">All the procedure's code lies between these statements.</span></span>  
  
 <span data-ttu-id="1b839-105">プロシージャは、最初と最後のステートメントが、他のプロシージャの外部にある必要がありますので、別のプロシージャを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="1b839-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>  
  
 <span data-ttu-id="1b839-106">さまざまな場所で同じタスクを実行するコードがあれば、プロシージャの 1 回として、タスクを記述し、コード内の異なる場所から呼び出すできます。</span><span class="sxs-lookup"><span data-stu-id="1b839-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="1b839-107">値を返さないプロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="1b839-107">To create a procedure that does not return a value</span></span>  
  
1.  <span data-ttu-id="1b839-108">その他のプロシージャの外側を使用して、`Sub`ステートメントの後に、`End Sub`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1b839-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="1b839-109">`Sub`ステートメントでは、以下の`Sub`キーワード、プロシージャ、かっこで囲まれたパラメーター リストの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1b839-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="1b839-110">間のプロシージャのコード ステートメントを配置、`Sub`と`End Sub`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1b839-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="1b839-111">値を返すプロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="1b839-111">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="1b839-112">その他のプロシージャの外側を使用して、`Function`ステートメントの後に、`End Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1b839-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="1b839-113">`Function`ステートメントでは、以下の`Function`パラメーター リストをかっこで、プロシージャの名前を持つキーワードをクリックし、`As`戻り値のデータ型を指定する句。</span><span class="sxs-lookup"><span data-stu-id="1b839-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>  
  
3.  <span data-ttu-id="1b839-114">間のプロシージャのコード ステートメントを配置、`Function`と`End Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1b839-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
4.  <span data-ttu-id="1b839-115">使用して、`Return`ステートメントを呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="1b839-115">Use a `Return` statement to return the value to the calling code.</span></span>  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="1b839-116">繰り返し発生する以前のコード ブロックで、新しいプロシージャを接続するには</span><span class="sxs-lookup"><span data-stu-id="1b839-116">To connect your new procedure with the old, repetitive blocks of code</span></span>  
  
1.  <span data-ttu-id="1b839-117">古いコードのアクセス権がある場所に新しいプロシージャを定義することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b839-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>  
  
2.  <span data-ttu-id="1b839-118">呼び出す 1 つのステートメントで反復的なタスクを実行するステートメントを置き換える、古い、繰り返し発生するコード ブロックで、`Sub`または`Function`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="1b839-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>  
  
3.  <span data-ttu-id="1b839-119">プロシージャがある場合、`Function`値を返すことを呼び出し元のステートメントは、変数に格納することなど、返された値を持つ操作を実行します。 そうしないと、値は失われますを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b839-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b839-120">例</span><span class="sxs-lookup"><span data-stu-id="1b839-120">Example</span></span>  
 <span data-ttu-id="1b839-121">次`Function`プロシージャは、最長の辺またはの他の 2 つの辺の値を指定された直角三角形の斜辺を計算します。</span><span class="sxs-lookup"><span data-stu-id="1b839-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1b839-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b839-122">See also</span></span>

- [<span data-ttu-id="1b839-123">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1b839-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1b839-124">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1b839-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="1b839-125">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1b839-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="1b839-126">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1b839-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="1b839-127">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1b839-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="1b839-128">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="1b839-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1b839-129">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1b839-129">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="1b839-130">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="1b839-130">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="1b839-131">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="1b839-131">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="1b839-132">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b839-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
