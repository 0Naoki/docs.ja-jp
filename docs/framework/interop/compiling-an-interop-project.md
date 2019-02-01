---
title: 相互運用プロジェクトのコンパイル
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a1e6ea8a7a7e6869ca9bc6c1b635f30574ac97f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695195"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="580bd-102">相互運用プロジェクトのコンパイル</span><span class="sxs-lookup"><span data-stu-id="580bd-102">Compiling an Interop Project</span></span>

<span data-ttu-id="580bd-103">インポートされた COM 型を含む 1 つ以上のアセンブリを参照する COM 相互運用プロジェクトは、他のマネージド プロジェクトと同じようにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="580bd-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="580bd-104">相互運用機能アセンブリは、Visual Studio などの開発環境で参照できます。コマンド ライン コンパイラを使用して参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="580bd-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="580bd-105">どちらの場合でも、正常にコンパイルするには、相互運用機能アセンブリを、その他のプロジェクト ファイルと同じディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="580bd-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="580bd-106">相互運用機能アセンブリを参照する方法には、次の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="580bd-106">There are two ways to reference interop assemblies:</span></span>

-   <span data-ttu-id="580bd-107">埋め込まれた相互運用機能型:[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] および Visual Studio 2010 以降では、相互運用機能アセンブリから実行可能ファイルに型情報を埋め込むようにコンパイラに指示できます。</span><span class="sxs-lookup"><span data-stu-id="580bd-107">Embedded interop types: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="580bd-108">この手法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="580bd-108">This is the recommended technique.</span></span>

-   <span data-ttu-id="580bd-109">相互運用機能アセンブリの配置:相互運用機能アセンブリへの標準の参照を作成できます。</span><span class="sxs-lookup"><span data-stu-id="580bd-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="580bd-110">この場合、アプリケーションで相互運用機能アセンブリを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="580bd-110">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="580bd-111">この 2 つの手法の違いの詳細については、「[Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))」(マネージド コードでの COM 型の使用) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580bd-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span></span>

 <span data-ttu-id="580bd-112">Visual Studio での相互運用機能型の埋め込みについては、「[チュートリアル:Microsoft Office アセンブリからの型情報の埋め込み (C# および Visual Basic)](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))」および「[チュートリアル:マネージド アセンブリからの型の埋め込み](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="580bd-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)) and [Walkthrough: Embedding Types from Managed Assemblies](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>

 <span data-ttu-id="580bd-113">コマンド ライン コンパイラを使用して相互運用機能アセンブリを参照し、実行可能ファイルに型情報を埋め込むには、[/link (C# コンパイラ オプション)](../../csharp/language-reference/compiler-options/link-compiler-option.md) または [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) コンパイラ スイッチを使用して、相互運用機能アセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="580bd-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="580bd-114">Visual C++ アプリケーションは型情報を埋め込むことはできませんが、型情報を埋め込むことができるアプリケーションまたはアドインと相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="580bd-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="580bd-115">配置時にプライマリ相互運用機能アセンブリを含むアプリケーションをコンパイルするには、**/reference** コンパイラ スイッチを使用して、相互運用機能アセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="580bd-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="580bd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="580bd-116">See also</span></span>

- [<span data-ttu-id="580bd-117">.NET Framework への COM コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="580bd-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="580bd-118">言語への非依存性、および言語非依存コンポーネント</span><span class="sxs-lookup"><span data-stu-id="580bd-118">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="580bd-119">[マネージド コードでの COM 型の使用](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="580bd-119">[Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span></span>
- <span data-ttu-id="580bd-120">[チュートリアル: Microsoft Office アセンブリからの型情報の埋め込み](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="580bd-120">[Walkthrough: Embedding Type Information from Microsoft Office Assemblies](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span></span>
- [<span data-ttu-id="580bd-121">チュートリアル: マネージド アセンブリからの型の埋め込み</span><span class="sxs-lookup"><span data-stu-id="580bd-121">Walkthrough: Embedding Types from Managed Assemblies</span></span>](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)
- [<span data-ttu-id="580bd-122">タイプ ライブラリのアセンブリとしてのインポート</span><span class="sxs-lookup"><span data-stu-id="580bd-122">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)