---
title: Erase ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 7dec2a859f664ee8dcbb305082ec33aeacbaccb4
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583384"
---
# <a name="erase-statement-visual-basic"></a>Erase ステートメント (Visual Basic)
配列変数を解放し、それらの要素に使用されるメモリの割り当てを解除するために使用されます。  
  
## <a name="syntax"></a>構文  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>指定項目  
 `arraylist`  
 必須です。 消去する配列変数の一覧。 複数の変数を指定するときは、コンマで区切ります。  
  
## <a name="remarks"></a>Remarks  
 @No__t_0 ステートメントは、プロシージャレベルでのみ使用できます。 これは、プロシージャ内では、クラスレベルまたはモジュールレベルではなく、配列を解放できることを意味します。  
  
 @No__t_0 ステートメントは、各配列変数に `Nothing` を割り当てることと同じです。  
  
## <a name="example"></a>例  
 次の例では、`Erase` ステートメントを使用して2つの配列をクリアし、メモリ (それぞれ1000と100のストレージ要素) を解放します。 次に、`ReDim` ステートメントによって、3次元配列に新しい配列インスタンスが割り当てられます。  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>関連項目

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim ステートメント](../../../visual-basic/language-reference/statements/redim-statement.md)
