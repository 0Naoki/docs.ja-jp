---
title: == 演算子 (C# リファレンス)
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: d9d7dcf3b38939e681fb51d6c674151cee78b3d0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43421113"
---
# <a name="-operator-c-reference"></a>== 演算子 (C# リファレンス)
組み込みの値型の場合、等値演算子 (`==`) ではオペランドの値が等しい場合に true が返され、それ以外の場合は `false` が返されます。 [string](../../../csharp/language-reference/keywords/string.md) 以外の参照型の場合、`==` では 2 つのオペランドが同じオブジェクトを参照する場合に `true` が返されます。 `string` 型の場合は、`==` は文字列の値を比較します。  
  
## <a name="remarks"></a>コメント  
 ユーザー定義の値の型は `==` 演算子をオーバーロードできます (「[演算子](../../../csharp/language-reference/keywords/operator.md)」を参照)。 ユーザー定義参照型もオーバーロードはできますが、既定では、組み込み参照型とユーザー定義参照型のいずれに対しても `==` は前述のとおりに機能します。 `==` をオーバーロードする場合は、[!=](../../../csharp/language-reference/operators/not-equal-operator.md) もオーバーロードする必要があります。 整数型に対する演算は、通常、列挙型で使用できます。  
  
## <a name="example"></a>例  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>参照

- [C# リファレンス](../../../csharp/language-reference/index.md)  
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [C# 演算子](../../../csharp/language-reference/operators/index.md)
