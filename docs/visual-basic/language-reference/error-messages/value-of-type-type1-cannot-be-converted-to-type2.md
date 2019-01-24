---
title: 型の値&#39;type1&#39;に変換できない&#39;type2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 657e0feb675e15b9ece00d40c3d1ebe932a29099
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568290"
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a><span data-ttu-id="a6deb-102">型の値&#39;type1&#39;に変換できない&#39;type2&#39;</span><span class="sxs-lookup"><span data-stu-id="a6deb-102">Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;</span></span>
<span data-ttu-id="a6deb-103">型 'type1' の値は、'type2' へ変換できません。</span><span class="sxs-lookup"><span data-stu-id="a6deb-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="a6deb-104">最初の要素の文字列値を取得する、'Value' プロパティを使用することができます '\<parentElement >'。</span><span class="sxs-lookup"><span data-stu-id="a6deb-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="a6deb-105">XML リテラルを特定の型を暗黙的にキャストしようとしました。</span><span class="sxs-lookup"><span data-stu-id="a6deb-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="a6deb-106">XML リテラルは、指定した型に暗黙的にキャストできません。</span><span class="sxs-lookup"><span data-stu-id="a6deb-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="a6deb-107">**エラー ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="a6deb-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a6deb-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="a6deb-108">To correct this error</span></span>  
  
-   <span data-ttu-id="a6deb-109">XML リテラルの `Value` プロパティを使用して、その値を `String`として参照します。</span><span class="sxs-lookup"><span data-stu-id="a6deb-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="a6deb-110">`CType` 関数、別の型変換関数、または <xref:System.Convert> クラスを使用して、指定した型として値をキャストします。</span><span class="sxs-lookup"><span data-stu-id="a6deb-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6deb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6deb-111">See also</span></span>
- <xref:System.Convert>
- [<span data-ttu-id="a6deb-112">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="a6deb-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="a6deb-113">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="a6deb-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="a6deb-114">XML</span><span class="sxs-lookup"><span data-stu-id="a6deb-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
