---
title: F# Interactive (fsi.exe) のリファレンス
description: 学習方法F#Interactive (fsi.exe) は、実行に使用されるF#対話的に、コンソールで、またはを実行するコードF#スクリプト。
ms.date: 05/16/2016
ms.openlocfilehash: 459a2a4ba49ba0f55455797617781d010efecc0b
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170719"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="f194f-103">F# による対話型プログラミング</span><span class="sxs-lookup"><span data-stu-id="f194f-103">Interactive Programming with F#</span></span> #

> [!NOTE]
<span data-ttu-id="f194f-104">この記事では、現時点の Windows のエクスペリエンスについてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="f194f-104">This article currently describes the experience for Windows only.</span></span>  <span data-ttu-id="f194f-105">書き換えられる予定です。</span><span class="sxs-lookup"><span data-stu-id="f194f-105">It will be rewritten.</span></span>

> [!NOTE]
<span data-ttu-id="f194f-106">API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="f194f-106">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="f194f-107">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="f194f-107">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f194f-108">F# Interactive (fsi.exe) は、コンソールで F# コードを対話形式で実行したり、F# スクリプトを実行したりするために使用します。</span><span class="sxs-lookup"><span data-stu-id="f194f-108">F# Interactive (fsi.exe) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="f194f-109">つまり、F# Interactive は、F# 言語の REPL (Read、Evaluate、Print Loop) を実行します。</span><span class="sxs-lookup"><span data-stu-id="f194f-109">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="f194f-110">コンソールから F# Interactive を実行するには、fsi.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="f194f-110">To run F# Interactive from the console, run fsi.exe.</span></span>  <span data-ttu-id="f194f-111">Fsi.exe で表示されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-111">You will find fsi.exe in:</span></span>

```console
C:\Program Files (x86)\Microsoft Visual Studio\2017\<sku>\Common7\IDE\CommonExtensions\Microsoft\FSharp
```

<span data-ttu-id="f194f-112">場所`sku`か`Community`、 `Professional`、または`Enterprise`します。</span><span class="sxs-lookup"><span data-stu-id="f194f-112">where `sku` is either `Community`, `Professional`, or `Enterprise`.</span></span>

