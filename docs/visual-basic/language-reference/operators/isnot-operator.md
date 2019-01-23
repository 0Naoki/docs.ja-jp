---
title: IsNot 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ffafff915af8a94e9bc135246064e4c049d41838
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596463"
---
# <a name="isnot-operator-visual-basic"></a>IsNot 演算子 (Visual Basic)
2 つのオブジェクト参照変数を比較します。  
  
## <a name="syntax"></a>構文  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>指定項目  
 `result`  
 必須。 `Boolean` 値。  
  
 `object1`  
 必須。 すべて`Object`変数または式。  
  
 `object2`  
 必須。 すべて`Object`変数または式。  
  
## <a name="remarks"></a>Remarks  
 `IsNot`演算子が 2 つのオブジェクト参照が別のオブジェクトを参照してかどうかを決定します。 ただし、値の比較は実行されません。 場合`object1`と`object2`両方には、まったく同じオブジェクト インスタンスを参照してください`result`は`False`; が存在しない場合、`result`は`True`します。  
  
 `IsNot` 反対、`Is`演算子。 利点は、`IsNot`で不適切な構文を回避できることは、`Not`と`Is`、読みにくくなることができます。  
  
 使用することができます、`Is`と`IsNot`事前バインディングと遅延バインディングの両方のオブジェクトをテストする演算子。  
  
> [!NOTE]
>  `IsNot`から返される式を比較する演算子を使用することはできません、`TypeOf`演算子。 代わりに、使用する必要があります、`Not`と`Is`演算子。  
  
## <a name="example"></a>例  
 次のコード例では、両方は使用して、`Is`演算子と`IsNot`同じ比較演算子。  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a>関連項目
- [Is 演算子](../../../visual-basic/language-reference/operators/is-operator.md)
- [TypeOf 演算子](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Visual Basic における演算子の優先順位](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [方法: 2 つのオブジェクトが等しいかどうかをテストします。](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
