---
title: XML リテラルおよび XML プロパティは、ASP.NET 内の埋め込みコードではサポートされません
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 79be695478983055ae1f016cf841d733d3f4c430
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813926"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="bce86-102">XML リテラルおよび XML プロパティは、ASP.NET 内の埋め込みコードではサポートされません</span><span class="sxs-lookup"><span data-stu-id="bce86-102">XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>
<span data-ttu-id="bce86-103">ASP.NET 内の埋め込みコードでは、XML リテラルおよび XML プロパティがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bce86-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="bce86-104">XML の機能を使用するには、分離コードにコードを移動します。</span><span class="sxs-lookup"><span data-stu-id="bce86-104">To use XML features, move the code to code-behind.</span></span>  
  
 <span data-ttu-id="bce86-105">埋め込みコード内で、XML リテラルまたは XML 軸プロパティが定義されている (`<%= =>`) で、ASP.NET ファイル。</span><span class="sxs-lookup"><span data-stu-id="bce86-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>  
  
 <span data-ttu-id="bce86-106">**エラー ID:** BC31200</span><span class="sxs-lookup"><span data-stu-id="bce86-106">**Error ID:** BC31200</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bce86-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="bce86-107">To correct this error</span></span>  
  
-   <span data-ttu-id="bce86-108">ASP.NET 分離コード ファイルにコードを含む XML リテラルまたは XML 軸プロパティを移動します。</span><span class="sxs-lookup"><span data-stu-id="bce86-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce86-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="bce86-109">See also</span></span>

- [<span data-ttu-id="bce86-110">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="bce86-110">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="bce86-111">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="bce86-111">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="bce86-112">XML</span><span class="sxs-lookup"><span data-stu-id="bce86-112">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
