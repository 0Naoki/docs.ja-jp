---
title: "値型パラメーターの引き渡し (C# プログラミング ガイド)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 08a336e9aa34ac3ce5bb8848df533caa563972f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="passing-value-type-parameters-c-programming-guide"></a>値型パラメーターの引き渡し (C# プログラミング ガイド)
データへの参照を含む[参照型](../../../csharp/language-reference/keywords/reference-types.md)変数とは対照的に、[値型](../../../csharp/language-reference/keywords/value-types.md)変数にはデータが直接含まれます。 値型変数を値渡しでメソッドに渡すと、変数のコピーがメソッドに渡されます。 メソッド内部で生じるパラメーターに対する変更の影響は、引数の変数に格納されている元のデータには及びません。 呼び出したメソッドでパラメーターの値を変更する場合は、[ref](../../../csharp/language-reference/keywords/ref.md) キーワードまたは [out](../../../csharp/language-reference/keywords/out.md) キーワードを使用して、参照渡しでそのメソッドを渡す必要があります。 わかりやすくするために、次の例では `ref` を使用しています。  
  
## <a name="passing-value-types-by-value"></a>値渡しによる値型の引き渡し  
 次の例では、値型のパラメーターを値渡しで渡す方法について説明します。 変数 `n` を、値渡しでメソッド `SquareIt` に渡します。 メソッド内で生じた変更が、変数の元の値に影響することはありません。  
  
 [!code-csharp[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]  
  
 変数 `n` は値型です。 この変数には、そのデータである値 `5` が含まれます。 `SquareIt` を呼び出すと、`n` の内容がパラメーター `x` にコピーされ、このパラメーターがメソッド内で 2 乗されます。 ただし、`Main` 内の `n` の値は、`SquareIt` メソッドを呼び出した後でも以前の値と同じままです。 メソッド内で生じた変更の影響は、ローカル変数 `x` にのみ及びます。  
  
## <a name="passing-value-types-by-reference"></a>参照渡しによる値型の引き渡し  
 次の例は、`ref` パラメーターとして引数を渡す点を除いて上記の例と同じです。 基になる引数 `n` の値は、メソッド内で `x` が変更されると変わります。  
  
 [!code-csharp[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]  
  
 この例では、`n` の値が渡されるのではなく、`n` への参照が渡されています。 つまり、パラメーター `x` は [int](../../../csharp/language-reference/keywords/int.md) ではなく、`int` への参照 (この場合は `n` への参照) となります。 したがって、メソッド内で `x` が 2 乗された場合、`x` の参照先である `n` が実際に2乗されます。  
  
## <a name="swapping-value-types"></a>値型のスワップ  
 引数の値を変更する一般的な例としてスワップ メソッドがあります。この方法では、2 つの変数をメソッドに渡してから、メソッドにより変数の中身を交換します。 スワップ メソッドへの引数の引き渡しは、参照渡しで行う必要があります。 このようにしないと、メソッド内でパラメーターのローカル コピーどうしが交換され、呼び出し元のメソッドでは変更が行われません。 次の例では、整数値が入れ替えられます。  
  
 [!code-csharp[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]  
  
 `SwapByRef` メソッドを呼び出す場合は、次の例に示すように呼び出しで `ref` キーワードを使用します。  
  
 [!code-csharp[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]  
  
## <a name="see-also"></a>関連項目  
 [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
 [パラメーターの引き渡し](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
 [参照型パラメーターの引き渡し](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)
