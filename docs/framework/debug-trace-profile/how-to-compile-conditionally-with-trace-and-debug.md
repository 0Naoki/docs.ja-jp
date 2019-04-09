---
title: '方法: トレースとデバッグを指定して条件付きコンパイルを実行する'
ms.date: 03/30/2017
helpviewer_keywords:
- trace compiler options
- trace statements
- compiling source code, trace statements
- tracing [.NET Framework], enabling or disabling
- tracing [.NET Framework], compiling conditionally
- TRACE directive
- conditional compilation, tracing code
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76e442536e4c863031072adfb4d8716ca7a19aff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158659"
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a><span data-ttu-id="12870-102">方法: トレースとデバッグを指定して条件付きコンパイルを実行する</span><span class="sxs-lookup"><span data-stu-id="12870-102">How to: Compile Conditionally with Trace and Debug</span></span>
<span data-ttu-id="12870-103">開発時にアプリケーションをデバッグするときは、トレース出力とデバッグ出力の両方が Visual Studio の [出力] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="12870-103">While you are debugging an application during development, both your tracing and debugging output go to the Output window in Visual Studio.</span></span> <span data-ttu-id="12870-104">ただし、配置されるアプリケーションにトレース機能を組み込むには、**TRACE** コンパイラ ディレクティブを有効にして、インストルメント化されたアプリケーションをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12870-104">However, to include tracing features in a deployed application, you must compile your instrumented applications with the **TRACE** compiler directive enabled.</span></span> <span data-ttu-id="12870-105">これにより、コンパイルされたアプリケーションのリリース バージョンに、トレース コードが組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="12870-105">This allows tracing code to be compiled into the release version of your application.</span></span> <span data-ttu-id="12870-106">**TRACE** ディレクティブを有効にしないと、コンパイル時にすべてのトレース コードが無視され、配置する実行可能コードに含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="12870-106">If you do not enable the **TRACE** directive, all tracing code is ignored during compilation and is not included in the executable code that you will deploy.</span></span>  
  
 <span data-ttu-id="12870-107">トレース用のメソッドとデバッグ用のメソッドにはどちらも、関連付けられた条件属性があります。</span><span class="sxs-lookup"><span data-stu-id="12870-107">Both the tracing and debugging methods have associated conditional attributes.</span></span> <span data-ttu-id="12870-108">たとえば、トレースの条件属性が **true** の場合は、すべてのトレース ステートメントがアセンブリ (コンパイル済みの .exe ファイルや .dll ファイル) 内に組み込まれます。また、**Trace** 条件属性が **false** の場合、トレース ステートメントは組み込まれません。</span><span class="sxs-lookup"><span data-stu-id="12870-108">For example, if the conditional attribute for tracing is **true**, all trace statements are included within an assembly (a compiled .exe file or .dll); if the **Trace** conditional attribute is **false**, the trace statements are not included.</span></span>  
  
 <span data-ttu-id="12870-109">ビルドでは、**Trace** 条件属性または **Debug** 条件属性をオンにすることも、両方をオンにすることも、あるいは両方をオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="12870-109">You can have either the **Trace** or **Debug** conditional attribute turned on for a build, or both, or neither.</span></span> <span data-ttu-id="12870-110">そのため、これにはビルドの 4 つの種類があります。**デバッグ**、**トレース**、両方、またはどちらもします。</span><span class="sxs-lookup"><span data-stu-id="12870-110">Thus, there are four types of build: **Debug**, **Trace**, both, or neither.</span></span> <span data-ttu-id="12870-111">実際の配置用のリリース ビルドでは両方ともオフにする場合もありますが、大半のデバッグ ビルドでは両方ともオンにします。</span><span class="sxs-lookup"><span data-stu-id="12870-111">Some release builds for production deployment might contain neither; most debugging builds contain both.</span></span>  
  
 <span data-ttu-id="12870-112">アプリケーションのコンパイラ設定は、次に示すいくつかの方法で指定できます。</span><span class="sxs-lookup"><span data-stu-id="12870-112">You can specify the compiler settings for your application in several ways:</span></span>  
  
