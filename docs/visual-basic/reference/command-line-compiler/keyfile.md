---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 8e90535739adb4f7f8a88f91e301c2db121241a7
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759341"
---
# <a name="-keyfile"></a><span data-ttu-id="84e6d-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="84e6d-102">-keyfile</span></span>
<span data-ttu-id="84e6d-103">アセンブリに厳密な名前を付けるキーまたはキー ペアを含むファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="84e6d-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e6d-104">構文</span><span class="sxs-lookup"><span data-stu-id="84e6d-104">Syntax</span></span>  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="84e6d-105">引数</span><span class="sxs-lookup"><span data-stu-id="84e6d-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="84e6d-106">必須。</span><span class="sxs-lookup"><span data-stu-id="84e6d-106">Required.</span></span> <span data-ttu-id="84e6d-107">キーを含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="84e6d-107">File that contains the key.</span></span> <span data-ttu-id="84e6d-108">ファイル名にスペースが含まれている場合は、名前を引用符で囲みます ("")。</span><span class="sxs-lookup"><span data-stu-id="84e6d-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84e6d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="84e6d-109">Remarks</span></span>  
 <span data-ttu-id="84e6d-110">コンパイラはアセンブリ マニフェストに公開キーを挿入し、秘密キーで最終アセンブリに署名します。</span><span class="sxs-lookup"><span data-stu-id="84e6d-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="84e6d-111">キー ファイルを生成するには、コマンド ラインで「`sn -k file`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="84e6d-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="84e6d-112">詳細については、次を参照してください。 [Sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md))。</span><span class="sxs-lookup"><span data-stu-id="84e6d-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="84e6d-113">使用してコンパイルする場合`-target:module`、キー ファイルの名前がモジュールに保持され、使用してアセンブリをコンパイルするときに作成されるアセンブリに組み込まれます[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)します。</span><span class="sxs-lookup"><span data-stu-id="84e6d-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="84e6d-114">また、暗号化情報を [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) でコンパイラに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="84e6d-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="84e6d-115">部分的に署名されたアセンブリを作成する場合は、[-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) を使います。</span><span class="sxs-lookup"><span data-stu-id="84e6d-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="84e6d-116">カスタム属性として、このオプションを指定することもできます (<xref:System.Reflection.AssemblyKeyFileAttribute>) 任意の Microsoft intermediate language モジュールのソース コードにします。</span><span class="sxs-lookup"><span data-stu-id="84e6d-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="84e6d-117">場合両方`-keyfile`と[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)がで指定された (コマンド ライン オプションまたはカスタム属性によって)、同じコンパイル時に、コンパイラが最初にキー コンテナーを試みます。</span><span class="sxs-lookup"><span data-stu-id="84e6d-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="84e6d-118">それが成功すると、アセンブリはキー コンテナーの情報で署名されます。</span><span class="sxs-lookup"><span data-stu-id="84e6d-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="84e6d-119">指定したファイルがしようと、コンパイラがキー コンテナーを見つけられない場合`-keyfile`します。</span><span class="sxs-lookup"><span data-stu-id="84e6d-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="84e6d-120">これが成功すると、アセンブリは、キー ファイルの情報で署名およびキーの情報がキー コンテナーにインストールされている場合 (のような`sn -i`) 次のコンパイル時にキー コンテナーが有効になるようにします。</span><span class="sxs-lookup"><span data-stu-id="84e6d-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="84e6d-121">キー ファイルには公開キーだけが含まれる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="84e6d-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="84e6d-122">参照してください[の作成と using strong-named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)アセンブリへの署名の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="84e6d-122">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84e6d-123">`-keyfile`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="84e6d-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84e6d-124">例</span><span class="sxs-lookup"><span data-stu-id="84e6d-124">Example</span></span>  
 <span data-ttu-id="84e6d-125">次のコードは、ソース ファイルをコンパイル`Input.vb`キー ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="84e6d-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="84e6d-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="84e6d-126">See also</span></span>
- [<span data-ttu-id="84e6d-127">アセンブリとグローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="84e6d-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [<span data-ttu-id="84e6d-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="84e6d-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="84e6d-129">-参照 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84e6d-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="84e6d-130">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="84e6d-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
