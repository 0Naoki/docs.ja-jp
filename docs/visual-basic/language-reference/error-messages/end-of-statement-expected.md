---
title: ステートメントの終わりを指定してください。
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: ab6a4a0e6736e2af9c1fa0dd170b6aa4c42d9e4a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817155"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="0d6c4-102">ステートメントの終わりを指定してください。</span><span class="sxs-lookup"><span data-stu-id="0d6c4-102">End of statement expected</span></span>
<span data-ttu-id="0d6c4-103">ステートメントが構文的に完了するが、その他のプログラミング要素に依存してステートメントを終了する要素。</span><span class="sxs-lookup"><span data-stu-id="0d6c4-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="0d6c4-104">行終端記号は、すべてのステートメントの末尾にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d6c4-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="0d6c4-105">行終端記号は、Visual Basic のソース ファイルの文字を行に分割します。</span><span class="sxs-lookup"><span data-stu-id="0d6c4-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="0d6c4-106">行ターミネータの例には、Unicode キャリッジ リターン文字 (& HD)、Unicode とライン フィード文字 (& HA)、および、Unicode 復帰文字の Unicode のラインフィード文字後にします。</span><span class="sxs-lookup"><span data-stu-id="0d6c4-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="0d6c4-107">行ターミネータの詳細については、次を参照してください。、 [Visual Basic 言語仕様](~/_vblang/spec/lexical-grammar.md#line-terminators)します。</span><span class="sxs-lookup"><span data-stu-id="0d6c4-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="0d6c4-108">**エラー ID:** BC30205</span><span class="sxs-lookup"><span data-stu-id="0d6c4-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0d6c4-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="0d6c4-109">To correct this error</span></span>
  
1.  <span data-ttu-id="0d6c4-110">2 つの異なるステートメントが同じ行に格納された誤ってかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d6c4-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2.  <span data-ttu-id="0d6c4-111">ステートメントを終了要素の後に行終端記号を挿入します。</span><span class="sxs-lookup"><span data-stu-id="0d6c4-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0d6c4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d6c4-112">See also</span></span>

- [<span data-ttu-id="0d6c4-113">方法: コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="0d6c4-113">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="0d6c4-114">ステートメント</span><span class="sxs-lookup"><span data-stu-id="0d6c4-114">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