<span data-ttu-id="f194f-113">使用できるコマンド ライン オプションについては、「[F# Interactive Options](../../language-reference/fsharp-interactive-options.md)」 (F# Interactive オプション) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f194f-113">For information about command line options available, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

<span data-ttu-id="f194f-114">Visual Studio で F# Interactive を実行するには、ツール バーの **[F# Interactive]** というボタンをクリックするか、**Ctrl + Alt + F** キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f194f-114">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive**, or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="f194f-115">この操作により、対話形式のウィンドウが開きます。このウィンドウは、F# Interactive セッションを実行するツール ウィンドウです</span><span class="sxs-lookup"><span data-stu-id="f194f-115">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="f194f-116">対話形式のウィンドウで実行するコードを選択し、**Alt + Enter** キーの組み合わせを押す方法もあります。</span><span class="sxs-lookup"><span data-stu-id="f194f-116">You can also select some code that you want to run in the interactive window and hit the key combination **ALT+ENTER**.</span></span> <span data-ttu-id="f194f-117">F# インタラクティブが **[F# Interactive]** というツール ウィンドウで開始されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-117">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="f194f-118">このショートカット キーを使用するときは、エディター ウィンドウにフォーカスがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f194f-118">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="f194f-119">コンソールと Visual Studio のどちらを使用している場合でも、コマンド プロンプトが表示され、入力待ちの状態になります。</span><span class="sxs-lookup"><span data-stu-id="f194f-119">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="f194f-120">コード ファイルと同じようにコードを入力できます。</span><span class="sxs-lookup"><span data-stu-id="f194f-120">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="f194f-121">コードをコンパイルして実行するには、2 つのセミコロン (**;;**) を入力して、入力行を終了します。</span><span class="sxs-lookup"><span data-stu-id="f194f-121">To compile and execute the code, enter two semicolons (**;;**) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="f194f-122">F# Interactive によってコードがコンパイルされ、成功すると、コードが実行され、コンパイルされた型のシグネチャと値が出力されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-122">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="f194f-123">エラーが発生した場合は、エラー メッセージが出力されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-123">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="f194f-124">同じセッションで入力したコードからは、前に入力したどの構成要素にもアクセスできるため、プログラムの構築が可能です。</span><span class="sxs-lookup"><span data-stu-id="f194f-124">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="f194f-125">ツール ウィンドウには十分なバッファーが用意されており、必要に応じてコードをファイルにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="f194f-125">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="f194f-126">Visual Studio で実行する場合、F# Interactive はプロジェクトとは独立して動作します。このため、たとえば、プロジェクトで定義された構成要素を F# Interactive で使用することはできません。使用するには、関数のコードを対話形式のウィンドウにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f194f-126">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="f194f-127">あるライブラリを参照するプロジェクトを開くと、**ソリューション エクスプローラー**で、F# Interactive のライブラリを参照できます。</span><span class="sxs-lookup"><span data-stu-id="f194f-127">If you have a project open that references some libraries, you can reference these in F# Interactive through **Solution Explorer**.</span></span> <span data-ttu-id="f194f-128">F# Interactive のライブラリを参照するには、**[参照]** ノードを展開し、ライブラリのショートカット メニューを開き、**[F# Interactive に送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f194f-128">To reference a library in F# Interactive, expand the **References** node, open the shortcut menu for the library, and choose **Send to F# Interactive**.</span></span>

<span data-ttu-id="f194f-129">設定を調整することで、F# Interactive コマンド ライン引数 (オプション) を制御できます。</span><span class="sxs-lookup"><span data-stu-id="f194f-129">You can control the F# Interactive command line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="f194f-130">**[ツール]** メニューの **[オプション]** をクリックし、**[F# ツール]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="f194f-130">On the **Tools** menu, select **Options...**, and then expand **F# Tools**.</span></span> <span data-ttu-id="f194f-131">変更できる 2 つの設定は、F# Interactive オプションおよび 64 ビット コンピューターで F# Interactive を実行する場合にのみ関連する **64 ビット F# Interactive** 設定です。</span><span class="sxs-lookup"><span data-stu-id="f194f-131">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="f194f-132">この設定によって、32 ビットまたは 64 ビット プロセスとして実行するかどうかを決定するためにコンピューター アーキテクチャを使用する、fsi.exe または fsianycpu.exe の専用の 64 ビット バージョンを実行するかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-132">This setting determines whether you want to run the dedicated 64-bit version of fsi.exe or fsianycpu.exe, which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>


## <a name="scripting-with-f"></a><span data-ttu-id="f194f-133">F# によるスクリプト</span><span class="sxs-lookup"><span data-stu-id="f194f-133">Scripting with F#</span></span> #
<span data-ttu-id="f194f-134">スクリプトで使用されるファイル拡張子は **.fsx** または **.fsscript** です。</span><span class="sxs-lookup"><span data-stu-id="f194f-134">Scripts use the file extension **.fsx** or **.fsscript**.</span></span> <span data-ttu-id="f194f-135">ソース コードをコンパイルし、後でそのコンパイル済みのアセンブリを実行する代わりに、**fsi.exe** を実行し、F# ソース コードのスクリプトのファイル名を指定するだけで、F# Interactive によってコードを読み取り、リアルタイムで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f194f-135">Instead of compiling source code and then later running the compiled assembly, you can just run **fsi.exe** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span>


## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a><span data-ttu-id="f194f-136">対話型、スクリプト、およびコンパイル型の環境の相違</span><span class="sxs-lookup"><span data-stu-id="f194f-136">Differences Between the Interactive, Scripting and Compiled Environments</span></span>
<span data-ttu-id="f194f-137">F# Interactive でのコードのコンパイル時には、対話形式で実行しているか、スクリプトを実行しているかにかかわらず、シンボル **INTERACTIVE** が定義されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-137">When you are compiling code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="f194f-138">コンパイラでのコードのコンパイル時には、シンボル **COMPILED** が定義されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-138">When you are compiling code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="f194f-139">したがって、コンパイル モードと対話モードでコードを別にする必要がある場合は、条件付きコンパイルを行うプリプロセッサ ディレクティブを使用して、どちらを有効にするかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="f194f-139">Thus, if code needs to be different in compiled and interactive modes, you can use preprocessor directives for conditional compilation to determine which to use.</span></span>

<span data-ttu-id="f194f-140">F# Interactive でスクリプトを実行するときに使用できるディレクティブの中には、コンパイラを実行するときには使用できないものがあります。</span><span class="sxs-lookup"><span data-stu-id="f194f-140">Some directives are available when you are executing scripts in F# Interactive that are not available when you are executing the compiler.</span></span> <span data-ttu-id="f194f-141">次の表に、F# Interactive で使用できるディレクティブの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="f194f-141">The following table summarizes directives that are available when you are using F# Interactive.</span></span>

|<span data-ttu-id="f194f-142">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f194f-142">Directive</span></span>|<span data-ttu-id="f194f-143">説明</span><span class="sxs-lookup"><span data-stu-id="f194f-143">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="f194f-144">**#help**</span><span class="sxs-lookup"><span data-stu-id="f194f-144">**#help**</span></span>|<span data-ttu-id="f194f-145">使用できるディレクティブに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f194f-145">Displays information about available directives.</span></span>|
|<span data-ttu-id="f194f-146">**#I**</span><span class="sxs-lookup"><span data-stu-id="f194f-146">**#I**</span></span>|<span data-ttu-id="f194f-147">アセンブリ検索パスを引用符で囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="f194f-147">Specifies an assembly search path in quotation marks.</span></span>|
|<span data-ttu-id="f194f-148">**#load**</span><span class="sxs-lookup"><span data-stu-id="f194f-148">**#load**</span></span>|<span data-ttu-id="f194f-149">ソース ファイルを読み取り、コンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="f194f-149">Reads a source file, compiles it, and runs it.</span></span>|
|<span data-ttu-id="f194f-150">**#quit**</span><span class="sxs-lookup"><span data-stu-id="f194f-150">**#quit**</span></span>|<span data-ttu-id="f194f-151">F# Interactive セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="f194f-151">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="f194f-152">**#r**</span><span class="sxs-lookup"><span data-stu-id="f194f-152">**#r**</span></span>|<span data-ttu-id="f194f-153">アセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="f194f-153">References an assembly.</span></span>|
|<span data-ttu-id="f194f-154">**#time ["on"&#124;"off"]**</span><span class="sxs-lookup"><span data-stu-id="f194f-154">**#time ["on"&#124;"off"]**</span></span>|<span data-ttu-id="f194f-155">**#time** 単独で、パフォーマンス情報を表示するかどうかを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f194f-155">By itself, **#time** toggles whether to display performance information.</span></span> <span data-ttu-id="f194f-156">有効にすると、解釈および実行されるコードのセクションごとに、実時間、CPU 時間、およびガベージ コレクションの情報が F# Interactive によって計測されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-156">When it is enabled, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="f194f-157">F# Interactive でファイルまたはパスを指定するときは、リテラル文字列が想定されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-157">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="f194f-158">したがって、ファイルとパスは引用符で囲む必要があり、通常のエスケープ文字が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f194f-158">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="f194f-159">また、@ 文字を使用して、パスを含む文字列が F# Internactive で逐語的文字列として解釈されるように指示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f194f-159">Also, you can use the @ character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="f194f-160">この場合、F# Interactive はエスケープ文字を無視するようになります。</span><span class="sxs-lookup"><span data-stu-id="f194f-160">This causes F# Interactive to ignore any escape characters.</span></span>

<span data-ttu-id="f194f-161">コンパイル モードと対話モードの違いの 1 つは、コマンド ライン引数にアクセスする方法です。</span><span class="sxs-lookup"><span data-stu-id="f194f-161">One of the differences between compiled and interactive mode is the way you access command line arguments.</span></span> <span data-ttu-id="f194f-162">コンパイル モードでは **System.Environment.GetCommandLineArgs** を使用します。</span><span class="sxs-lookup"><span data-stu-id="f194f-162">In compiled mode, use **System.Environment.GetCommandLineArgs**.</span></span> <span data-ttu-id="f194f-163">スクリプトでは、**fsi.CommandLineArgs** を使用します。</span><span class="sxs-lookup"><span data-stu-id="f194f-163">In scripts, use **fsi.CommandLineArgs**.</span></span>

<span data-ttu-id="f194f-164">次のコードは、スクリプトでコマンド ライン引数を読み取る関数を作成する方法と、スクリプトから別のアセンブリを参照する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f194f-164">The following code illustrates how to create a function that reads the command line arguments in a script and also demonstrates how to reference another assembly from a script.</span></span> <span data-ttu-id="f194f-165">最初のコード ファイル **MyAssembly.fs** は、参照先となるアセンブリのコードです。</span><span class="sxs-lookup"><span data-stu-id="f194f-165">The first code file, **MyAssembly.fs**, is the code for the assembly being referenced.</span></span> <span data-ttu-id="f194f-166">このファイルをコマンド ラインでコンパイルし (**fsc -a MyAssembly.fs**)、2 番目のファイルをスクリプトとしてコマンド ラインで実行します (**fsi --exec file1.fsx** test)。</span><span class="sxs-lookup"><span data-stu-id="f194f-166">Compile this file with the command line: **fsc -a MyAssembly.fs** and then execute the second file as a script with the command line: **fsi --exec file1.fsx** test</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="f194f-167">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f194f-167">The output is as follows:</span></span>

```
Command line arguments: 
file1.fsx
test
90
```

## <a name="related-topics"></a><span data-ttu-id="f194f-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f194f-168">Related Topics</span></span>

|<span data-ttu-id="f194f-169">Title</span><span class="sxs-lookup"><span data-stu-id="f194f-169">Title</span></span>|<span data-ttu-id="f194f-170">説明</span><span class="sxs-lookup"><span data-stu-id="f194f-170">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="f194f-171">F# Interactive オプション</span><span class="sxs-lookup"><span data-stu-id="f194f-171">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="f194f-172">コマンドライン構文について説明し、オプション、F#対話形式で、fsi.exe します。</span><span class="sxs-lookup"><span data-stu-id="f194f-172">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
|[<span data-ttu-id="f194f-173">F# Interactive ライブラリ リファレンス</span><span class="sxs-lookup"><span data-stu-id="f194f-173">F# Interactive Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-interactive-library-reference)|<span data-ttu-id="f194f-174">F# Interactive でコードを実行するときに使用できるライブラリ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="f194f-174">Describes library functionality available when executing code in F# interactive.</span></span>|
