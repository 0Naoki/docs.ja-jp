---
title: '&lt;例外&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 047805ad91d87550da80448fd10883ae58647bd6
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881331"
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="e22c9-102">&lt;例外&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e22c9-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="e22c9-103">どの例外がスローされる可能性を指定します。</span><span class="sxs-lookup"><span data-stu-id="e22c9-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e22c9-104">構文</span><span class="sxs-lookup"><span data-stu-id="e22c9-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e22c9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e22c9-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="e22c9-106">現在のコンパイル環境から使用できる例外の参照。</span><span class="sxs-lookup"><span data-stu-id="e22c9-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="e22c9-107">コンパイラは、指定された例外が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e22c9-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="e22c9-108">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e22c9-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="e22c9-109">説明です。</span><span class="sxs-lookup"><span data-stu-id="e22c9-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e22c9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="e22c9-110">Remarks</span></span>  
 <span data-ttu-id="e22c9-111">使用して、`<exception>`タグをどの例外をスローすることができますを指定します。</span><span class="sxs-lookup"><span data-stu-id="e22c9-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="e22c9-112">このタグは、メソッドの定義に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e22c9-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="e22c9-113">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="e22c9-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e22c9-114">例</span><span class="sxs-lookup"><span data-stu-id="e22c9-114">Example</span></span>  
 <span data-ttu-id="e22c9-115">この例では、`<exception>`例外を記述するタグを`IntDivide`関数はスローできます。</span><span class="sxs-lookup"><span data-stu-id="e22c9-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e22c9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e22c9-116">See Also</span></span>  
 [<span data-ttu-id="e22c9-117">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="e22c9-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
