---
title: '方法: 値 (Visual Basic) を返すプロシージャを作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 18becfe05da27e538c5c294b26e0bb7aa19cad2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506421"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>方法: 値 (Visual Basic) を返すプロシージャを作成します。
使用する、`Function`プロシージャを呼び出し元のコードに値を返します。  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>値を返すプロシージャを作成するには  
  
1.  その他のプロシージャの外側を使用して、`Function`ステートメントの後に、`End Function`ステートメント。  
  
2.  `Function`ステートメントでは、以下の`Function`キーワード、プロシージャとし、パラメーター リストをかっこでの名前に置き換えます。  
  
3.  かっこの後に、`As`句を戻り値のデータ型を指定します。  
  
4.  間のプロシージャのコード ステートメントを配置、`Function`と`End Function`ステートメント。  
  
5.  使用して、`Return`ステートメントを呼び出し元のコードに値を返します。  
  
     次`Function`プロシージャは、最長の辺またはの他の 2 つの辺の値を指定された直角三角形の斜辺を計算します。  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     次の例では、一般的な呼び出しを`hypotenuse`します。  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a>関連項目
- [プロシージャ](./index.md)
- [Sub プロシージャ](./sub-procedures.md)
- [Property プロシージャ](./property-procedures.md)
- [演算子プロシージャ](./operator-procedures.md)
- [プロシージャのパラメーターと引数](./procedure-parameters-and-arguments.md)
- [Function ステートメント](../../../../visual-basic/language-reference/statements/function-statement.md)
- [方法: プロシージャから値を返す](./how-to-return-a-value-from-a-procedure.md)
- [方法: 値を返すプロシージャを呼び出す](./how-to-call-a-procedure-that-returns-a-value.md)
