---
title: ネットワークのトレースの有効化
ms.date: 03/30/2017
helpviewer_keywords:
- trace destinations
- sending traces to log file
- trace listeners, network tracing
- network tracing, enabling
- CLR Debugger
- default listeners
- logs, trace
- destination for tracing output
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 56a24f93e92fbfbd2dbb1156a1c3ef786f59034e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="enabling-network-tracing"></a>ネットワークのトレースの有効化
ネットワークのトレースでは、メソッド呼び出しについての情報、およびマネージ アプリケーションによって生成されるネットワーク トラフィックについての情報にアクセスできます。 アプリケーションでネットワーク トレースを有効にするには、次のタスクを実行する必要があります。  
  
-   トレースを有効にしてコードをコンパイルします。 トレースを有効にするために必要なコンパイラ スイッチの詳細については、「[方法 : トレースとデバッグを指定して条件付きコンパイルを実行する](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)」を参照してください。  
  
-   トレースの出力先を指定します。  
  
-   ネットワークのトレースの動作を構成します。 詳細については、「[方法: ネットワークのトレースを構成する](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)」を参照してください。  
  
 最も一般的なトレース先 (トレース リスナーとも呼ばれます) は、既定のリスナーとログ ファイルです。  
  
 トレース リスナーを指定しない場合、トレースは既定のリスナーを使用します。 .NET Framework SDK に付属の CLR デバッガーや、Windows SDK に付属の DBwin32.exe などのマネージ コード対応のデバッガーでコードを実行することで、既定のリスナーに送信されたメッセージを表示することができます。 CLR デバッガーを使用すると、**[出力]** ウィンドウにトレース メッセージが表示されます。  
  
 ファイルを使用してトレースを受信する場合は、次の例のように、構成設定を使用して、ログ ファイルを指定できます  (構成ファイルに関する全般的な説明については、「[構成ファイル](../../../docs/framework/configure-apps/index.md)」を参照してください)。  
  
 トレースをログ ファイルに送信するには、次のノードを適切な (アプリケーションまたはコンピューターの) 構成ファイルの `<system.diagnostics>` ノードに追加します。 必要に応じてファイルの名前 (trace.log) を変更することができます。  
  
```xml  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## <a name="see-also"></a>参照  
 [ネットワークのトレースの解釈](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [.NET Framework のネットワークのトレース](../../../docs/framework/network-programming/network-tracing.md)  
 [実装とトレースの概要](http://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
