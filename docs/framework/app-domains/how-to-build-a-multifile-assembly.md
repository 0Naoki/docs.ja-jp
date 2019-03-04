---
title: '方法: マルチファイル アセンブリをビルドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68f525244f2238ebdc44116fc91c3ddcb0a79bfd
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975057"
---
# <a name="how-to-build-a-multifile-assembly"></a><span data-ttu-id="60ee9-102">方法: マルチファイル アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="60ee9-102">How to: Build a Multifile Assembly</span></span>
<span data-ttu-id="60ee9-103">この記事では、マルチファイル アセンブリを作成する方法を説明し、プロシージャの各手順を示すコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-103">This article explains how to create a multifile assembly and provides code that illustrates each step in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="60ee9-104">Visual Studio IDE for C# および Visual Basic は、シングルファイル アセンブリの作成でしか使用できません。</span><span class="sxs-lookup"><span data-stu-id="60ee9-104">The Visual Studio IDE for C# and Visual Basic can only be used to create single-file assemblies.</span></span> <span data-ttu-id="60ee9-105">マルチファイル アセンブリを作成する場合は、コマンド ライン コンパイラまたは Visual C++ 付き Visual Studio を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60ee9-105">If you want to create multifile assemblies, you must use the command-line compilers or Visual Studio with Visual C++.</span></span>

### <a name="to-create-a-multifile-assembly"></a><span data-ttu-id="60ee9-106">マルチファイル アセンブリを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="60ee9-106">To create a multifile assembly</span></span>

01. <span data-ttu-id="60ee9-107">アセンブリ内のほかのモジュールによって参照される名前空間を含むすべてのファイルをコンパイルして、コード モジュールを生成します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-107">Compile all files that contain namespaces referenced by other modules in the assembly into code modules.</span></span> <span data-ttu-id="60ee9-108">コード モジュールの既定の拡張子は .netmodule です。</span><span class="sxs-lookup"><span data-stu-id="60ee9-108">The default extension for code modules is .netmodule.</span></span>

    <span data-ttu-id="60ee9-109">たとえば、`Stringer` ファイルに `myStringer` と呼ばれるクラスを含む `Stringer` という名前空間があるとします。</span><span class="sxs-lookup"><span data-stu-id="60ee9-109">For example, let's say the `Stringer` file has a namespace called `myStringer`, which includes a class called `Stringer`.</span></span> <span data-ttu-id="60ee9-110">`Stringer` クラスには、コンソールに 1 つの行を書き込む `StringerMethod` メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="60ee9-110">The `Stringer` class contains a method called `StringerMethod` that writes a single line to the console.</span></span>

    [!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]
    [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]
    [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]

    <span data-ttu-id="60ee9-111">このコードをコンパイルするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-111">Use the following command to compile this code:</span></span>

    [!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]
    [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]
    [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]

    <span data-ttu-id="60ee9-112">*module* パラメーターと **/t:** コンパイラ オプションを指定すると、ファイルはアセンブリではなくモジュールとしてコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="60ee9-112">Specifying the *module* parameter with the **/t:** compiler option indicates that the file should be compiled as a module rather than as an assembly.</span></span> <span data-ttu-id="60ee9-113">コンパイラは、アセンブリに追加できる `Stringer.netmodule` モジュールを生成します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-113">The compiler produces a module called `Stringer.netmodule`, which can be added to an assembly.</span></span>

02. <span data-ttu-id="60ee9-114">コード内で参照されるほかのモジュールを示すために必要なコンパイラ オプションを使用して、ほかのすべてのモジュールをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="60ee9-114">Compile all other modules, using the necessary compiler options to indicate the other modules that are referenced in the code.</span></span> <span data-ttu-id="60ee9-115">この手順では、**/addmodule** コンパイラ オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-115">This step uses the **/addmodule** compiler option.</span></span>

    <span data-ttu-id="60ee9-116">次の例では、`Client` コード モジュールに、手順 1. で作成した `Main` モジュール内のメソッドを参照するエントリ ポイント `Stringer.dll` メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="60ee9-116">In the following example, a code module called `Client` has an entry point `Main` method that references a method in the `Stringer.dll` module created in step 1.</span></span>

    [!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]
    [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]
    [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]

    <span data-ttu-id="60ee9-117">このコードをコンパイルするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-117">Use the following command to compile this code:</span></span>

    [!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]
    [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]
    [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]

    <span data-ttu-id="60ee9-118">このモジュールは後の手順でアセンブリに追加するため、**/t:module** オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-118">Specify the **/t:module** option because this module will be added to an assembly in a future step.</span></span> <span data-ttu-id="60ee9-119">`Client` 内のコードが `Stringer.netmodule` 内のコードによって作成された名前空間を参照するため、**/addmodule** オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-119">Specify the **/addmodule** option because the code in `Client` references a namespace created by the code in `Stringer.netmodule`.</span></span> <span data-ttu-id="60ee9-120">コンパイラは、`Client.netmodule` という別のモジュールへの参照を格納する `Stringer.netmodule` モジュールを生成します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-120">The compiler produces a module called `Client.netmodule` that contains a reference to another module, `Stringer.netmodule`.</span></span>

    >[!NOTE]
    ><span data-ttu-id="60ee9-121">C# コンパイラと Visual Basic コンパイラは、マルチファイル アセンブリを直接作成する場合、次の 2 種類の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-121">The C# and Visual Basic compilers support directly creating multifile assemblies using the following two different syntaxes.</span></span>
    >
    >- <span data-ttu-id="60ee9-122">2 回のコンパイルで、2 ファイルのアセンブリを作成する。</span><span class="sxs-lookup"><span data-stu-id="60ee9-122">Two compilations create a two-file assembly:</span></span>
    >
    >    [!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]
    >    [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]
    >    [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]
    >
    >- <span data-ttu-id="60ee9-123">1 回のコンパイルで、2 ファイルのアセンブリを作成する。</span><span class="sxs-lookup"><span data-stu-id="60ee9-123">One compilation creates a two-file assembly:</span></span>
    >
    >    [!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]
    >    [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]
    >    [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]

