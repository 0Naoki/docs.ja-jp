---
title: "同期クライアント ソケットの使用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- synchronous client sockets
- Socket class, synchronous client sockets
- receiving data, sockets
- sockets, synchronous client sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 03595539d825f26251a24fce33ede2552b79b38b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-synchronous-client-socket"></a>同期クライアント ソケットの使用
ネットワーク操作が完了するまで、同期クライアント ソケットはアプリケーション プログラムを一時停止させます。 同期ソケットは動作のためにネットワークを多用するアプリケーションには適しませんが、それ以外のアプリケーションの場合、ネットワーク サービスへの簡単アクセスを可能にします。  
  
 データを送信するには、<xref:System.Net.Sockets.Socket> クラスのデータ送信メソッド (<xref:System.Net.Sockets.Socket.Send%2A> と <xref:System.Net.Sockets.Socket.SendTo%2A>) のいずれかにバイト配列を渡します。 次の例では、<xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> プロパティを利用してバイト配列バッファーに文字列をエンコードし、**Send** メソッドを利用してネットワーク デバイスにバッファーを送信しています。 **Send** メソッドは、ネットワーク デバイスに送信されたバイトの数を返します。  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 **Send** メソッドは、バッファーからバイトを取り除き、ネットワーク インターフェイスで、ネットワーク デバイスに送信するための待ち行列に入れます。 ネットワーク インターフェイスはデータをすぐには送信しないかもしれませんが、<xref:System.Net.Sockets.Socket.Shutdown%2A> メソッドで接続が通常どおり閉じられる限り、いずれは送信します。  
  
 ネットワーク デバイスからデータを受け取るには、**Socket** クラスのデータ受信メソッド (<xref:System.Net.Sockets.Socket.Receive%2A> と <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>) のいずれかにバッファーを渡します。 同期ソケットは、ネットワークからバイトが届くまで、あるいは、ソケットが閉じられるまで、アプリケーションを一時停止させます。 次の例では、ネットワークからデータを受信し、コンソールに表示しています。 この例では、ネットワークから届くデータが ASCII エンコード テキストであると想定しています。 **Receive** メソッドは、ネットワークから受信したバイト数を返します。  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 ソケットが不要になったら、解放する必要があります。<xref:System.Net.Sockets.Socket.Shutdown%2A> メソッドを呼び出し、**Close** メソッドを呼び出します。 次の例では、**Socket** を解放しています。 <xref:System.Net.Sockets.SocketShutdown> 列挙は、送信、受信、あるいは両方のためにソケットを閉じるかどうかを示す定数を定義します。  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a>参照  
 [非同期クライアント ソケットの使用](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [リッスン (ソケットで)](../../../docs/framework/network-programming/listening-with-sockets.md)  
 [同期クライアント ソケットの例](../../../docs/framework/network-programming/synchronous-client-socket-example.md)
