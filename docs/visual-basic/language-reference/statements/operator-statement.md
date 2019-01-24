---
title: Operator ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: 9da2fc05824fa7e412c1c4802852fd00ba2709e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658196"
---
# <a name="operator-statement"></a><span data-ttu-id="6bbc2-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="6bbc2-102">Operator Statement</span></span>
<span data-ttu-id="6bbc2-103">演算子記号、オペランド、およびクラスまたは構造体に演算子プロシージャを定義するコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bbc2-104">構文</span><span class="sxs-lookup"><span data-stu-id="6bbc2-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="6bbc2-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="6bbc2-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="6bbc2-106">任意。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-106">Optional.</span></span> <span data-ttu-id="6bbc2-107">参照してください[属性一覧](../../../visual-basic/language-reference/statements/attribute-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="6bbc2-108">必須。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-108">Required.</span></span> <span data-ttu-id="6bbc2-109">この演算子プロシージャがあることを示します[パブリック](../../../visual-basic/language-reference/modifiers/public.md)アクセスします。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="6bbc2-110">任意。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-110">Optional.</span></span> <span data-ttu-id="6bbc2-111">参照してください[オーバー ロード](../../../visual-basic/language-reference/modifiers/overloads.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="6bbc2-112">必須。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-112">Required.</span></span> <span data-ttu-id="6bbc2-113">この演算子プロシージャがあることを示します、 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="6bbc2-114">任意。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-114">Optional.</span></span> <span data-ttu-id="6bbc2-115">参照してください[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="6bbc2-116">指定しない限り、変換演算子に必要な`Narrowing`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="6bbc2-117">この演算子プロシージャを定義することを示します、 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)変換します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="6bbc2-118">このヘルプ ページでは、「拡大と縮小変換」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="6bbc2-119">指定しない限り、変換演算子に必要な`Widening`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="6bbc2-120">この演算子プロシージャを定義することを示します、 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)変換します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="6bbc2-121">このヘルプ ページでは、「拡大と縮小変換」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="6bbc2-122">必須。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-122">Required.</span></span> <span data-ttu-id="6bbc2-123">シンボルまたはこの演算子プロシージャを定義する演算子の識別子。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="6bbc2-124">必須。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-124">Required.</span></span> <span data-ttu-id="6bbc2-125">名前と 1 つのオペランド (変換演算子を含む)、単項演算子または二項演算子の左側のオペランドの型。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="6bbc2-126">2 項演算子が必要です。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-126">Required for binary operators.</span></span> <span data-ttu-id="6bbc2-127">名前と二項演算子の右辺オペランドの型。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="6bbc2-128">`operand1` `operand2`次の構文と部分があります。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="6bbc2-129">パーツ</span><span class="sxs-lookup"><span data-stu-id="6bbc2-129">Part</span></span>|<span data-ttu-id="6bbc2-130">説明</span><span class="sxs-lookup"><span data-stu-id="6bbc2-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="6bbc2-131">省略可能、ただし引き渡し方法があります[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="6bbc2-132">必須。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-132">Required.</span></span> <span data-ttu-id="6bbc2-133">このオペランドを表す変数の名前。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="6bbc2-134">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="6bbc2-135">省略可能な場合を除き、`Option Strict`は`On`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="6bbc2-136">このオペランドのデータ型。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="6bbc2-137">省略可能な場合を除き、`Option Strict`は`On`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="6bbc2-138">演算子プロシージャは、値のデータ型を返します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="6bbc2-139">任意。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-139">Optional.</span></span> <span data-ttu-id="6bbc2-140">演算子プロシージャを実行するステートメントのブロックです。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="6bbc2-141">必須。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-141">Required.</span></span> <span data-ttu-id="6bbc2-142">演算子プロシージャが呼び出し元のコードに返す値。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="6bbc2-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="6bbc2-143">`End` `Operator`</span></span>  
 <span data-ttu-id="6bbc2-144">必須。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-144">Required.</span></span> <span data-ttu-id="6bbc2-145">この演算子プロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bbc2-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="6bbc2-146">Remarks</span></span>  
 <span data-ttu-id="6bbc2-147">使用することができます`Operator`クラスまたは構造体でのみです。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="6bbc2-148">つまり、*宣言コンテキスト*の演算子はソース ファイル、名前空間、モジュール、インターフェイス、プロシージャ、またはブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="6bbc2-149">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="6bbc2-150">すべての演算子である必要があります`Public Shared`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="6bbc2-151">指定することはできません`ByRef`、 `Optional`、または`ParamArray`のいずれかのオペランド。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="6bbc2-152">演算子記号や識別子を使用して、戻り値を保持することはできません。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="6bbc2-153">使用する必要があります、`Return`ステートメント、およびその値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="6bbc2-154">任意の数の`Return`の手順でステートメントは任意の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="6bbc2-155">この方法で、演算子を定義すると呼びます*演算子のオーバー ロード*を使用するかどうかを`Overloads`キーワード。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="6bbc2-156">定義可能な演算子を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="6bbc2-157">型</span><span class="sxs-lookup"><span data-stu-id="6bbc2-157">Type</span></span>|<span data-ttu-id="6bbc2-158">演算子</span><span class="sxs-lookup"><span data-stu-id="6bbc2-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="6bbc2-159">単項</span><span class="sxs-lookup"><span data-stu-id="6bbc2-159">Unary</span></span>|<span data-ttu-id="6bbc2-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="6bbc2-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="6bbc2-161">2 項</span><span class="sxs-lookup"><span data-stu-id="6bbc2-161">Binary</span></span>|<span data-ttu-id="6bbc2-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="6bbc2-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="6bbc2-163">変換 (単項)</span><span class="sxs-lookup"><span data-stu-id="6bbc2-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="6bbc2-164">なお、`=`バイナリの一覧で演算子は、比較演算子、代入演算子ではありません。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="6bbc2-165">定義するときに`CType`、いずれかを指定する必要があります`Widening`または`Narrowing`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="6bbc2-166">一致するペア</span><span class="sxs-lookup"><span data-stu-id="6bbc2-166">Matched Pairs</span></span>  
 <span data-ttu-id="6bbc2-167">一致するペアとして、特定の演算子を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="6bbc2-168">このようなペアのいずれかの演算子を定義する場合に、他にもを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="6bbc2-169">一致するペア以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="6bbc2-170">`=` および `<>`</span><span class="sxs-lookup"><span data-stu-id="6bbc2-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="6bbc2-171">`>` および `<`</span><span class="sxs-lookup"><span data-stu-id="6bbc2-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="6bbc2-172">`>=` および `<=`</span><span class="sxs-lookup"><span data-stu-id="6bbc2-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="6bbc2-173">`IsTrue` および `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="6bbc2-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="6bbc2-174">データの種類の制限</span><span class="sxs-lookup"><span data-stu-id="6bbc2-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="6bbc2-175">定義するすべてのオペレーターを定義するクラスまたは構造体が含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="6bbc2-176">つまり、クラスまたは構造体は、次のデータ型として表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="6bbc2-177">単項演算子のオペランド。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="6bbc2-178">少なくとも 1 つの二項演算子のオペランド。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="6bbc2-179">オペランドまたは変換演算子の戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="6bbc2-180">特定の演算子がある追加のデータ型の制限を次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="6bbc2-181">定義する場合、`IsTrue`と`IsFalse`演算子を返す必要がある両方の`Boolean`型。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="6bbc2-182">定義する場合、`<<`と`>>`演算子、それら両方を指定してください、`Integer`の入力、`operandtype`の`operand2`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="6bbc2-183">戻り値の型をいずれかのオペランドの型に対応する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="6bbc2-184">などの比較演算子など`=`または`<>`返せる`Boolean`場合でも、どちらのオペランドが`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="6bbc2-185">論理/ビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="6bbc2-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="6bbc2-186">`And`、 `Or`、 `Not`、および`Xor`演算子は、Visual Basic で論理またはビットごとのいずれかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="6bbc2-187">ただし、クラスまたは構造体でこれらの演算子のいずれかを定義する場合は、そのビットごとの演算のみを定義できます。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="6bbc2-188">定義することはできません、`AndAlso`演算子と直接、`Operator`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="6bbc2-189">ただし、使用することができます`AndAlso`次の条件を満たしている場合。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="6bbc2-190">定義した`And`に使用する同じオペランドの型で`AndAlso`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="6bbc2-191">定義`And`を定義したクラスまたは構造体と同じ型を返します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="6bbc2-192">定義した、`IsFalse`演算子を定義したクラスまたは構造体に対して`And`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="6bbc2-193">同様に、使用`OrElse`定義している場合`Or`同じのオペランドに対して、クラスや構造体の戻り値の型が定義されている`IsTrue`クラスまたは構造体にします。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="6bbc2-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="6bbc2-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="6bbc2-195">A*拡大変換*、実行時に常に成功したときに、*縮小変換*実行時に失敗することができます。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="6bbc2-196">詳細については、「 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="6bbc2-197">変換のプロシージャを宣言する場合`Widening`プロシージャのコードはエラーを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="6bbc2-198">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-198">This means the following:</span></span>  
  