03. <span data-ttu-id="60ee9-124">[アセンブリ リンカー (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) を使用して、アセンブリ マニフェストを格納する出力ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-124">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the output file that contains the assembly manifest.</span></span> <span data-ttu-id="60ee9-125">このファイルは、アセンブリの一部であるすべてのモジュールまたはリソースについての参照情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-125">This file contains reference information for all modules or resources that are part of the assembly.</span></span>

    <span data-ttu-id="60ee9-126">コマンド プロンプトに次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-126">At the command prompt, type the following command:</span></span>

    <span data-ttu-id="60ee9-127">**al** \<*module name*> \<*module name*> …</span><span class="sxs-lookup"><span data-stu-id="60ee9-127">**al** \<*module name*> \<*module name*> …</span></span> <span data-ttu-id="60ee9-128">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span><span class="sxs-lookup"><span data-stu-id="60ee9-128">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span></span>

    <span data-ttu-id="60ee9-129">このコマンドで、*module name* 引数はアセンブリに含める各モジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-129">In this command, the *module name* arguments specify the name of each module to include in the assembly.</span></span> <span data-ttu-id="60ee9-130">**/main:** オプションは、アセンブリのエントリ ポイントであるメソッド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-130">The **/main:** option specifies the method name that is the assembly's entry point.</span></span> <span data-ttu-id="60ee9-131">**/out:** オプションは、アセンブリ メタデータを格納する出力ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-131">The **/out:** option specifies the name of the output file, which contains assembly metadata.</span></span> <span data-ttu-id="60ee9-132">**/target:** オプションは、アセンブリがコンソール アプリケーション実行可能ファイル (.exe)、Windows 実行可能ファイル (.win)、またはライブラリ ファイル (.lib) であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-132">The **/target:** option specifies that the assembly is a console application executable (.exe) file, a Windows executable (.win) file, or a library (.lib) file.</span></span>

    <span data-ttu-id="60ee9-133">Al.exe を使用して、コンソール アプリケーションを実行する `myAssembly.exe` という名前のアセンブリを作成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-133">In the following example, Al.exe creates an assembly that is a console application executable called `myAssembly.exe`.</span></span> <span data-ttu-id="60ee9-134">このアプリケーションは、`Client.netmodule` と `Stringer.netmodule` の 2 つのモジュール、およびアセンブリ メタデータだけを格納する実行可能ファイル `myAssembly.exe,` で構成されます。</span><span class="sxs-lookup"><span data-stu-id="60ee9-134">The application consists of two modules called `Client.netmodule` and `Stringer.netmodule`, and the executable file called `myAssembly.exe,` which contains only assembly metadata.</span></span> <span data-ttu-id="60ee9-135">アセンブリのエントリ ポイントは `Main` クラスの `MainClientApp` メソッドで、`Client.dll` 内に配置されています。</span><span class="sxs-lookup"><span data-stu-id="60ee9-135">The entry point of the assembly is the `Main` method in the class `MainClientApp`, which is located in `Client.dll`.</span></span>

    ```
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    <span data-ttu-id="60ee9-136">[MSIL 逆アセンブラー (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) を使用すると、アセンブリの内容を調査したり、ファイルがアセンブリであるかモジュールであるかを判断したりできます。</span><span class="sxs-lookup"><span data-stu-id="60ee9-136">You can use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the contents of an assembly, or determine whether a file is an assembly or a module.</span></span>

## <a name="see-also"></a><span data-ttu-id="60ee9-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="60ee9-137">See also</span></span>
- [<span data-ttu-id="60ee9-138">アセンブリの作成</span><span class="sxs-lookup"><span data-stu-id="60ee9-138">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)
- [<span data-ttu-id="60ee9-139">方法: アセンブリの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="60ee9-139">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)
- [<span data-ttu-id="60ee9-140">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="60ee9-140">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="60ee9-141">マルチファイル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="60ee9-141">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
