---
title: '*= 演算子 (C# リファレンス)'
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: e47bc5c681c94ac3fc5c345c56b3814350ffa5ec
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517169"
---
# <a name="-operator-c-reference"></a>*= 演算子 (C# リファレンス)
二項乗算代入演算子です。  
  
## <a name="remarks"></a>コメント  
 次のような `*=` 代入演算子を使用する式があるとします  
  
```csharp  
x *= y  
```  
  
 上記の式は、次の式と同じです。  
  
```csharp  
x = x * y  
```  
  
 ただし、`x` が評価されるのは 1 回だけです。 [* 演算子](../../../csharp/language-reference/operators/multiplication-operator.md)は、数値型の乗算のために事前定義されています。  
  
 `*=` 演算子は直接オーバーロードできませんが、ユーザー定義型は [* 演算子](../../../csharp/language-reference/operators/multiplication-operator.md)をオーバーロードできます (「[operator](../../../csharp/language-reference/keywords/operator.md)」参照)。  
  
## <a name="example"></a>例  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>参照

- [C# リファレンス](../../../csharp/language-reference/index.md)  
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [C# 演算子](../../../csharp/language-reference/operators/index.md)
