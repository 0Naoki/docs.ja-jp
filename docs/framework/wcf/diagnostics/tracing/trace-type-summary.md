---
title: トレースの種類の概要
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e3bc66753dd44e1dc4c7417caf593820300f69a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486043"
---
# <a name="trace-type-summary"></a>トレースの種類の概要
[Sourcelevels](http://go.microsoft.com/fwlink/?LinkID=94943)さまざまなトレース レベルを定義します。 重大なエラー、警告、情報、および Verbose も同様の説明、`ActivityTracing`の出力を切り替えるかをフラグは、境界とアクティビティ転送イベントをトレースします。  
  
 確認することも[TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169)から出力できるトレースの種類の<xref:System.Diagnostics>します。  
  
 最も重要な種類を次の表に示します。  
  
|トレースの種類|説明|  
|----------------|-----------------|  
|Critical|致命的なエラーまたはアプリケーションのクラッシュ。|  
|Error|回復可能なエラー。|  
|警告|情報メッセージ。|  
|情報|重大ではない問題。|  
|詳細|トレースのデバッグ。|  
|[開始]|処理の論理単位の開始。|  
|Suspend|処理の論理単位の中断。|  
|再開|処理の論理単位の再開。|  
|停止|処理の論理単位の停止。|  
|転送|相関 ID の変更。|  
  
 アクティビティは、上記のトレースの種類の組み合わせとして定義されます。  
  
 ローカル (トレース ソース) スコープでの典型的なアクティビティを定義する正規表現は次のとおりです。  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 これは、アクティビティが次の条件を満たす必要があることを意味します。  
  
-   アクティビティは、Start トレースによって開始し、Stop トレースによって停止する必要があります。  
  
-   Suspend トレースまたは Resume トレースの直前に Transfer トレースが必要です。  
  
-   Suspend トレースと Resume トレースが存在する場合、これらのトレースの間にトレースが存在することはできません。  
  
-   上記の条件を満たしている限り、Critical/Error/Warning/Information/Verbose/Transfer の各トレースはいくつでも含めることができます。  
  
 グローバル スコープでの典型的なアクティビティを定義する正規表現は次のとおりです。  
  
```  
R+   
```  
  
 R はローカル スコープのアクティビティを表す正規表現です。 これは、次のようになります。  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
