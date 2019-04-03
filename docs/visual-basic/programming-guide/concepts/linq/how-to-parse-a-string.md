---
title: '方法: (Visual Basic)、文字列を解析します。'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 815e94b3b41c2c0cc1d18d598307ab292919bea4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827303"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="b165c-102">方法: (Visual Basic)、文字列を解析します。</span><span class="sxs-lookup"><span data-stu-id="b165c-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="b165c-103">このトピックで XML ツリーを作成する方法を示しています。C#します。</span><span class="sxs-lookup"><span data-stu-id="b165c-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b165c-104">例</span><span class="sxs-lookup"><span data-stu-id="b165c-104">Example</span></span>  
 <span data-ttu-id="b165c-105">使用して Visual Basic で文字列を解析することができます、`XElement.Parse`メソッド。</span><span class="sxs-lookup"><span data-stu-id="b165c-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="b165c-106">ただし、次のコードに示すように XML リテラルを使用する方が効率的です。これは、XML リテラルでは、文字列から XML を解析する場合のようなパフォーマンスの低下がないためです。</span><span class="sxs-lookup"><span data-stu-id="b165c-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="b165c-107">XML リテラルを使用すると、だけコピーして、Visual Basic プログラムに、XML を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b165c-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b165c-108">テキストの解析やテキスト ファイルからの XML ドキュメントの読み込みは、関数型構築より非効率です。</span><span class="sxs-lookup"><span data-stu-id="b165c-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="b165c-109">XML ツリーをコードから初期化すると、関数型構築で必要となるプロセッサ時間は、テキストの解析に比べて短くなります。</span><span class="sxs-lookup"><span data-stu-id="b165c-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b165c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b165c-110">See also</span></span>

- [<span data-ttu-id="b165c-111">(Visual Basic) の XML の解析</span><span class="sxs-lookup"><span data-stu-id="b165c-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
