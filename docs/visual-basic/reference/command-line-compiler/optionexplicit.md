---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 220d6e06ef692655bd6db000fa98b4eb2fc69ba9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683847"
---
# <a name="-optionexplicit"></a><span data-ttu-id="bd760-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="bd760-102">-optionexplicit</span></span>
<span data-ttu-id="bd760-103">使用されるように、変数が宣言されていない場合は、コンパイラ エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="bd760-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd760-104">構文</span><span class="sxs-lookup"><span data-stu-id="bd760-104">Syntax</span></span>  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="bd760-105">引数</span><span class="sxs-lookup"><span data-stu-id="bd760-105">Arguments</span></span>  
 <span data-ttu-id="bd760-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="bd760-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="bd760-107">任意。</span><span class="sxs-lookup"><span data-stu-id="bd760-107">Optional.</span></span> <span data-ttu-id="bd760-108">指定`-optionexplicit+`変数の明示的な宣言を要求します。</span><span class="sxs-lookup"><span data-stu-id="bd760-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="bd760-109">`-optionexplicit+`オプションと同じですが、既定`-optionexplicit`します。</span><span class="sxs-lookup"><span data-stu-id="bd760-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="bd760-110">`-optionexplicit-`オプションは、変数の暗黙的な宣言を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd760-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd760-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="bd760-111">Remarks</span></span>  
 <span data-ttu-id="bd760-112">ソース コード ファイルが含まれている場合、 [Option Explicit ステートメント](../../../visual-basic/language-reference/statements/option-explicit-statement.md)、ステートメントよりも優先、`-optionexplicit`コマンド ライン コンパイラを設定します。</span><span class="sxs-lookup"><span data-stu-id="bd760-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="bd760-113">Visual Studio IDE で-optionexplicit を設定するには</span><span class="sxs-lookup"><span data-stu-id="bd760-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="bd760-114">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd760-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bd760-115">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd760-115">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="bd760-116">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd760-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="bd760-117">値を変更、 **Option Explicit**ボックス。</span><span class="sxs-lookup"><span data-stu-id="bd760-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd760-118">例</span><span class="sxs-lookup"><span data-stu-id="bd760-118">Example</span></span>  
 <span data-ttu-id="bd760-119">ときに、次のコードがコンパイル`-optionexplicit-`使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd760-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bd760-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd760-120">See also</span></span>
- [<span data-ttu-id="bd760-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="bd760-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bd760-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="bd760-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="bd760-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="bd760-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="bd760-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="bd760-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="bd760-125">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="bd760-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="bd760-126">Option Explicit ステートメント</span><span class="sxs-lookup"><span data-stu-id="bd760-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- <span data-ttu-id="bd760-127">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="bd760-127">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
