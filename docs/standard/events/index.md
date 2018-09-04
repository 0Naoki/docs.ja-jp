---
title: イベントの処理と発生
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- delegate model for events
- application development [.NET Framework], events
- events [.NET Framework]
ms.assetid: b6f65241-e0ad-4590-a99f-200ce741bb1f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 623700161ae4587daeb2c7348055d413512f7c87
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43538709"
---
# <a name="handling-and-raising-events"></a>イベントの処理と発生
.NET Framework でのイベントは、デリゲート モデルに基づいています。 デリゲート モデルはオブザーバー デザイン パターンに従って、サブスクライバーがプロバイダーに登録して通知を受信できるようにします。 イベントの送信元がイベント発生の通知をプッシュしたら、イベント レシーバーはその通知を受信して、通知に対する応答を定義します。 ここでは、デリゲート モデルの主要コンポーネント、アプリケーションでイベントを利用する方法、およびコードでイベントを実装する方法について説明します。  
  
 Windows 8.x ストア アプリでのイベントの処理については、「[Events and routed events overview](https://docs.microsoft.com/previous-versions/windows/apps/hh758286(v=win.10))」(イベントとルーティング イベントの概要) を参照してください。  
  
## <a name="events"></a>イベント  
 イベントは、アクションの発生を知らせるために、オブジェクトによって送信されるメッセージです。 アクションは、ユーザーがボタンのクリックなどの対話的操作を行った場合や、プロパティの値の変更など、なんらかのプログラム ロジックによって発生します。 イベントを発生させるオブジェクトを "*イベントの送信元*" と呼びます。 イベントの送信元は、発生させたイベントをどのオブジェクトまたはメソッドが受信する (処理する) かについての情報を持っていません。 このイベントはイベントの送信元のメンバーです。たとえば、<xref:System.Web.UI.WebControls.Button.Click> イベントは <xref:System.Web.UI.WebControls.Button> クラスのメンバーであり、<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> イベントは <xref:System.ComponentModel.INotifyPropertyChanged> インターフェイスを実装するクラスのメンバーです。  
  
 イベントを定義するには、イベント クラスのシグネチャで `event` (C# の場合) または `Event` (Visual Basic の場合) のキーワードを使用し、イベントにデリゲートの型を指定します。 デリゲートについては、次のセクションで説明します。  
  
 通常、イベントを発生させるには、`protected` や `virtual` (C# の場合)、または `Protected` や `Overridable` (Visual Basic の場合) としてマークされたメソッドを追加します。 このメソッドには `On`*EventName* の形式で名前を付けます (`OnDataReceived` など)。 また、イベント データ オブジェクトを指定するパラメーターを 1 つ指定する必要があります。 このメソッドを指定すると、イベントを発生させるためのロジックを派生クラスでオーバーライドできます。 派生クラスは常に基底クラスの `On`*EventName* メソッドを呼び出して、登録されたデリゲートがイベントを必ず受信できるようにします。  
  
 次の例は、`ThresholdReached` という名前のイベントを宣言する方法を示しています。 イベントは <xref:System.EventHandler> デリゲートに関連付けられ、`OnThresholdReached` という名前のメソッドで発生します。  
  
 [!code-csharp[EventsOverview#1](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#1)]
 [!code-vb[EventsOverview#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#1)]  
  
## <a name="delegates"></a>デリゲート  
 デリゲートは、メソッドへの参照を保持する型です。 デリゲートは、自身が参照するメソッドの戻り値とパラメーターを表示するシグネチャで宣言され、このシグネチャに一致するメソッドへの参照だけを保持できます。 これにより、デリゲートはタイプ セーフな関数ポインターやコールバックと同等の機能を持つことができます。 デリゲート クラスは、宣言すると、定義は不要です。  
  
 .NET Framework でのデリゲートの用途は多数あります。 イベントのコンテキストでは、デリゲートは、イベント ソースとイベントを処理するコードの間を仲介するもの、つまりポインター的な機構です。 デリゲートをイベントに関連付けるには、デリゲート型をイベント宣言に追加します。 デリゲートの詳細については、「<xref:System.Delegate> クラス」を参照してください。  
  
 .NET Framework には <xref:System.EventHandler> デリゲートおよび <xref:System.EventHandler%601> デリゲートが用意されており、ほとんどのイベント シナリオがサポートされます。 <xref:System.EventHandler> デリゲートは、イベント データを含まないすべてのイベントに対して使用します。 <xref:System.EventHandler%601> デリゲートは、イベントに関するデータを含むイベントに使用します。 これらのデリゲートには戻り値の型の値がなく、2 つのパラメーター (イベント ソース用オブジェクトとイベント データ用オブジェクト) を受け取ります。  
  
 デリゲートはマルチキャストであるため、複数のイベント処理メソッドへの参照を保持できます。 詳細については、<xref:System.Delegate> のリファレンス ページを参照してください。 デリゲートでは、イベント処理を柔軟に、そして詳細に制御できます。 デリゲートは、イベントに対して登録されているイベント ハンドラーのリストを管理することで、そのイベントを発生させるクラスのイベント ディスパッチャーとして動作します。  
  
 <xref:System.EventHandler> デリゲートおよび <xref:System.EventHandler%601> デリゲートが動作しないシナリオについては、デリゲートを定義できます。 デリゲートの定義が必要なシナリオは非常にまれで、たとえば、ジェネリックを認識しないコードを使用する必要がある場合などです。 デリゲートには、宣言内で `delegate` キーワード (C# の場合) および `Delegate` キーワード (Visual Basic の場合) を使用してマークします。 次の例は、`ThresholdReachedEventHandler` という名前のデリゲートを宣言する方法を示しています。  
  
 [!code-csharp[EventsOverview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#4)]
 [!code-vb[EventsOverview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#4)]  
  
## <a name="event-data"></a>イベント データ  
 イベントに関連付けられたデータは、イベント データ クラスを使用して提供できます。 .NET Framework には、アプリケーションで使用できるイベント データ クラスが多数用意されています。 たとえば、<xref:System.IO.Ports.SerialDataReceivedEventArgs> クラスは、<xref:System.IO.Ports.SerialPort.DataReceived?displayProperty=nameWithType> イベントのイベント データ クラスです。 .NET Framework の名前付けパターンでは、すべてのイベント データ クラス名の末尾に `EventArgs` が付きます。 イベントに関連付けられているイベント データ クラスは、そのイベントのデリゲートを見ればわかります。 たとえば、<xref:System.IO.Ports.SerialDataReceivedEventHandler> デリゲートには、パラメーターの 1 つとして <xref:System.IO.Ports.SerialDataReceivedEventArgs> クラスが含まれます。  
  
 <xref:System.EventArgs> は、すべてのイベント データ クラスの基本型です。 また、<xref:System.EventArgs> は、イベントにデータが関連付けられていないときに使用するクラスでもあります。 何かが発生したことを他のクラスに通知することのみが目的のイベント、つまり、データの受け渡しを必要としないイベントを作成する場合は、デリゲートの 2 番目のパラメーターとして <xref:System.EventArgs> クラスを追加します。 データが指定されていない場合は、<xref:System.EventArgs.Empty?displayProperty=nameWithType> 値を渡すことができます。 <xref:System.EventHandler> デリゲートには、パラメーターとして <xref:System.EventArgs> クラスが含まれます。  
  
 カスタマイズされたイベント データ クラスを作成する場合は、<xref:System.EventArgs>から派生したクラスを作成し、イベントに関連するデータを渡すのに必要なメンバーを指定します。 通常は、.NET Framework と同じ名前付けパターンを使用する必要があり、イベント データ クラス名の末尾には `EventArgs` が付きます。  
  
 次の例は、`ThresholdReachedEventArgs` という名前のイベント データを示しています。 これには、発生したイベントに応じた特定のプロパティが含まれます。  
  
 [!code-csharp[EventsOverview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#3)]
 [!code-vb[EventsOverview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#3)]  
  
## <a name="event-handlers"></a>イベント ハンドラー  
 イベントに応答するには、イベント レシーバーのイベント ハンドラー メソッドを定義します。 このメソッドは、処理するイベントのデリゲートのシグネチャと一致する必要があります。 イベント ハンドラーでは、ユーザーがボタンをクリックしたときにユーザー入力を収集するなど、イベントが発生したときに必要なアクションを実行します。 イベントが発生したときに通知を受け取るには、イベント ハンドラー メソッドがイベントをサブスクライブする必要があります。  
  
 次の例は、`c_ThresholdReached` デリゲートのシグネチャと一致する、<xref:System.EventHandler> という名前のイベント ハンドラー メソッドを示しています。 メソッドは、`ThresholdReached` イベントをサブスクライブします。  
  
 [!code-csharp[EventsOverview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#2)]
 [!code-vb[EventsOverview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#2)]  
  
## <a name="static-and-dynamic-event-handlers"></a>静的イベント ハンドラーと動的イベント ハンドラー  
 .NET Framework を使用すると、静的または動的にイベント通知のためのサブスクライバーを登録できます。 静的なイベント ハンドラーは、処理対象のイベントのクラスの有効期間にわたって有効になります。 動的なイベント ハンドラーは、プログラムの実行中、通常は条件付きのプログラム ロジックに応答する形で、明示的にアクティブ化または非アクティブ化されます。 たとえば、特定の条件下でのみイベント通知が必要な場合や、複数のイベント ハンドラーを持つアプリケーションで、実行時の条件に応じて適切なハンドラーを決定する場合などに使用できます。 前のセクションの例は、イベント ハンドラーを動的に追加する方法を示しています。 詳細については、「[イベント](../../visual-basic/programming-guide/language-features/events/index.md)」および「[イベント](../../csharp/programming-guide/events/index.md)」を参照してください。  
  
## <a name="raising-multiple-events"></a>複数のイベントの発生  
 クラスで複数のイベントを発生させる場合、コンパイラでは、イベント デリゲートのインスタンスごとに 1 つのフィールドが生成されます。 イベントの数が多い場合は、デリゲート 1 つあたり 1 フィールドというストレージ コストが許容されない可能性があります。 このような状況に備えて、.NET Framework には、イベント デリゲートを格納するために任意に選択した別のデータ構造と一緒に使用できる、イベント プロパティが用意されています。  
  
 イベント プロパティは、イベント アクセサーを伴うイベント宣言によって構成されます。 イベント アクセサーは、ストレージ データ構造におけるイベント デリゲート インスタンスの追加または削除を定義するメソッドです。 イベント プロパティを使用すると、イベント プロパティは各イベント デリゲートを呼び出す前に取得する必要があるので、イベント フィールドよりも低速です。 つまり、メモリを取るか、速度を取るかの比較検討になります。 クラスで、発生頻度の低いイベントを数多く定義する場合は、イベント プロパティを実装することをお勧めします。 詳細については、「[方法 : イベント プロパティを使用して複数のイベントを処理する](../../../docs/standard/events/how-to-handle-multiple-events-using-event-properties.md)」を参照してください。  
  
## <a name="related-topics"></a>関連トピック  
  
|Title|説明|  
|-----------|-----------------|  
|[方法 : イベントを発生させる/処理する](../../../docs/standard/events/how-to-raise-and-consume-events.md)|イベントの発生例と実装例が含まれます。|  
|[方法 : イベント プロパティを使用して複数のイベントを処理する](../../../docs/standard/events/how-to-handle-multiple-events-using-event-properties.md)|イベント プロパティを使用して複数のイベントを処理する方法を示します。|  
|[オブサーバー デザイン パターン](../../../docs/standard/events/observer-design-pattern.md)|サブスクライバーがプロバイダーに登録して、通知を受信できるようにするデザイン パターンについて説明します。|  
|[方法 : Web フォーム アプリケーションでイベントを利用する](../../../docs/standard/events/how-to-consume-events-in-a-web-forms-application.md)|Web フォーム コントロールによって発生したイベントを処理する方法を示します。|  
  
## <a name="see-also"></a>参照  
 <xref:System.EventHandler>  
 <xref:System.EventHandler%601>  
 <xref:System.EventArgs>  
 <xref:System.Delegate>  
 [イベントとルーティング イベントの概要 (UWP アプリ)](/windows/uwp/xaml-platform/events-and-routed-events-overview)  
 [イベント (Visual Basic)](../../visual-basic/programming-guide/language-features/events/index.md)  
 [イベント (C# プログラミング ガイド)](../../csharp/programming-guide/events/index.md)
