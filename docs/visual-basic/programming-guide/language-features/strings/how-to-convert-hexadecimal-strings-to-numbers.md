---
title: '方法: 16 進文字列を数値に変換する (Visual Basic)'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: 65184bbb742ad549a8398d55dc7bdeed05a9d973
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197550"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="4d7ab-102">方法: 16 進文字列を数値に変換する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d7ab-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="4d7ab-103">この例では、16 進数の文字列に変換を使用して、整数、<xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="4d7ab-104">16 進数の文字列を数値に変換するには</span><span class="sxs-lookup"><span data-stu-id="4d7ab-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="4d7ab-105">使用して、<xref:System.Convert.ToInt32(System.String,System.Int32)>ベース-16 を整数で表された数値に変換します。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="4d7ab-106">最初の引数、<xref:System.Convert.ToInt32(System.String,System.Int32)>メソッドは変換する文字列。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="4d7ab-107">2 番目の引数には、どの基本; で表現されるは、数値がについて説明します16 進数が 16 進です。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- <span data-ttu-id="4d7ab-108">16 進数の文字列に、次の制限に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="4d7ab-109">含めることはできません、`&h`プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="4d7ab-110">含めることはできません、`_`桁区切り記号。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="4d7ab-111">プレフィックスまたは桁区切り記号が存在する場合、呼び出し、<xref:System.Convert.ToInt32(System.String,System.Int32)>メソッドがスローされます、<xref:System.FormatException>します。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d7ab-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d7ab-112">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
