---
ms.openlocfilehash: 69b25db88c7580787bbb47fb0902b6bb072f8dde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235736"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="0850a-101">Regex.CompileToAssembly でコンパイルされたアセンブリは 4.0 と 4.5 の間で区別されます</span><span class="sxs-lookup"><span data-stu-id="0850a-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0850a-102">説明</span><span class="sxs-lookup"><span data-stu-id="0850a-102">Details</span></span>|<span data-ttu-id="0850a-103">コンパイル済みの正規表現のアセンブリが .NET Framework 4.5 でビルドされ、.NET Framework 4 を対象としている場合、.NET Framework 4 がインストールされているシステム上でそのアセンブリの正規表現の 1 つを使用しようとすると、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="0850a-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>|
|<span data-ttu-id="0850a-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0850a-104">Suggestion</span></span>|<span data-ttu-id="0850a-105">この問題を回避するには、次のいずれかの方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="0850a-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="0850a-106">.NET Framework 4 を使用して正規表現を含むアセンブリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0850a-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="0850a-107">解釈される正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="0850a-107">Use an interpreted regular expression.</span></span></li></ul>|
|<span data-ttu-id="0850a-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="0850a-108">Scope</span></span>|<span data-ttu-id="0850a-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="0850a-109">Minor</span></span>|
|<span data-ttu-id="0850a-110">Version</span><span class="sxs-lookup"><span data-stu-id="0850a-110">Version</span></span>|<span data-ttu-id="0850a-111">4.5</span><span class="sxs-lookup"><span data-stu-id="0850a-111">4.5</span></span>|
|<span data-ttu-id="0850a-112">型</span><span class="sxs-lookup"><span data-stu-id="0850a-112">Type</span></span>|<span data-ttu-id="0850a-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="0850a-113">Runtime</span></span>|
|<span data-ttu-id="0850a-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="0850a-114">Affected APIs</span></span>|<ul><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