-   <span data-ttu-id="6bbc2-199">型の有効な値を返す必要が常に`type`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="6bbc2-200">すべての例外とその他のエラー条件に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="6bbc2-201">これは、呼び出したプロシージャから返されたエラーを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="6bbc2-202">変換の手順が成功しない可能性があります、ある可能性がある、またはその it ハンドルされない例外が発生する可能性がありますを宣言する必要があります`Narrowing`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bbc2-203">例</span><span class="sxs-lookup"><span data-stu-id="6bbc2-203">Example</span></span>  
 <span data-ttu-id="6bbc2-204">次のコード例では、`Operator`演算子する手順について説明する構造体のアウトラインを定義するステートメント、 `And`、 `Or`、 `IsFalse`、および`IsTrue`演算子。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="6bbc2-205">`And` `Or`型の 2 つのオペランドを受け取る各`abc`型を返すと`abc`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="6bbc2-206">`IsFalse` `IsTrue`それぞれ型の 1 つのオペランドを受け取ります`abc`戻って`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="6bbc2-207">これらの定義を使用して、呼び出し元のコードを許可する`And`、 `AndAlso`、 `Or`、および`OrElse`型のオペランドで`abc`します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6bbc2-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bbc2-208">See also</span></span>
- [<span data-ttu-id="6bbc2-209">IsFalse 演算子</span><span class="sxs-lookup"><span data-stu-id="6bbc2-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="6bbc2-210">IsTrue 演算子</span><span class="sxs-lookup"><span data-stu-id="6bbc2-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="6bbc2-211">Widening</span><span class="sxs-lookup"><span data-stu-id="6bbc2-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="6bbc2-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="6bbc2-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="6bbc2-213">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="6bbc2-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="6bbc2-214">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="6bbc2-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="6bbc2-215">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="6bbc2-216">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="6bbc2-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="6bbc2-217">方法: 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="6bbc2-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="6bbc2-218">方法: 演算子を定義するクラスを使用して、</span><span class="sxs-lookup"><span data-stu-id="6bbc2-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
