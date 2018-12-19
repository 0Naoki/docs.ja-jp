---
title: '#pragma - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 65867bc441711193f93142d1c65122b6bc60c25d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241828"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="74e55-102">#pragma (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="74e55-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="74e55-103">`#pragma` は、ファイル内に指定され、そのファイルのコンパイルについての特別な命令をコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="74e55-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="74e55-104">命令はコンパイラによってサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e55-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="74e55-105">つまり、`#pragma` を使用してカスタムの前処理命令を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="74e55-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="74e55-106">Microsoft C# コンパイラは、次の 2 つの `#pragma` 命令をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="74e55-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="74e55-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="74e55-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="74e55-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="74e55-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="74e55-109">構文</span><span class="sxs-lookup"><span data-stu-id="74e55-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74e55-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74e55-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="74e55-111">認識されているプラグマの名前。</span><span class="sxs-lookup"><span data-stu-id="74e55-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="74e55-112">プラグマに固有の引数。</span><span class="sxs-lookup"><span data-stu-id="74e55-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74e55-113">参照</span><span class="sxs-lookup"><span data-stu-id="74e55-113">See Also</span></span>

- [<span data-ttu-id="74e55-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="74e55-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="74e55-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="74e55-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="74e55-116">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="74e55-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [<span data-ttu-id="74e55-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="74e55-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
- [<span data-ttu-id="74e55-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="74e55-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
