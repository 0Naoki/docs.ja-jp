---
title: パラメーターと引数の違い (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: a69b956c7cffcc2a26916d6fc92f23dd4e2322d7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838977"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="4b376-102">パラメーターと引数の違い (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b376-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="4b376-103">ほとんどの場合、プロシージャが呼び出されたときの状況に関する情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="4b376-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="4b376-104">繰り返される、または共有のタスクを実行する手順では、呼び出しごとに異なる情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b376-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="4b376-105">この情報は、変数、定数、および呼び出しでは、プロシージャに渡す式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="4b376-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="4b376-106">プロシージャには、この情報を通信するために、プロシージャの定義、*パラメーター*、呼び出し元のコードを渡します、*引数*パラメーターにします。</span><span class="sxs-lookup"><span data-stu-id="4b376-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="4b376-107">駐車場としてパラメーターと引数は、自動車を考えることができます。</span><span class="sxs-lookup"><span data-stu-id="4b376-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="4b376-108">さまざまな自動車は、異なる時刻で駐車場で駐車できると同様、呼び出し元のコードは、it は、プロシージャを呼び出すたびに、同じパラメーターを別の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4b376-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="4b376-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b376-109">Parameters</span></span>  
 <span data-ttu-id="4b376-110">A*パラメーター*プロシージャには、それを呼び出すときに渡すことが期待される値を表します。</span><span class="sxs-lookup"><span data-stu-id="4b376-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="4b376-111">プロシージャの宣言では、そのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="4b376-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="4b376-112">定義するとき、`Function`または`Sub`プロシージャを指定する、*パラメーター リスト*プロシージャ名の直後に続くかっこ内に示します。</span><span class="sxs-lookup"><span data-stu-id="4b376-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="4b376-113">各パラメーターの名前、データ型、および引き渡し方法を指定 ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)または[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md))。</span><span class="sxs-lookup"><span data-stu-id="4b376-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="4b376-114">パラメーターが省略可能であるかも指定できます。</span><span class="sxs-lookup"><span data-stu-id="4b376-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="4b376-115">これは、その値を渡す呼び出し元のコードがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4b376-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="4b376-116">各パラメーターの名前として、*ローカル変数*の手順でします。</span><span class="sxs-lookup"><span data-stu-id="4b376-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="4b376-117">パラメーター名は、他の変数を使用すると同じ方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="4b376-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="4b376-118">引数</span><span class="sxs-lookup"><span data-stu-id="4b376-118">Arguments</span></span>  
 <span data-ttu-id="4b376-119">*引数*プロシージャを呼び出す場合、プロシージャのパラメーターに渡す値を表します。</span><span class="sxs-lookup"><span data-stu-id="4b376-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="4b376-120">プロシージャを呼び出すときに、呼び出し元のコードは、引数を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b376-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="4b376-121">呼び出すと、`Function`または`Sub`プロシージャを含める、*引数リスト*プロシージャ名の直後に続くかっこで囲まれました。</span><span class="sxs-lookup"><span data-stu-id="4b376-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="4b376-122">各引数は、パラメーター リスト内の同じ位置に対応します。</span><span class="sxs-lookup"><span data-stu-id="4b376-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="4b376-123">パラメーターの定義とは対照的引数には名前がありません。</span><span class="sxs-lookup"><span data-stu-id="4b376-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="4b376-124">各引数は、0 以上の変数、定数、およびリテラルに含めることができる式です。</span><span class="sxs-lookup"><span data-stu-id="4b376-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="4b376-125">通常、対応するパラメーター、定義されているデータ型に一致する必要があります式の評価結果のデータ型と、いずれの場合も、パラメーターの型に変換できるあります。</span><span class="sxs-lookup"><span data-stu-id="4b376-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b376-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b376-126">See also</span></span>

- [<span data-ttu-id="4b376-127">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4b376-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4b376-128">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4b376-128">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="4b376-129">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4b376-129">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="4b376-130">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4b376-130">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="4b376-131">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4b376-131">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="4b376-132">方法: プロシージャのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="4b376-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="4b376-133">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="4b376-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="4b376-134">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="4b376-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="4b376-135">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4b376-135">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="4b376-136">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="4b376-136">Procedure Overloading</span></span>](./procedure-overloading.md)
