---
title: '&lt;例外&gt; - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 09c2ce3d7c0c9b8c20d4a32aa1d4c84d4ead4fbf
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245536"
---
# <a name="ltexceptiongt-c-programming-guide"></a><span data-ttu-id="100ac-102">&lt;例外&gt; (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="100ac-102">&lt;exception&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="100ac-103">構文</span><span class="sxs-lookup"><span data-stu-id="100ac-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="100ac-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="100ac-104">Parameters</span></span>  
 <span data-ttu-id="100ac-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="100ac-105">cref = " `member`"</span></span>  
 <span data-ttu-id="100ac-106">現在のコンパイル環境から使用できる例外の参照。</span><span class="sxs-lookup"><span data-stu-id="100ac-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="100ac-107">コンパイラは、指定された例外が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="100ac-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="100ac-108">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="100ac-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="100ac-109">ジェネリック型への cref 参照を作成する方法については、[\<see>](../../../csharp/programming-guide/xmldoc/see.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="100ac-109">For more information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="100ac-110">例外の説明。</span><span class="sxs-lookup"><span data-stu-id="100ac-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="100ac-111">コメント</span><span class="sxs-lookup"><span data-stu-id="100ac-111">Remarks</span></span>  
 <span data-ttu-id="100ac-112">\<exception> タグを使用すると、スローできる例外を指定できます。</span><span class="sxs-lookup"><span data-stu-id="100ac-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="100ac-113">このタブは、メソッド、プロパティ、イベント、インデクサーの定義に適用できます。</span><span class="sxs-lookup"><span data-stu-id="100ac-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="100ac-114">コンパイル時に [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定してドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="100ac-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="100ac-115">例外処理の詳細については、「[例外と例外処理](../../../csharp/programming-guide/exceptions/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="100ac-115">For more information about exception handling, see [Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="100ac-116">例</span><span class="sxs-lookup"><span data-stu-id="100ac-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="100ac-117">参照</span><span class="sxs-lookup"><span data-stu-id="100ac-117">See Also</span></span>

- [<span data-ttu-id="100ac-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="100ac-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="100ac-119">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="100ac-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
