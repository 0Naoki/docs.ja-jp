---
title: ソケット
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
ms.openlocfilehash: 468d8afc290d8e725deb13ba57dd990181ae4e19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680495"
---
# <a name="sockets"></a><span data-ttu-id="2aed7-102">ソケット</span><span class="sxs-lookup"><span data-stu-id="2aed7-102">Sockets</span></span>
<span data-ttu-id="2aed7-103"><xref:System.Net.Sockets> 名前空間には、Windows ソケット インターフェイスのマネージド実装が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2aed7-103">The <xref:System.Net.Sockets> namespace contains a managed implementation of the Windows Sockets interface.</span></span> <span data-ttu-id="2aed7-104"><xref:System.Net> 名前空間のその他すべてのネットワーク アクセス クラスは、ソケットのこの実装の上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="2aed7-104">All other network-access classes in the <xref:System.Net> namespace are built on top of this implementation of sockets.</span></span>  
  
 <span data-ttu-id="2aed7-105">.NET Framework <xref:System.Net.Sockets.Socket> クラスは、Winsock32 API が提供するソケット サービスのマネージ コード版です。</span><span class="sxs-lookup"><span data-stu-id="2aed7-105">The .NET Framework <xref:System.Net.Sockets.Socket> class is a managed-code version of the socket services provided by the Winsock32 API.</span></span> <span data-ttu-id="2aed7-106">ほとんどの場合、**Socket** クラス メソッドはネイティブ Win32 の該当メソッドにデータをマーシャリングし、必要なセキュリティ チェックがあればそれを処理します。</span><span class="sxs-lookup"><span data-stu-id="2aed7-106">In most cases, the **Socket** class methods simply marshal data into their native Win32 counterparts and handle any necessary security checks.</span></span>  
  
 <span data-ttu-id="2aed7-107">**Socket** クラスは、同期と非同期という 2 つの基本モードに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2aed7-107">The **Socket** class supports two basic modes, synchronous and asynchronous.</span></span> <span data-ttu-id="2aed7-108">同期モードの場合、ネットワーク操作 (<xref:System.Net.Sockets.Socket.Send%2A> や <xref:System.Net.Sockets.Socket.Receive%2A> など) を実行する関数の呼び出しは、操作の完了を待ってから、呼び出し元のプログラムにコントロールを返します。</span><span class="sxs-lookup"><span data-stu-id="2aed7-108">In synchronous mode, calls to functions that perform network operations (such as <xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.Receive%2A>) wait until the operation completes before returning control to the calling program.</span></span> <span data-ttu-id="2aed7-109">非同期モードの場合、このような呼び出しはすぐに返されます。</span><span class="sxs-lookup"><span data-stu-id="2aed7-109">In asynchronous mode, these calls return immediately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aed7-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="2aed7-110">See also</span></span>
- [<span data-ttu-id="2aed7-111">方法: ソケットを作成する</span><span class="sxs-lookup"><span data-stu-id="2aed7-111">How to: Create a Socket</span></span>](../../../docs/framework/network-programming/how-to-create-a-socket.md)

- [<span data-ttu-id="2aed7-112">アプリケーション プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="2aed7-112">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
