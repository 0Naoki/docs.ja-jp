---
title: 定数は、class、structure、型パラメーター、または array 型ではなく、組み込み型または列挙型でなければなりません。
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 4d635d289ed99aed48c296c278bc546971af51da
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083923"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>定数は、class、structure、型パラメーター、または array 型ではなく、組み込み型または列挙型でなければなりません。
クラス、構造体、または配列型、またはそれを含むジェネリック型で定義された型パラメーターと定数を宣言しようとしました。  
  
 組み込み型の定数があります (`Boolean`、 `Byte`、 `Date`、 `Decimal`、 `Double`、 `Integer`、 `Long`、 `Object`、 `SByte`、 `Short`、 `Single`、 `String`、 `UInteger`、 `ULong`、または`UShort`)、または`Enum`型が整数型のいずれかに基づきます。  
  
 **エラー ID:** BC30424  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  組み込み関数として定数を宣言または`Enum`型。  
  
2.  定数にはまた、特殊な値など`True`、 `False`、または`Nothing`します。 コンパイラでは、これらの定義済み値の適切な組み込み型と見なします。  
  
## <a name="see-also"></a>関連項目  
 [定数と列挙体](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [データの種類](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [データの種類](../../../visual-basic/language-reference/data-types/index.md)
