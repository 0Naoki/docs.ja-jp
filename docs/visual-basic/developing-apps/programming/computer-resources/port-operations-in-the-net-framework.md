---
title: Visual Basic による .NET Framework でのポート操作
ms.date: 07/20/2015
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
ms.openlocfilehash: 33298fd9840630fbfd6f7f9d883cc2397a459843
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826445"
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a><span data-ttu-id="7a7f7-102">Visual Basic による .NET Framework でのポート操作</span><span class="sxs-lookup"><span data-stu-id="7a7f7-102">Port Operations in the .NET Framework with Visual Basic</span></span>
<span data-ttu-id="7a7f7-103"><xref:System.IO.Ports?displayProperty=nameWithType> 名前空間の [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] クラスを介して、コンピューターのシリアル ポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-103">You can access your computer's serial ports through the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="7a7f7-104">最も重要な役割を持つのが <xref:System.IO.Ports.SerialPort> クラスです。このクラスにより、同期 I/O とイベント ドリブン I/O のフレームワーク、ピンの状態とブレーク状態へのアクセス、およびシリアル ドライバーのプロパティへのアクセスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-104">The most important class, <xref:System.IO.Ports.SerialPort>, provides a framework for synchronous and event-driven I/O, access to pin and break states, and access to serial driver properties.</span></span> <span data-ttu-id="7a7f7-105">このクラスは、<xref:System.IO.Ports.SerialPort.BaseStream> プロパティを通じてアクセス可能な <xref:System.IO.Stream> オブジェクト内にラップできます。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-105">It can be wrapped in a <xref:System.IO.Stream> object, accessible through the <xref:System.IO.Ports.SerialPort.BaseStream> property.</span></span> <span data-ttu-id="7a7f7-106"><xref:System.IO.Stream> オブジェクト内で <xref:System.IO.Ports.SerialPort> をラップすることにより、ストリームを使用するクラスからシリアル ポートへのアクセスを実現できます。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-106">Wrapping <xref:System.IO.Ports.SerialPort> in a <xref:System.IO.Stream> object allows the serial port to be accessed by classes that use streams.</span></span> <span data-ttu-id="7a7f7-107">名前空間には、シリアル ポートの制御を容易にする列挙型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-107">The namespace includes enumerations that simplify the control of serial ports.</span></span>  
  
 <span data-ttu-id="7a7f7-108">最も簡単に <xref:System.IO.Ports.SerialPort> オブジェクトを作成する方法は、<xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> メソッドを経由することです。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-108">The simplest way to create a <xref:System.IO.Ports.SerialPort> object is through the <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a7f7-109">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] クラスを使用してパラレル ポートや USB ポートなどの他の種類のポートに直接アクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-109">You cannot use [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes to directly access other types of ports, such as parallel ports, USB ports, and so on.</span></span>  
  
## <a name="enumerations"></a><span data-ttu-id="7a7f7-110">列挙</span><span class="sxs-lookup"><span data-stu-id="7a7f7-110">Enumerations</span></span>  
 <span data-ttu-id="7a7f7-111">次の表は、シリアル ポートへのアクセスに使用される主な列挙型を一覧にまとめ、説明を加えたものです。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-111">This table lists and describes the main enumerations used for accessing a serial port:</span></span>  
  
|<span data-ttu-id="7a7f7-112">列挙</span><span class="sxs-lookup"><span data-stu-id="7a7f7-112">Enumeration</span></span>|<span data-ttu-id="7a7f7-113">説明</span><span class="sxs-lookup"><span data-stu-id="7a7f7-113">Description</span></span>|  
|---|---|   
|<xref:System.IO.Ports.Handshake>|<span data-ttu-id="7a7f7-114"><xref:System.IO.Ports.SerialPort> オブジェクトでのシリアル ポート通信の確立に使用する制御プロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-114">Specifies the control protocol used in establishing a serial port communication for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.Parity>|<span data-ttu-id="7a7f7-115"><xref:System.IO.Ports.SerialPort> オブジェクトのパリティ ビットを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-115">Specifies the parity bit for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialData>|<span data-ttu-id="7a7f7-116"><xref:System.IO.Ports.SerialPort> オブジェクトのシリアル ポートで受信した文字の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-116">Specifies the type of character that was received on the serial port of the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialError>|<span data-ttu-id="7a7f7-117"><xref:System.IO.Ports.SerialPort> オブジェクトで発生するエラーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-117">Specifies errors that occur on the <xref:System.IO.Ports.SerialPort> object</span></span>|  
|<xref:System.IO.Ports.SerialPinChange>|<span data-ttu-id="7a7f7-118"><xref:System.IO.Ports.SerialPort> オブジェクトで発生した変更の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-118">Specifies the type of change that occurred on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.StopBits>|<span data-ttu-id="7a7f7-119"><xref:System.IO.Ports.SerialPort> オブジェクトで使用するストップ ビットの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a7f7-119">Specifies the number of stop bits used on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a7f7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a7f7-120">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [<span data-ttu-id="7a7f7-121">コンピューターのポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="7a7f7-121">Accessing the Computer's Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
