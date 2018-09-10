---
title: -target:library (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: e15210d189c4a553da72b418f583e44666bac2fc
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2018
ms.locfileid: "44201178"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="5e8a0-102">-target:library (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="5e8a0-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="5e8a0-103">**-target:library** オプションを指定した場合、コンパイラは実行可能ファイル (EXE) ではなく、ダイナミック リンク ライブラリ (DLL) を作成します。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e8a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e8a0-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="5e8a0-105">コメント</span><span class="sxs-lookup"><span data-stu-id="5e8a0-105">Remarks</span></span>  
 <span data-ttu-id="5e8a0-106">.dll 拡張子の DLL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="5e8a0-107">[-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) オプションを特に指定しない限り、出力ファイル名は最初の入力ファイルと同じになります。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-107">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="5e8a0-108">コマンド ラインで指定すると、次の **-out** または **-target:module** オプションまでのすべてのファイルが .dll ファイルを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="5e8a0-109">.dll ファイルを作成する際に、[Main](../../../csharp/programming-guide/main-and-command-args/index.md)メソッドは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5e8a0-110">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="5e8a0-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="5e8a0-111">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="5e8a0-112">**[アプリケーション]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="5e8a0-113">**[出力の種類]** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="5e8a0-114">このコンパイラ オプションをプログラムで設定する方法については、「 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e8a0-115">例</span><span class="sxs-lookup"><span data-stu-id="5e8a0-115">Example</span></span>  
 <span data-ttu-id="5e8a0-116">`in.cs` をコンパイルし、`in.dll` を作成するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e8a0-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e8a0-117">参照</span><span class="sxs-lookup"><span data-stu-id="5e8a0-117">See Also</span></span>  

- [<span data-ttu-id="5e8a0-118">-target (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="5e8a0-118">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
- [<span data-ttu-id="5e8a0-119">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="5e8a0-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
