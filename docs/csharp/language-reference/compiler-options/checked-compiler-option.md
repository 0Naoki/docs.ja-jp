---
title: -checked (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: cf6fa0e87654d0f9d61f34ea9b29ad80921a5720
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2018
ms.locfileid: "43401707"
---
# <a name="-checked-c-compiler-options"></a><span data-ttu-id="06bc5-102">-checked (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="06bc5-102">-checked (C# Compiler Options)</span></span>
<span data-ttu-id="06bc5-103">**-checked** オプションは、データ型の範囲外の値になる整数の算術ステートメントと、[checked](../../../csharp/language-reference/keywords/checked.md) または [unchecked](../../../csharp/language-reference/keywords/unchecked.md) キーワードのスコープ内に含まれない整数の算術ステートメントで、ランタイム例外が発生するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="06bc5-103">The **-checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../../../csharp/language-reference/keywords/checked.md) or [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06bc5-104">構文</span><span class="sxs-lookup"><span data-stu-id="06bc5-104">Syntax</span></span>  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="06bc5-105">コメント</span><span class="sxs-lookup"><span data-stu-id="06bc5-105">Remarks</span></span>  
 <span data-ttu-id="06bc5-106">`checked` または `unchecked` キーワードのスコープ内に含まれる整数の算術ステートメントは、**-checked** オプションの作用の対象になりません。</span><span class="sxs-lookup"><span data-stu-id="06bc5-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **-checked** option.</span></span>  
  
 <span data-ttu-id="06bc5-107">`checked` または `unchecked` キーワードのスコープ内に含まれない整数の算術ステートメントがデータ型の範囲外の値になり、**-checked+** (または **-checked**) がコンパイル時に使用されている場合は、そのステートメントでランタイム例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="06bc5-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **-checked+** (or **-checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="06bc5-108">**-checked-** がコンパイル時に使用された場合、そのステートメントでランタイム例外は発生しません。</span><span class="sxs-lookup"><span data-stu-id="06bc5-108">If **-checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="06bc5-109">このオプションの既定値は **-checked-** です。オーバーフロー チェックは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="06bc5-109">The default value for this option is **-checked-**; overflow checking is disabled.</span></span>
 
 <span data-ttu-id="06bc5-110">場合によっては、大規模アプリケーションの構築に使用される自動化ツールによって -checked が + に設定されます。</span><span class="sxs-lookup"><span data-stu-id="06bc5-110">Sometimes, automated tools that are used to build large applications set -checked to +.</span></span> <span data-ttu-id="06bc5-111">-checked- を使用する場合のシナリオの 1 つは、-checked- を指定してツールのグローバルな既定値をオーバーライドすることです。</span><span class="sxs-lookup"><span data-stu-id="06bc5-111">One scenario for using -checked- is to override the tool's global default by specifying -checked-.</span></span>
 
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="06bc5-112">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="06bc5-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="06bc5-113">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="06bc5-113">Open the project's **Properties** page.</span></span> <span data-ttu-id="06bc5-114">詳細については、「[Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)」([ビルド] ページ (プロジェクト デザイナー) (C#)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06bc5-114">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="06bc5-115">**[ビルド]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="06bc5-115">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="06bc5-116">**[詳細設定]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="06bc5-116">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="06bc5-117">**[演算のオーバーフローおよびアンダーフローのチェック]** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="06bc5-117">Modify the **Check for arithmetic overflow/underflow** property.</span></span>  
  
 <span data-ttu-id="06bc5-118">プログラムによってこのコンパイラ オプションにアクセスする方法については、<xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A> に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="06bc5-118">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06bc5-119">例</span><span class="sxs-lookup"><span data-stu-id="06bc5-119">Example</span></span>  
 <span data-ttu-id="06bc5-120">次のコマンドは `t2.cs` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="06bc5-120">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="06bc5-121">コマンドで使用されている `-checked` は、ファイル内の整数の算術ステートメントのうち、`checked` または `unchecked` キーワードのスコープ内に含まれず、データ型の範囲外の値になるステートメントで、ランタイム例外が発生することを指定します。</span><span class="sxs-lookup"><span data-stu-id="06bc5-121">The use of `-checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="06bc5-122">参照</span><span class="sxs-lookup"><span data-stu-id="06bc5-122">See Also</span></span>  

- [<span data-ttu-id="06bc5-123">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="06bc5-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="06bc5-124">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="06bc5-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
