---
title: '&lt;list&gt; (C# プログラミング ガイド)'
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 3f9d1e2b08b672ca58e96767aedaa71a8826c0ab
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512433"
---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="51267-102">&lt;list&gt; (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="51267-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="51267-103">構文</span><span class="sxs-lookup"><span data-stu-id="51267-103">Syntax</span></span>  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51267-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="51267-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="51267-105">定義される用語であり、`description` で定義されます。</span><span class="sxs-lookup"><span data-stu-id="51267-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="51267-106">行頭文字または番号付きリストの項目、または `term` の定義です。</span><span class="sxs-lookup"><span data-stu-id="51267-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51267-107">コメント</span><span class="sxs-lookup"><span data-stu-id="51267-107">Remarks</span></span>  
 <span data-ttu-id="51267-108">\< > ブロックを使用して、テーブルまたは定義の一覧の見出し行を定義します。</span><span class="sxs-lookup"><span data-stu-id="51267-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="51267-109">テーブルを定義するときにのみ、見出しの用語のエントリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51267-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="51267-110">リスト内の各項目は、\<item> ブロックで指定されます。</span><span class="sxs-lookup"><span data-stu-id="51267-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="51267-111">定義リストを作成する場合は、`term` と `description` の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51267-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="51267-112">ただし、テーブル、箇条書きリスト、または番号付きリストの場合は、`description` のエントリを指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="51267-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="51267-113">リストまたはテーブルでは、必要な数の \<item> ブロックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="51267-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="51267-114">コンパイル時に [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="51267-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51267-115">例</span><span class="sxs-lookup"><span data-stu-id="51267-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="51267-116">参照</span><span class="sxs-lookup"><span data-stu-id="51267-116">See Also</span></span>

- [<span data-ttu-id="51267-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="51267-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="51267-118">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="51267-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
