---
title: シリアル化バインダーの使用
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 677decebcf444fed95311bd02acf8a96e0a4eca9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591779"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="03867-102">シリアル化バインダーの使用</span><span class="sxs-lookup"><span data-stu-id="03867-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="03867-103">このサンプルでは、<xref:System.Runtime.Serialization.SerializationBinder> を使用して、ジェネリック型のバージョンをシリアル化する際に変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="03867-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="03867-104">使用例</span><span class="sxs-lookup"><span data-stu-id="03867-104">Demonstrates</span></span>  
 <span data-ttu-id="03867-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="03867-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="03867-106">説明</span><span class="sxs-lookup"><span data-stu-id="03867-106">Discussion</span></span>  
 <span data-ttu-id="03867-107">このサンプルはターゲットの異なるバージョンの .NET Framework は、通信をバイナリ フォーマッタとシリアル化バインダーを使用して 2 つのエンティティを示します。</span><span class="sxs-lookup"><span data-stu-id="03867-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
 <span data-ttu-id="03867-108">このサンプルの開発は、.NET リモート処理を使用して行われました。</span><span class="sxs-lookup"><span data-stu-id="03867-108">The development of this sample has been done using .NET Remoting.</span></span> <span data-ttu-id="03867-109">このサンプルは、[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] を対象とするサーバー (ジェネリック型を含むコントラクトを実装しています) と、2 つの異なるクライアント (1 つは [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] を対象とし、もう 1 つは [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] を対象としています) で構成されています。</span><span class="sxs-lookup"><span data-stu-id="03867-109">The sample consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="03867-110">このサーバーは、シリアル化の際に型のバージョンを相応に変更できるようにするために、<xref:System.Runtime.Serialization.SerializationBinder> をバイナリ フォーマッタにアタッチします。これにより、両方のクライアントで、これらの型を適切に逆シリアル化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="03867-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="03867-111">サンプルを設定、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="03867-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="03867-112">クライアントを実行するには、SBGenericsVTS ソリューションを右クリックして (6 プロジェクト) を選び**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="03867-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="03867-113">**共通プロパティ**、**スタートアップ プロジェクト**を選択し、**マルチ スタートアップ プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="03867-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="03867-114">選択**Server**し最初**Client20**し **[client40]** します。</span><span class="sxs-lookup"><span data-stu-id="03867-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="03867-115">選択、**開始**これら 3 つのアクションは、プロジェクトし、残りの部分に設定のままに**None**します。</span><span class="sxs-lookup"><span data-stu-id="03867-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="03867-116">クリックして**OK**し、f5 キーを押してサンプルを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="03867-116">Click **OK** and then press F5 to run the sample.</span></span>
