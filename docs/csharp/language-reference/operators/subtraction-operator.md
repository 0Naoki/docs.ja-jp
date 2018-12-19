---
title: '- 演算子 - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 5a467e8383d7510260ad3044976601deca7cafdb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242231"
---
# <a name="--operator-c-reference"></a>- 演算子 (C# リファレンス)
`-` 演算子には、単項演算子としての働きと 2 項演算子としての働きとがあります。  
  
## <a name="remarks"></a>コメント  
 すべての数値型には、単項 `-` 演算子が事前定義されています。 数値型に対する単項 `-` 演算の結果は、オペランドの反転の数値となります。  
  
 最初のオペランドから 2 番目のオペランドを減算するために、すべての数値型と列挙型に 2 項 `-` 演算子が事前定義されています。  
  
 2 項 `-` 演算子はデリゲート型にも備わっており、その場合、デリゲートの削除が実行されます。  
  
 単項 `-` 演算子と 2 項 `-` 演算子は、ユーザー定義型でオーバーロードすることができます。 詳細については、「[operator (C# Reference) (operator (C# リファレンス))](../../../csharp/language-reference/keywords/operator.md)」を参照してください。  
  
## <a name="example"></a>例  
 [!code-csharp[csRefOperators#40](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-operator_1.cs)]  
  
## <a name="see-also"></a>参照

- [C# リファレンス](../../../csharp/language-reference/index.md)  
- [C# プログラミングガイド](../../../csharp/programming-guide/index.md)  
- [C# 演算子](../../../csharp/language-reference/operators/index.md)
