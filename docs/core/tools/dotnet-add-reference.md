---
title: dotnet-add 参照コマンド - .NET Core CLI
description: dotnet add 参照コマンドは、プロジェクト間参照を追加する便利なオプションを提供します。
author: mairaw
ms.author: mairaw
ms.date: 12/04/2018
ms.openlocfilehash: 33c5e532baf23cc8fe2b3a5084bff029caece842
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129546"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="29c7c-103">dotnet-add 参照</span><span class="sxs-lookup"><span data-stu-id="29c7c-103">dotnet-add reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="29c7c-104">name</span><span class="sxs-lookup"><span data-stu-id="29c7c-104">Name</span></span>

<span data-ttu-id="29c7c-105">`dotnet add reference` - プロジェクト間 (P2P) 参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="29c7c-105">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="29c7c-106">構文</span><span class="sxs-lookup"><span data-stu-id="29c7c-106">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="29c7c-107">説明</span><span class="sxs-lookup"><span data-stu-id="29c7c-107">Description</span></span>

<span data-ttu-id="29c7c-108">`dotnet add reference` コマンドは、プロジェクトにプロジェクト参照を追加する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="29c7c-108">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="29c7c-109">このコマンドを実行すると、[`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) 要素がプロジェクト ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="29c7c-109">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="29c7c-110">引数</span><span class="sxs-lookup"><span data-stu-id="29c7c-110">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="29c7c-111">プロジェクト ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="29c7c-111">Specifies the project file.</span></span> <span data-ttu-id="29c7c-112">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="29c7c-112">If not specified, the command searches the current directory for one.</span></span>

* **`PROJECT_REFERENCES`**

  <span data-ttu-id="29c7c-113">追加するプロジェクト間参照 (P2P) です。</span><span class="sxs-lookup"><span data-stu-id="29c7c-113">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="29c7c-114">1 つ以上のプロジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="29c7c-114">Specify one or more projects.</span></span> <span data-ttu-id="29c7c-115">[glob パターン](https://en.wikipedia.org/wiki/Glob_(programming))は Unix/Linux ベースのシステムで利用できます。</span><span class="sxs-lookup"><span data-stu-id="29c7c-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="29c7c-116">オプション</span><span class="sxs-lookup"><span data-stu-id="29c7c-116">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="29c7c-117">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="29c7c-117">Prints out a short help for the command.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="29c7c-118">特定の[フレームワーク](../../standard/frameworks.md)を対象にしている場合にのみ、プロジェクト参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="29c7c-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="29c7c-119">使用例</span><span class="sxs-lookup"><span data-stu-id="29c7c-119">Examples</span></span>

* <span data-ttu-id="29c7c-120">プロジェクト参照を追加する:</span><span class="sxs-lookup"><span data-stu-id="29c7c-120">Add a project reference:</span></span>

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* <span data-ttu-id="29c7c-121">現在のディレクトリのプロジェクトに複数のプロジェクト参照を追加する:</span><span class="sxs-lookup"><span data-stu-id="29c7c-121">Add multiple project references to the project in the current directory:</span></span>

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* <span data-ttu-id="29c7c-122">Linux/Unix で glob パターンを使って複数のプロジェクト参照を追加する:</span><span class="sxs-lookup"><span data-stu-id="29c7c-122">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```