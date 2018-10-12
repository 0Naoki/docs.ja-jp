---
title: RemoveHandler ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: c1e6ffec64bc01936955a2e94aa9c110b317109f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925167"
---
# <a name="removehandler-statement"></a>RemoveHandler ステートメント
イベントとイベント ハンドラー間の関連付けを削除します。  
  
## <a name="syntax"></a>構文  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>指定項目  
  
|用語|定義|  
|---|---|  
|`event`|処理されるイベントの名前。|  
|`eventhandler`|現在、イベントを処理するプロシージャの名前。|  
  
## <a name="remarks"></a>Remarks  
 `AddHandler`と`RemoveHandler`ステートメントでは、開始およびプログラムの実行中にいつでも、特定のイベントのイベント処理を停止することができます。  
  
> [!NOTE]
>  カスタム イベントの場合、`RemoveHandler`ステートメントで呼び出されるイベントの`RemoveHandler`アクセサー。 カスタム イベントの詳細については、次を参照してください。 [Event ステートメント](../../../visual-basic/language-reference/statements/event-statement.md)します。  
  
## <a name="example"></a>例  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a>関連項目  
 [AddHandler ステートメント](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event ステートメント](../../../visual-basic/language-reference/statements/event-statement.md)  
 [イベント](../../../visual-basic/programming-guide/language-features/events/index.md)
