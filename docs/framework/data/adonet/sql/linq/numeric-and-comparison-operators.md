---
title: 数値演算子および比較演算子
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: a7a455730860e2b11a5ceff5a70934502b312e19
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515067"
---
# <a name="numeric-and-comparison-operators"></a>数値演算子および比較演算子
算術演算子と比較演算子は、次の点を除いて、共通言語ランタイム (CLR) では期待どおりに動作します。  
  
-   SQL では、浮動小数点数に対して剰余演算子がサポートされません。  
  
-   SQL ではチェックされない算術はサポートされません。  
  
-   インクリメント演算子とデクリメント演算子は、SQL に複製できない式で使用すると副作用があるため、SQL ではサポートされません。  
  
## <a name="supported-operators"></a>サポートされる演算子  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、次の演算子をサポートしています。  
  
-   基本算術演算子  
  
    -   `+`  
  
    -   `-` (減算)  
  
    -   `*`  
  
    -   `/`  
  
    -   Visual Basic 整数除算 (`\`)  
  
    -   `%` (Visual Basic `Mod`)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` (単項マイナス符号)  
  
-   基本比較演算子  
  
    -   Visual Basic `=` および C# `==`  
  
    -   Visual Basic `<>` および C# `!=`  
  
    -   Visual Basic `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a>関連項目  
 [データ型と関数](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [C# 演算子](https://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [演算子](../../../../../visual-basic/language-reference/operators/index.md)
