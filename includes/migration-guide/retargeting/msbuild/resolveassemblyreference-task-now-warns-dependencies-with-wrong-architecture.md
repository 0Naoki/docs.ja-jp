---
ms.openlocfilehash: 39a329597ef28e002242103a247515d94761676a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774464"
---
### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a><span data-ttu-id="37d18-101">ResolveAssemblyReference タスクは、正しくないアーキテクチャとの依存関係に関する警告を表示するようになりました</span><span class="sxs-lookup"><span data-stu-id="37d18-101">ResolveAssemblyReference task now warns of dependencies with the wrong architecture</span></span>

|   |   |
|---|---|
|<span data-ttu-id="37d18-102">説明</span><span class="sxs-lookup"><span data-stu-id="37d18-102">Details</span></span>|<span data-ttu-id="37d18-103">タスクは警告 MSB3270 を生成します。これは参照または依存関係がアプリのアーキテクチャと一致しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="37d18-103">The task emits a warning, MSB3270, which indicates that a reference or any of its dependencies does not match the app's architecture.</span></span> <span data-ttu-id="37d18-104">たとえば、<code>AnyCPU</code> オプションでコンパイルされたアプリに x86 参照が含まれる場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="37d18-104">For example, this occurs if an app that was compiled with the <code>AnyCPU</code> option includes an x86 reference.</span></span> <span data-ttu-id="37d18-105">このようなシナリオは、実行時にアプリでエラーが起こった場合に発生することがあります (この場合は、アプリが x64 プロセスとして配置されている場合)。</span><span class="sxs-lookup"><span data-stu-id="37d18-105">Such a scenario could result in an app failure at run time (in this case, if the app is deployed as an x64 process).</span></span>|
|<span data-ttu-id="37d18-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="37d18-106">Suggestion</span></span>|<span data-ttu-id="37d18-107">影響には 2 つの領域があります。</span><span class="sxs-lookup"><span data-stu-id="37d18-107">There are two areas of impact:</span></span><ul><li><span data-ttu-id="37d18-108">再コンパイルすると、アプリが MSBuild の以前のバージョンでコンパイルされたときには現れなかった警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="37d18-108">Recompilation generates warnings that did not appear when the app was compiled under a previous version of MSBuild.</span></span> <span data-ttu-id="37d18-109">ただし、警告はランタイム エラーの可能性のある原因を特定するため、調査と対処が必要です。</span><span class="sxs-lookup"><span data-stu-id="37d18-109">However, because the warning identifies a possible source of runtime failure, it should be investigated and addressed.</span></span></li><li><span data-ttu-id="37d18-110">警告がエラーとして扱われると、アプリはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="37d18-110">If warnings are treated as errors, the app will fail to compile.</span></span></li></ul>|
|<span data-ttu-id="37d18-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="37d18-111">Scope</span></span>|<span data-ttu-id="37d18-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="37d18-112">Minor</span></span>|
|<span data-ttu-id="37d18-113">Version</span><span class="sxs-lookup"><span data-stu-id="37d18-113">Version</span></span>|<span data-ttu-id="37d18-114">4.5.1</span><span class="sxs-lookup"><span data-stu-id="37d18-114">4.5.1</span></span>|
|<span data-ttu-id="37d18-115">型</span><span class="sxs-lookup"><span data-stu-id="37d18-115">Type</span></span>|<span data-ttu-id="37d18-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="37d18-116">Retargeting</span></span>|
