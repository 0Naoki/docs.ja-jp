---
title: <remarks> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: b290315cd9c36281c110bbf0c6246468a1a899b2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259164"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="dcf6b-102">\<remarks> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="dcf6b-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="dcf6b-103">構文</span><span class="sxs-lookup"><span data-stu-id="dcf6b-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dcf6b-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dcf6b-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="dcf6b-105">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="dcf6b-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcf6b-106">コメント</span><span class="sxs-lookup"><span data-stu-id="dcf6b-106">Remarks</span></span>  
 <span data-ttu-id="dcf6b-107">\<remarks> タグを使用して、型の情報を追加し、[\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) で指定された情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="dcf6b-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="dcf6b-108">この情報はオブジェクト ブラウザー ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dcf6b-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="dcf6b-109">コンパイル時に [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="dcf6b-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcf6b-110">例</span><span class="sxs-lookup"><span data-stu-id="dcf6b-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="dcf6b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcf6b-111">See also</span></span>

- [<span data-ttu-id="dcf6b-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="dcf6b-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dcf6b-113">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="dcf6b-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