-   <span data-ttu-id="12870-113">プロパティ ページ</span><span class="sxs-lookup"><span data-stu-id="12870-113">The property pages</span></span>  
  
-   <span data-ttu-id="12870-114">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="12870-114">The command line</span></span>  
  
-   <span data-ttu-id="12870-115">**#CONST** (Visual Basic の場合) および **#define** (C# の場合)</span><span class="sxs-lookup"><span data-stu-id="12870-115">**#CONST** (for Visual Basic) and **#define** (for C#)</span></span>  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a><span data-ttu-id="12870-116">プロパティ ページのダイアログ ボックスでコンパイル設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="12870-116">To change compile settings from the property pages dialog box</span></span>  
  
1.  <span data-ttu-id="12870-117">**ソリューション エクスプローラー**で、プロジェクト ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="12870-117">Right-click the project node in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="12870-118">ショートカット メニューの **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="12870-118">Choose **Properties** from the shortcut menu.</span></span>  
  
    -   <span data-ttu-id="12870-119">Visual Basic では、プロパティ ページの左ペインで **[コンパイル]** タブをクリックし、**[詳細コンパイル オプション]** ボタンをクリックして **[コンパイラの詳細設定]** ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="12870-119">In Visual Basic, click the **Compile** tab in the left pane of the property page, then click the **Advanced Compile Options** button to display the **Advanced Compiler Settings** dialog box.</span></span> <span data-ttu-id="12870-120">有効にするコンパイラ設定のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="12870-120">Select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="12870-121">無効にする設定のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="12870-121">Clear the check boxes for settings you want to disable.</span></span>  
  
    -   <span data-ttu-id="12870-122">C# では、プロパティ ページの左ペインで **[ビルド]** タブをクリックし、有効にするコンパイラ設定のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="12870-122">In C#, click the **Build** tab in the left pane of the property page, then select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="12870-123">無効にする設定のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="12870-123">Clear the check boxes for settings you want to disable.</span></span>  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a><span data-ttu-id="12870-124">インストルメント化されたコードをコマンド ラインを使用してコンパイルするには</span><span class="sxs-lookup"><span data-stu-id="12870-124">To compile instrumented code using the command line</span></span>  
  
