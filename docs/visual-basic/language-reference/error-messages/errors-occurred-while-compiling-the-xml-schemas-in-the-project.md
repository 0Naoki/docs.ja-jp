---
title: プロジェクトで、XML スキーマのコンパイル中にエラーが発生しました
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07233ed1c68f85878ffdd7131f64e30e158dc350
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>プロジェクトで、XML スキーマのコンパイル中にエラーが発生しました
プロジェクトで、XML スキーマのコンパイル中にエラーが発生しました。 このため、XML IntelliSense は使用できません。  
  
 プロジェクトに含まれる XML スキーマ定義 (XSD) スキーマでエラーがあります。 このエラーは、既存の XSD スキーマと競合していますが、プロジェクトに設定されている XSD スキーマ (.xsd) ファイルを追加するときに発生します。  
  
 **エラー ID:** BC36810  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   警告をダブルクリック、**エラー一覧**ウィンドウです。 Visual Basic では、警告のソースである XSD ファイルの場所を実行します。 XSD スキーマでエラーを修正します。  
  
-   必要なすべての XSD スキーマ (.xsd) ファイルがプロジェクトに含まれることを確認します。 をクリックする必要があります**すべてのファイル**上、**プロジェクト**にファイルを .xsd を表示するメニュー**ソリューション エクスプ ローラー**です。 .Xsd ファイルを右クリックし、をクリックして**プロジェクトに含める**プロジェクトのファイルをインクルードします。  
  
-   XML to Schema ウィザードを使用している場合、同じソースから複数回のスキーマを推論する場合にこのエラーが発生することができます。 スキーマ項目テンプレートに新しい XML がここでは、既存の XSD スキーマ ファイルを削除するには、プロジェクトから追加し、XML to Schema ウィザードに提供適用可能なすべての XML ソース プロジェクトのします。  
  
-   XSD スキーマでエラーを識別できない場合、XML コンパイラはエラー メッセージの詳細を提供するための十分な情報ことはできません。 場合に、プロジェクトの一致に含まれる .xsd ファイル用の XML 名前空間が、Visual Studio での XML スキーマで特定された XML 名前空間を使用することを確認する詳細なエラー情報を取得することができます。  
  
## <a name="see-also"></a>関連項目  
 [[エラー一覧] ウィンドウ](/visualstudio/ide/reference/error-list-window)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
