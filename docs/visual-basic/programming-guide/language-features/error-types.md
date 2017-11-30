---
title: "エラーの種類 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e01ed588d284a475a537a5fcf5ca506d25ca69f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="error-types-visual-basic"></a>エラーの種類 (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]、エラー (とも呼ばれます*例外*) は 3 つのカテゴリに分類されます。 構文エラー、実行時エラー、および論理エラー。  
  
## <a name="syntax-errors"></a>構文エラー  
 *構文エラー*コードを記述するときに表示されることです。 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]入力すると、コードを確認、**コード エディター**ウィンドウを間違えた、単語のスペルが間違ってなどの言語要素を使用して不適切な場合、アラートが生成されます。 構文エラーは、エラーの最も一般的な種類です。 簡単に修正できますコーディングの環境で発生するとすぐにします。  
  
> [!NOTE]
>  `Option Explicit`ステートメントは構文エラーを回避する 1 つのことを意味します。 アプリケーションで使用するすべての変数を事前に宣言するように強制します。 したがって、コードでそれらの変数を使用している場合、入力ミスはすぐに検出され、修正することができます。  
  
## <a name="run-time-errors"></a>実行時エラー  
 *実行時エラー*コンパイルして、コードの実行後にのみ表示されることです。 これらには、構文エラーがないのに実行できない点で、正しいように表示されるコードが含まれます。 たとえば、ファイルを開くためのコードの行を正しく記述可能性があります。 ファイルが破損している場合、アプリケーションを実行できませんが、`Open`関数、およびが実行を停止します。 ほとんどの実行時エラーを修正するには、欠陥のあるコードの再書き換えを再コンパイルし、再実行することによってです。  
  
## <a name="logic-errors"></a>論理エラー  
 *論理エラー*アプリケーションは使用中に表示されることです。 これらは、ユーザーの操作への応答でほとんどの多くの場合、不要なまたは予期しない結果です。 たとえば、入力の間違いキーまたはその他の外部の影響を与えることがあります、アプリケーションで必要なパラメーターは、内での作業を停止するなったりします。 論理エラーは、通常、最も困難な型ではないため常に明確ではないを修正します。  
  
## <a name="see-also"></a>関連項目  
 [Try...Catch...Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [デバッガーの基本事項](/visualstudio/debugger/debugger-basics)
