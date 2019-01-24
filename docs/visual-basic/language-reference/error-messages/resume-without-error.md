---
title: エラーが発生していないときに Resume を実行することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 55295997e5e534b091063815d5ad1a37b81638ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686622"
---
# <a name="resume-without-error"></a>エラーが発生していないときに Resume を実行することはできません。
A`Resume`ステートメントが外部のエラー処理コードを表示またはエラーがなかった場合でも、コードがエラー ハンドラーにジャンプします。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  移動、`Resume`ステートメント エラー ハンドラーを削除したりします。  
  
2.  エラー ハンドラーを識別するラベルのプロシージャに、検索をラベルにジャンプは、プロシージャ間で発生することはできません。 対象として指定された重複するラベルを検索する場合、`GoTo`ステートメントではなく、`On Error GoTo`ステートメントでは、目的のターゲットと一致する行のラベルを変更します。  
  
## <a name="see-also"></a>関連項目
- [Resume ステートメント](../../../visual-basic/language-reference/statements/resume-statement.md)
- [On Error ステートメント](../../../visual-basic/language-reference/statements/on-error-statement.md)