1.  <span data-ttu-id="12870-125">コマンド ラインで、条件付きコンパイラ スイッチを設定します。</span><span class="sxs-lookup"><span data-stu-id="12870-125">Set a conditional compiler switch on the command line.</span></span> <span data-ttu-id="12870-126">コンパイラにより、トレース コードまたはデバッグ コードが実行可能ファイルに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="12870-126">The compiler will include trace or debug code in the executable.</span></span>  
  
     <span data-ttu-id="12870-127">たとえば、コマンド ラインで次のコンパイラ命令を入力すると、コンパイルされた実行可能ファイルにトレース コードが組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="12870-127">For example, the following compiler instruction entered on the command line would include your tracing code in a compiled executable:</span></span>  
  
     <span data-ttu-id="12870-128">Visual basic の場合: **vbc-r:System.dll-d: トレース = TRUE-d: デバッグ = FALSE MyApplication.vb**</span><span class="sxs-lookup"><span data-stu-id="12870-128">For Visual Basic: **vbc -r:System.dll -d:TRACE=TRUE -d:DEBUG=FALSE MyApplication.vb**</span></span>  
  
     <span data-ttu-id="12870-129">C#: **Csc-r:System.dll-d: トレース-d: デバッグ = FALSE MyApplication.cs**</span><span class="sxs-lookup"><span data-stu-id="12870-129">For C#: **csc -r:System.dll -d:TRACE -d:DEBUG=FALSE MyApplication.cs**</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="12870-130">複数のアプリケーション ファイルをコンパイルするには、各ファイル名の間にスペースを 1 つ挿入します。たとえば、「**MyApplication1.vb MyApplication2.vb MyApplication3.vb**」または「**MyApplication1.cs MyApplication2.cs MyApplication3.cs**」とします。</span><span class="sxs-lookup"><span data-stu-id="12870-130">To compile more than one application file, leave a blank space between the file names, for example, **MyApplication1.vb MyApplication2.vb MyApplication3.vb** or **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span></span>  
  
     <span data-ttu-id="12870-131">上記の例で使用した条件付きコンパイルのディレクティブの意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="12870-131">The meaning of the conditional-compilation directives used in the above examples is as follows:</span></span>  
  
    |<span data-ttu-id="12870-132">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="12870-132">Directive</span></span>|<span data-ttu-id="12870-133">説明</span><span class="sxs-lookup"><span data-stu-id="12870-133">Meaning</span></span>|  
    |---------------|-------------|  
    |`vbc`|<span data-ttu-id="12870-134">Visual Basic コンパイラ</span><span class="sxs-lookup"><span data-stu-id="12870-134">Visual Basic compiler</span></span>|  
    |`csc`|<span data-ttu-id="12870-135">C# コンパイラ</span><span class="sxs-lookup"><span data-stu-id="12870-135">C# compiler</span></span>|  
    |`-r:`|<span data-ttu-id="12870-136">外部アセンブリ (EXE または DLL) を参照します。</span><span class="sxs-lookup"><span data-stu-id="12870-136">References an external assembly (EXE or DLL)</span></span>|  
    |`-d:`|<span data-ttu-id="12870-137">条件付きコンパイル シンボルを定義します。</span><span class="sxs-lookup"><span data-stu-id="12870-137">Defines a conditional compilation symbol</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="12870-138">TRACE または DEBUG は大文字で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12870-138">You must spell TRACE or DEBUG with uppercase letters.</span></span> <span data-ttu-id="12870-139">条件付きコンパイル コマンドの詳細情報を参照するには、コマンド プロンプトに `vbc /?` (Visual Basic の場合) または `csc /?` (C# の場合) と入力します。</span><span class="sxs-lookup"><span data-stu-id="12870-139">For more information about the conditional compilation commands, enter `vbc /?` (for Visual Basic) or `csc /?` (for C#) at the command prompt.</span></span> <span data-ttu-id="12870-140">詳細については、「[コマンド ラインからのビルド](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)」(C# の場合) または「[コマンド ライン コンパイラの起動](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)」(Visual Basic の場合) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12870-140">For more information, see [Building from the Command Line](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (C#) or [Invoking the Command-Line Compiler](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).</span></span>  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a><span data-ttu-id="12870-141">#CONST または #define を使用して条件付きコンパイルを実行するには</span><span class="sxs-lookup"><span data-stu-id="12870-141">To perform conditional compilation using #CONST or #define</span></span>  
  
1.  <span data-ttu-id="12870-142">ソース コード ファイルの先頭に、使用するプログラミング言語に該当するステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="12870-142">Type the appropriate statement for your programming language at the top of the source code file.</span></span>  
  
    |<span data-ttu-id="12870-143">言語</span><span class="sxs-lookup"><span data-stu-id="12870-143">Language</span></span>|<span data-ttu-id="12870-144">ステートメント</span><span class="sxs-lookup"><span data-stu-id="12870-144">Statement</span></span>|<span data-ttu-id="12870-145">結果</span><span class="sxs-lookup"><span data-stu-id="12870-145">Result</span></span>|  
    |--------------|---------------|------------|  
    |**<span data-ttu-id="12870-146">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="12870-146">Visual Basic</span></span>**|**<span data-ttu-id="12870-147">#CONST TRACE = true</span><span class="sxs-lookup"><span data-stu-id="12870-147">#CONST TRACE = true</span></span>**|<span data-ttu-id="12870-148">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="12870-148">Enables tracing</span></span>|  
    ||**<span data-ttu-id="12870-149">#CONST TRACE = false</span><span class="sxs-lookup"><span data-stu-id="12870-149">#CONST TRACE = false</span></span>**|<span data-ttu-id="12870-150">トレースを無効にします。</span><span class="sxs-lookup"><span data-stu-id="12870-150">Disables tracing</span></span>|  
    ||**<span data-ttu-id="12870-151">#CONST DEBUG = true</span><span class="sxs-lookup"><span data-stu-id="12870-151">#CONST DEBUG = true</span></span>**|<span data-ttu-id="12870-152">デバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="12870-152">Enables debugging</span></span>|  
    ||**<span data-ttu-id="12870-153">#CONST DEBUG = false</span><span class="sxs-lookup"><span data-stu-id="12870-153">#CONST DEBUG = false</span></span>**|<span data-ttu-id="12870-154">デバッグを無効にします。</span><span class="sxs-lookup"><span data-stu-id="12870-154">Disables debugging</span></span>|  
    |**<span data-ttu-id="12870-155">C#</span><span class="sxs-lookup"><span data-stu-id="12870-155">C#</span></span>**|**<span data-ttu-id="12870-156">#define TRACE</span><span class="sxs-lookup"><span data-stu-id="12870-156">#define TRACE</span></span>**|<span data-ttu-id="12870-157">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="12870-157">Enables tracing</span></span>|  
    ||**<span data-ttu-id="12870-158">#undef TRACE</span><span class="sxs-lookup"><span data-stu-id="12870-158">#undef TRACE</span></span>**|<span data-ttu-id="12870-159">トレースを無効にします。</span><span class="sxs-lookup"><span data-stu-id="12870-159">Disables tracing</span></span>|  
    ||**<span data-ttu-id="12870-160">#define DEBUG</span><span class="sxs-lookup"><span data-stu-id="12870-160">#define DEBUG</span></span>**|<span data-ttu-id="12870-161">デバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="12870-161">Enables debugging</span></span>|  
    ||**<span data-ttu-id="12870-162">#undef DEBUG</span><span class="sxs-lookup"><span data-stu-id="12870-162">#undef DEBUG</span></span>**|<span data-ttu-id="12870-163">デバッグを無効にします。</span><span class="sxs-lookup"><span data-stu-id="12870-163">Disables debugging</span></span>|  
  
### <a name="to-disable-tracing-or-debugging"></a><span data-ttu-id="12870-164">トレースまたはデバッグを無効にするには</span><span class="sxs-lookup"><span data-stu-id="12870-164">To disable tracing or debugging</span></span>  
  
<span data-ttu-id="12870-165">ソース コードからコンパイラ ディレクティブを削除します。</span><span class="sxs-lookup"><span data-stu-id="12870-165">Delete the compiler directive from your source code.</span></span>  
  
<span data-ttu-id="12870-166">\- または -</span><span class="sxs-lookup"><span data-stu-id="12870-166">\- or -</span></span>  
  
<span data-ttu-id="12870-167">コンパイラ ディレクティブをコメント アウトします。</span><span class="sxs-lookup"><span data-stu-id="12870-167">Comment out the compiler directive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12870-168">コンパイルの準備ができたら、**[ビルド]** メニューの **[ビルド]** を選択できます。または、条件付きコンパイル シンボルを定義するための「**d:**」を入力せずにコマンド ライン メソッドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="12870-168">When you are ready to compile, you can either choose **Build** from the **Build** menu, or use the command line method but without typing the **d:** to define conditional compilation symbols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12870-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="12870-169">See also</span></span>

- [<span data-ttu-id="12870-170">アプリケーションのトレースとインストルメント</span><span class="sxs-lookup"><span data-stu-id="12870-170">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="12870-171">方法: トレース スイッチを作成、初期化、および構成する</span><span class="sxs-lookup"><span data-stu-id="12870-171">How to: Create, Initialize and Configure Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="12870-172">トレース スイッチ</span><span class="sxs-lookup"><span data-stu-id="12870-172">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)
- [<span data-ttu-id="12870-173">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="12870-173">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)
- [<span data-ttu-id="12870-174">方法: アプリケーション コードにトレース ステートメントを追加する</span><span class="sxs-lookup"><span data-stu-id="12870-174">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="12870-175">方法: Visual Studio のコマンドラインのための環境変数を設定する</span><span class="sxs-lookup"><span data-stu-id="12870-175">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [<span data-ttu-id="12870-176">方法: コマンド ライン コンパイラを呼び出す</span><span class="sxs-lookup"><span data-stu-id="12870-176">How to: Invoke the Command-Line Compiler</span></span>](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)
