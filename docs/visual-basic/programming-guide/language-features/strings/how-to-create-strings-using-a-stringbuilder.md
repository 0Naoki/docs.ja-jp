---
title: '方法: Visual Basic では、StringBuilder を使用して文字列を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: dec1afdbd3ca6c0ba719a95906de8cf6fc7ba378
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738800"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>方法: Visual Basic では、StringBuilder を使用して文字列を作成します。
この例を使用して多数の小さな文字列から長い文字列を構築します、<xref:System.Text.StringBuilder>クラス。 <xref:System.Text.StringBuilder>クラスより効率的、`&=`演算子の多くの文字列を連結します。  
  
## <a name="example"></a>例  
 次の例のインスタンスを作成する、<xref:System.Text.StringBuilder>クラス、1,000 の文字列をそのインスタンスに追加し、その文字列表現を返します。  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>関連項目
- [StringBuilder クラスの使用](../../../../standard/base-types/stringbuilder.md)
- [& = 演算子](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [文字列](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [新しい文字列の作成](../../../../standard/base-types/creating-new.md)
- [文字列の操作](../../../../standard/base-types/manipulating-strings.md)
