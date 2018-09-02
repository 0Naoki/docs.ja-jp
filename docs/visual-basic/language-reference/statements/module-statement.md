---
title: Module ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 5628224a08fe5f12cf2a81b179c4998001174354
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387648"
---
# <a name="module-statement"></a><span data-ttu-id="a22b4-102">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="a22b4-102">Module Statement</span></span>
<span data-ttu-id="a22b4-103">モジュールの名前を宣言し、変数、プロパティ、イベント、およびモジュールを構成するプロシージャの定義を紹介します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a22b4-104">構文</span><span class="sxs-lookup"><span data-stu-id="a22b4-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="a22b4-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="a22b4-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="a22b4-106">任意。</span><span class="sxs-lookup"><span data-stu-id="a22b4-106">Optional.</span></span> <span data-ttu-id="a22b4-107">参照してください[属性一覧](../../../visual-basic/language-reference/statements/attribute-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="a22b4-108">任意。</span><span class="sxs-lookup"><span data-stu-id="a22b4-108">Optional.</span></span> <span data-ttu-id="a22b4-109">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="a22b4-110">Public</span><span class="sxs-lookup"><span data-stu-id="a22b4-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="a22b4-111">Friend</span><span class="sxs-lookup"><span data-stu-id="a22b4-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="a22b4-112">参照してください[アクセス レベルを Visual Basic で](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="a22b4-113">必須。</span><span class="sxs-lookup"><span data-stu-id="a22b4-113">Required.</span></span> <span data-ttu-id="a22b4-114">このモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="a22b4-114">Name of this module.</span></span> <span data-ttu-id="a22b4-115">参照してください[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="a22b4-116">任意。</span><span class="sxs-lookup"><span data-stu-id="a22b4-116">Optional.</span></span> <span data-ttu-id="a22b4-117">変数、プロパティ、イベント、プロシージャ、およびこのモジュールの入れ子にされた型を定義するステートメントです。</span><span class="sxs-lookup"><span data-stu-id="a22b4-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="a22b4-118">`Module` の定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a22b4-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="a22b4-119">Remarks</span></span>  
 <span data-ttu-id="a22b4-120">A`Module`ステートメントは、その名前空間全体で使用できる参照型を定義します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="a22b4-121">A*モジュール*(とも呼ばれる、*標準モジュール*) のようなクラスがいくつか重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="a22b4-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="a22b4-122">すべてのモジュールは、1 つのインスタンスを備え、作成または変数に代入する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a22b4-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="a22b4-123">モジュールは継承をサポートしていないまたはインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="a22b4-124">モジュールが通知を*型*クラスまたは構造体は、という意味で-モジュールのデータ型を持つプログラミング要素を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="a22b4-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="a22b4-125">使用することができます`Module`名前空間レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="a22b4-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="a22b4-126">つまり、*宣言コンテキスト*モジュールのソース ファイルまたは名前空間にある必要があります、クラス、構造体、モジュール、インターフェイス、プロシージャ、またはブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a22b4-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="a22b4-127">文字列または任意の種類別のモジュール内のモジュールを入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a22b4-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="a22b4-128">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a22b4-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="a22b4-129">モジュールが、有効期間は、プログラムと同じです。</span><span class="sxs-lookup"><span data-stu-id="a22b4-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="a22b4-130">そのメンバーはすべてため`Shared`のプログラムの有効期間もあります。</span><span class="sxs-lookup"><span data-stu-id="a22b4-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="a22b4-131">既定で、モジュール[フレンド](../../../visual-basic/language-reference/modifiers/friend.md)アクセスします。</span><span class="sxs-lookup"><span data-stu-id="a22b4-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="a22b4-132">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="a22b4-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="a22b4-133">詳細については、次を参照してください。[アクセス レベルを Visual Basic で](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="a22b4-134">モジュールのすべてのメンバーは、暗黙的に`Shared`します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="a22b4-135">クラスとモジュール</span><span class="sxs-lookup"><span data-stu-id="a22b4-135">Classes and Modules</span></span>  
 <span data-ttu-id="a22b4-136">これらの要素がある多くの類似点がいくつかの重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="a22b4-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="a22b4-137">**用語集。**</span><span class="sxs-lookup"><span data-stu-id="a22b4-137">**Terminology.**</span></span> <span data-ttu-id="a22b4-138">Visual Basic の以前のバージョンは 2 種類のモジュールを認識:*クラス モジュール*(.cls ファイル) と*標準モジュール*(.bas ファイル)。</span><span class="sxs-lookup"><span data-stu-id="a22b4-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="a22b4-139">現在のバージョンを呼び出す*クラス*と*モジュール*、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="a22b4-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="a22b4-140">**共有メンバー。**</span><span class="sxs-lookup"><span data-stu-id="a22b4-140">**Shared Members.**</span></span> <span data-ttu-id="a22b4-141">クラスのメンバーは、共有するかどうか、またはインスタンス メンバーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a22b4-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="a22b4-142">**オブジェクト指向です。**</span><span class="sxs-lookup"><span data-stu-id="a22b4-142">**Object Orientation.**</span></span> <span data-ttu-id="a22b4-143">クラスは、オブジェクト指向ですが、モジュールがないです。</span><span class="sxs-lookup"><span data-stu-id="a22b4-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="a22b4-144">したがって、クラスだけは、オブジェクトとしてインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="a22b4-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="a22b4-145">詳細については、次を参照してください。[オブジェクトとクラス](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a22b4-146">ルール</span><span class="sxs-lookup"><span data-stu-id="a22b4-146">Rules</span></span>  
  
-   <span data-ttu-id="a22b4-147">**修飾子。**</span><span class="sxs-lookup"><span data-stu-id="a22b4-147">**Modifiers.**</span></span> <span data-ttu-id="a22b4-148">すべてのモジュールのメンバーは、暗黙的に[Shared](../../../visual-basic/language-reference/modifiers/shared.md)します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="a22b4-149">使用することはできません、`Shared`キーワードと、任意のメンバーの共有状態を変更して、メンバーを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="a22b4-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="a22b4-150">**継承。**</span><span class="sxs-lookup"><span data-stu-id="a22b4-150">**Inheritance.**</span></span> <span data-ttu-id="a22b4-151">モジュールが以外の任意の型から継承できません<xref:System.Object>、どのすべてのモジュールから継承します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="a22b4-152">具体的には、1 つのモジュールは、別の継承できません。</span><span class="sxs-lookup"><span data-stu-id="a22b4-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="a22b4-153">使用することはできません、 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)モジュールの定義を指定するも<xref:System.Object>します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="a22b4-154">**既定のプロパティ。**</span><span class="sxs-lookup"><span data-stu-id="a22b4-154">**Default Property.**</span></span> <span data-ttu-id="a22b4-155">モジュールには、既定のプロパティを定義できません。</span><span class="sxs-lookup"><span data-stu-id="a22b4-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="a22b4-156">詳細については、次を参照してください。[既定](../../../visual-basic/language-reference/modifiers/default.md)します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a22b4-157">動作</span><span class="sxs-lookup"><span data-stu-id="a22b4-157">Behavior</span></span>  
  
-   <span data-ttu-id="a22b4-158">**アクセス レベルです。**</span><span class="sxs-lookup"><span data-stu-id="a22b4-158">**Access Level.**</span></span> <span data-ttu-id="a22b4-159">モジュール内には、アクセス レベルでは、各メンバーを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a22b4-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="a22b4-160">モジュール メンバー[パブリック](../../../visual-basic/language-reference/modifiers/public.md)変数および定数を除く、既定のアクセス[プライベート](../../../visual-basic/language-reference/modifiers/private.md)アクセスします。</span><span class="sxs-lookup"><span data-stu-id="a22b4-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="a22b4-161">モジュールがそのメンバーの 1 つ以上のアクセスが制限されてよりときに、指定されたモジュールへのアクセス レベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a22b4-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="a22b4-162">**スコープ。**</span><span class="sxs-lookup"><span data-stu-id="a22b4-162">**Scope.**</span></span> <span data-ttu-id="a22b4-163">モジュールとは、名前空間全体のスコープ内で。</span><span class="sxs-lookup"><span data-stu-id="a22b4-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="a22b4-164">すべてのモジュール メンバーのスコープは、モジュール全体です。</span><span class="sxs-lookup"><span data-stu-id="a22b4-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="a22b4-165">すべてのメンバーに注意してください*の上位変換*、これにより、モジュールを含む名前空間に昇格するには、そのスコープ。</span><span class="sxs-lookup"><span data-stu-id="a22b4-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="a22b4-166">詳細については、次を参照してください。[型の上位変換](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="a22b4-167">**パス名です。**</span><span class="sxs-lookup"><span data-stu-id="a22b4-167">**Qualification.**</span></span> <span data-ttu-id="a22b4-168">プロジェクトでは、複数のモジュールがあることができ、2 つまたは複数のモジュールで同じ名前を持つメンバーを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="a22b4-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="a22b4-169">ただし、モジュールの外部から参照がある場合は、このような適切なモジュール名を持つメンバーへの参照を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a22b4-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="a22b4-170">詳細については、次を参照してください。 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)します。</span><span class="sxs-lookup"><span data-stu-id="a22b4-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a22b4-171">例</span><span class="sxs-lookup"><span data-stu-id="a22b4-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a22b4-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="a22b4-172">See Also</span></span>  
 [<span data-ttu-id="a22b4-173">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="a22b4-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="a22b4-174">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="a22b4-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="a22b4-175">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="a22b4-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="a22b4-176">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="a22b4-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="a22b4-177">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="a22b4-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="a22b4-178">型の上位変換</span><span class="sxs-lookup"><span data-stu-id="a22b4-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
