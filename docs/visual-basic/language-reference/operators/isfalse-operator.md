---
title: IsFalse 演算子 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d85fc51a75f82c65cf226b8239a8eee6585bd18a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse 演算子 (Visual Basic)
式は、かどうかを判断`False`です。  
  
 呼び出すことはできません`IsFalse`明示的に、コードが、Visual Basic のコンパイラが使用できるからコードを生成する`AndAlso`句。 クラスまたは構造体を定義しでその型の変数を使用する場合、`AndAlso`を定義する必要があります句、`IsFalse`そのクラスまたは構造にします。  
  
 コンパイラは、`IsFalse`と`IsTrue`演算子として、*ペア*です。 つまり、それらのいずれかを定義する場合をする必要がありますも定義、もう 1 つです。  
  
> [!NOTE]
>  `IsFalse`演算子を指定できます*オーバー ロードされた*、いるクラスまたは構造体を再定義できますその動作のオペランドは、そのクラスまたは構造体の型を持つときにすることを意味します。 コードは、このようなクラスまたは構造体で、この演算子を使用する場合は、再定義された動作を理解することを確認します。 詳細については、次を参照してください。[演算子プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)です。  
  
## <a name="example"></a>例  
 次のコード例の定義を含む構造体の輪郭の定義、`IsFalse`と`IsTrue`演算子。  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a>関連項目  
 [IsTrue 演算子](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [方法 : 演算子を定義する](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [AndAlso 演算子](../../../visual-basic/language-reference/operators/andalso-operator.md)
