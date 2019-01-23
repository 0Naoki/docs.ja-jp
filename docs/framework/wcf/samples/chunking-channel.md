---
title: チャネルのチャンキング
ms.date: 03/30/2017
ms.assetid: e4d53379-b37c-4b19-8726-9cc914d5d39f
ms.openlocfilehash: 3e98e4be3c5ad9d6d18990feeae86369775972b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624240"
---
# <a name="chunking-channel"></a><span data-ttu-id="98d18-102">チャネルのチャンキング</span><span class="sxs-lookup"><span data-stu-id="98d18-102">Chunking Channel</span></span>
<span data-ttu-id="98d18-103">Windows Communication Foundation (WCF) を使用してサイズの大きいメッセージを送信するときに、それらのメッセージをバッファーに使用されるメモリの量を制限することが望ましいは多くの場合。</span><span class="sxs-lookup"><span data-stu-id="98d18-103">When sending large messages using Windows Communication Foundation (WCF), it is often desirable to limit the amount of memory used to buffer those messages.</span></span> <span data-ttu-id="98d18-104">解決策の 1 つとして、メッセージ本文のストリーミングが考えられます (データの大部分が本文にある場合)。</span><span class="sxs-lookup"><span data-stu-id="98d18-104">One possible solution is to stream the message body (assuming the bulk of the data is in the body).</span></span> <span data-ttu-id="98d18-105">ただし、一部のプロトコルではメッセージ全体のバッファが必要です。</span><span class="sxs-lookup"><span data-stu-id="98d18-105">However some protocols require buffering of the entire message.</span></span> <span data-ttu-id="98d18-106">たとえば、信頼できるメッセージとセキュリティの 2 つがこの例として挙げられます。</span><span class="sxs-lookup"><span data-stu-id="98d18-106">Reliable messaging and security are two such examples.</span></span> <span data-ttu-id="98d18-107">そこで別の解決策として、サイズの大きいメッセージをチャンクと呼ばれるサイズの小さいメッセージに分割し、そうしたチャンクを 1 つずつ送信し、受信側でサイズの大きいメッセージに再構成するという方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="98d18-107">Another possible solution is to divide up the large message into smaller messages called chunks, send those chunks one chunk at a time, and reconstitute the large message on the receiving side.</span></span> <span data-ttu-id="98d18-108">アプリケーション自体でこうしたチャンキングおよびチャンキング解除を行うことができるほか、カスタム チャネルを使用して行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="98d18-108">The application itself could do this chunking and de-chunking or it could use a custom channel to do it.</span></span> <span data-ttu-id="98d18-109">チャネルのチャンキングのサンプルでは、カスタム プロトコル チャネルまたはカスタム階層チャネルを使用して、サイズの大きい任意のメッセージのチャンキングおよびチャンキング解除を行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="98d18-109">The chunking channel sample shows how a custom protocol or layered channel can be used to do chunking and de-chunking of arbitrarily large messages.</span></span>  
  
 <span data-ttu-id="98d18-110">チャンキングは常に、送信されるメッセージ全体が構築された後にのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d18-110">Chunking should always be employed only after the entire message to be sent has been constructed.</span></span> <span data-ttu-id="98d18-111">チャネルのチャンキングは常に、セキュリティ チャネルおよび信頼できるセッション チャネルの下位の階層に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d18-111">A chunking channel should always be layered below a security channel and a reliable session channel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98d18-112">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98d18-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="98d18-113">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="98d18-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="98d18-114">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="98d18-114">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="98d18-115">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="98d18-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="98d18-116">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-116">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ChunkingChannel`  
  
## <a name="chunking-channel-assumptions-and-limitations"></a><span data-ttu-id="98d18-117">チャネルのチャンキングにおける前提と制限</span><span class="sxs-lookup"><span data-stu-id="98d18-117">Chunking Channel Assumptions and Limitations</span></span>  
  
### <a name="message-structure"></a><span data-ttu-id="98d18-118">メッセージ構造</span><span class="sxs-lookup"><span data-stu-id="98d18-118">Message Structure</span></span>  
 <span data-ttu-id="98d18-119">チャネルのチャンキングでは、チャンク対象のメッセージについて、次のメッセージ構造を想定しています。</span><span class="sxs-lookup"><span data-stu-id="98d18-119">The chunking channel assumes the following message structure for messages to be chunked:</span></span>  
  
```xml  
<soap:Envelope ...>  
  <!-- headers -->  
  <soap:Body>  
    <operationElement>  
      <paramElement>data to be chunked</paramElement>  
    </operationElement>  
  </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="98d18-120">ServiceModel を使用する場合、1 つの入力パラメータを持つコントラクト操作は、入力メッセージについてこのメッセージ形式に準拠します。</span><span class="sxs-lookup"><span data-stu-id="98d18-120">When using the ServiceModel, contract operations that have 1 input parameter comply with this shape of message for their input message.</span></span> <span data-ttu-id="98d18-121">同様に、1 つの出力パラメータまたは 1 つの戻り値を持つコントラクト操作は、出力メッセージについてこのメッセージ形式に準拠します。</span><span class="sxs-lookup"><span data-stu-id="98d18-121">Similarly, contract operations that have 1 output parameter or return value comply with this shape of message for their output message.</span></span> <span data-ttu-id="98d18-122">このような操作の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="98d18-122">The following are examples of such operations:</span></span>  
  
```  
[ServiceContract]  
interface ITestService  
{  
    [OperationContract]  
    Stream EchoStream(Stream stream);  
  
    [OperationContract]  
    Stream DownloadStream();  
  
    [OperationContract(IsOneWay = true)]  
    void UploadStream(Stream stream);  
}  
```  
  
### <a name="sessions"></a><span data-ttu-id="98d18-123">セッション</span><span class="sxs-lookup"><span data-stu-id="98d18-123">Sessions</span></span>  
 <span data-ttu-id="98d18-124">チャネルのチャンキングでは、メッセージ (チャンク) の順序付き配信でメッセージが正確に 1 回だけ配信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d18-124">The chunking channel requires messages to be delivered exactly once, in ordered delivery of messages (chunks).</span></span> <span data-ttu-id="98d18-125">つまり、基になるチャネル スタックはセッションフルであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="98d18-125">This means the underlying channel stack must be sessionful.</span></span> <span data-ttu-id="98d18-126">セッションは、トランスポート (TCP トランスポートなど) またはセッションフル プロトコル チャネル (信頼できるセッション チャネルなど) によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-126">Sessions can be provided by the transport (for example, TCP transport) or by a sessionful protocol channel (for example, ReliableSession channel).</span></span>  
  
### <a name="asynchronous-send-and-receive"></a><span data-ttu-id="98d18-127">非同期の送受信</span><span class="sxs-lookup"><span data-stu-id="98d18-127">Asynchronous Send and Receive</span></span>  
 <span data-ttu-id="98d18-128">非同期の送受信方法は、このバージョンのチャネルのチャンキング サンプルには実装されていません。</span><span class="sxs-lookup"><span data-stu-id="98d18-128">Asynchronous send and receive methods are not implemented in this version of the chunking channel sample.</span></span>  
  
## <a name="chunking-protocol"></a><span data-ttu-id="98d18-129">プロトコルのチャンキング</span><span class="sxs-lookup"><span data-stu-id="98d18-129">Chunking Protocol</span></span>  
 <span data-ttu-id="98d18-130">チャネルのチャンキングでは、一連のチャンクの開始と終了、および各チャンクのシーケンス番号を示すプロトコルを定義します。</span><span class="sxs-lookup"><span data-stu-id="98d18-130">The chunking channel defines a protocol that indicates the start and end of a series of chunks as well as the sequence number of each chunk.</span></span> <span data-ttu-id="98d18-131">次の 3 つのメッセージ例では、開始メッセージ、チャンク メッセージ、および終了メッセージを、それぞれの主要な特徴を説明するコメントと共に示します。</span><span class="sxs-lookup"><span data-stu-id="98d18-131">The following three example messages demonstrate the start, chunk and end messages with comments that describe the key aspects of each.</span></span>  
  
### <a name="start-message"></a><span data-ttu-id="98d18-132">開始メッセージ</span><span class="sxs-lookup"><span data-stu-id="98d18-132">Start Message</span></span>  
  
```xml  
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"   
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">  
  <s:Header>  
<!--Original message action is replaced with a chunking-specific action. -->  
    <a:Action s:mustUnderstand="1">http://samples.microsoft.com/chunkingAction</a:Action>  
<!--  
Original message is assigned a unique id that is transmitted   
in a MessageId header. Note that this is different from the WS-Addressing MessageId header.  
-->  
    <MessageId s:mustUnderstand="1" xmlns="http://samples.microsoft.com/chunking">  
53f183ee-04aa-44a0-b8d3-e45224563109  
</MessageId>  
<!--  
ChunkingStart header signals the start of a chunked message.  
-->  
    <ChunkingStart s:mustUnderstand="1" i:nil="true" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://samples.microsoft.com/chunking" />  
<!--  
Original message action is transmitted in OriginalAction.  
This is required to re-create the original message on the other side.  
-->  
    <OriginalAction xmlns="http://samples.microsoft.com/chunking">  
http://tempuri.org/ITestService/EchoStream  
    </OriginalAction>  
   <!--  
    All original message headers are included here.  
   -->  
  </s:Header>  
  <s:Body>  
<!--  
Chunking assumes this structure of Body content:  
<element>  
  <childelement>large data to be chunked<childelement>  
</element>  
The start message contains just <element> and <childelement> without  
the data to be chunked.  
-->  
    <EchoStream xmlns="http://tempuri.org/">  
      <stream />  
    </EchoStream>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="chunk-message"></a><span data-ttu-id="98d18-133">チャンク メッセージ</span><span class="sxs-lookup"><span data-stu-id="98d18-133">Chunk Message</span></span>  
  
```xml  
<s:Envelope   
  xmlns:a="http://www.w3.org/2005/08/addressing"   
  xmlns:s="http://www.w3.org/2003/05/soap-envelope">  
  <s:Header>  
   <!--  
    All chunking protocol messages have this action.  
   -->  
    <a:Action s:mustUnderstand="1">  
      http://samples.microsoft.com/chunkingAction  
    </a:Action>  
<!--  
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.  
-->  
    <MessageId s:mustUnderstand="1"   
               xmlns="http://samples.microsoft.com/chunking">  
      53f183ee-04aa-44a0-b8d3-e45224563109  
    </MessageId>  
<!--  
The sequence number of the chunk.  
This number restarts at 1 with each new sequence of chunks.  
-->  
    <ChunkNumber s:mustUnderstand="1"   
                 xmlns="http://samples.microsoft.com/chunking">  
      1096  
    </ChunkNumber>  
  </s:Header>  
  <s:Body>  
<!--  
The chunked data is wrapped in a chunk element.  
The encoding of this data (and the entire message)   
depends on the encoder used. The chunking channel does not mandate an encoding.  
-->  
    <chunk xmlns="http://samples.microsoft.com/chunking">  
kfSr2QcBlkHTvQ==  
    </chunk>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="end-message"></a><span data-ttu-id="98d18-134">終了メッセージ</span><span class="sxs-lookup"><span data-stu-id="98d18-134">End Message</span></span>  
  
```xml  
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"   
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://samples.microsoft.com/chunkingAction  
    </a:Action>  
<!--  
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.  
-->  
    <MessageId s:mustUnderstand="1"   
               xmlns="http://samples.microsoft.com/chunking">  
      53f183ee-04aa-44a0-b8d3-e45224563109  
    </MessageId>  
<!--  
ChunkingEnd header signals the end of a chunk sequence.  
-->  
    <ChunkingEnd s:mustUnderstand="1" i:nil="true"   
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance"   
                 xmlns="http://samples.microsoft.com/chunking" />  
<!--  
ChunkingEnd messages have a sequence number.  
-->  
    <ChunkNumber s:mustUnderstand="1"   
                 xmlns="http://samples.microsoft.com/chunking">  
      79  
    </ChunkNumber>  
  </s:Header>  
  <s:Body>  
<!--  
The ChunkingEnd message has the same <element><childelement> structure  
as the ChunkingStart message.  
-->  
    <EchoStream xmlns="http://tempuri.org/">  
      <stream />  
    </EchoStream>  
  </s:Body>  
</s:Envelope>  
```  
  
## <a name="chunking-channel-architecture"></a><span data-ttu-id="98d18-135">チャネルのチャンキングのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="98d18-135">Chunking Channel Architecture</span></span>  
 <span data-ttu-id="98d18-136">チャンキングを行うチャネルは `IDuplexSessionChannel` で、高レベルで通常のチャネル アーキテクチャに従います。</span><span class="sxs-lookup"><span data-stu-id="98d18-136">The chunking channel is an `IDuplexSessionChannel` that, at a high level, follows the typical channel architecture.</span></span> <span data-ttu-id="98d18-137">`ChunkingBindingElement` と `ChunkingChannelFactory` を作成できる `ChunkingChannelListener` があります。</span><span class="sxs-lookup"><span data-stu-id="98d18-137">There is a `ChunkingBindingElement` that can build a `ChunkingChannelFactory` and a `ChunkingChannelListener`.</span></span> <span data-ttu-id="98d18-138">`ChunkingChannelFactory` は、作成を要求されたときに `ChunkingChannel` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="98d18-138">The `ChunkingChannelFactory` creates instances of `ChunkingChannel` when it is asked to.</span></span> <span data-ttu-id="98d18-139">`ChunkingChannelListener` は、新しい内部チャネルが受け入れられると `ChunkingChannel` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="98d18-139">The `ChunkingChannelListener` creates instances of `ChunkingChannel` when a new inner channel is accepted.</span></span> <span data-ttu-id="98d18-140">メッセージの送受信は `ChunkingChannel` 自体が行います。</span><span class="sxs-lookup"><span data-stu-id="98d18-140">The `ChunkingChannel` itself is responsible for sending and receiving messages.</span></span>  
  
 <span data-ttu-id="98d18-141">1 つ下のレベルでは、`ChunkingChannel` がいくつかのコンポーネントに依存して、チャンキングを行うプロトコルを実装します。</span><span class="sxs-lookup"><span data-stu-id="98d18-141">At the next level down, `ChunkingChannel` relies on several components to implement the chunking protocol.</span></span> <span data-ttu-id="98d18-142">送信側では、このチャネルは、実際にチャンキングを行う `XmlDictionaryWriter` というカスタム `ChunkingWriter` を使用します。</span><span class="sxs-lookup"><span data-stu-id="98d18-142">On the send side, the channel uses a custom `XmlDictionaryWriter` called `ChunkingWriter` that does the actual chunking.</span></span> <span data-ttu-id="98d18-143">`ChunkingWriter` は内部チャネルを使用して直接チャンクを送信します。</span><span class="sxs-lookup"><span data-stu-id="98d18-143">`ChunkingWriter` uses the inner channel directly to send chunks.</span></span> <span data-ttu-id="98d18-144">カスタム `XmlDictionaryWriter` を使用すると、本文のサイズが大きい元のメッセージの書き込みと同時にチャンクを送信できます。</span><span class="sxs-lookup"><span data-stu-id="98d18-144">Using a custom `XmlDictionaryWriter` allows us to send out chunks as the large body of the original message is being written.</span></span> <span data-ttu-id="98d18-145">つまり、元のメッセージ全体はバッファされません。</span><span class="sxs-lookup"><span data-stu-id="98d18-145">This means we do not buffer the entire original message.</span></span>  
  
 <span data-ttu-id="98d18-146">![チャネルのチャンキング](../../../../docs/framework/wcf/samples/media/chunkingchannel1.gif "ChunkingChannel1")</span><span class="sxs-lookup"><span data-stu-id="98d18-146">![Chunking Channel](../../../../docs/framework/wcf/samples/media/chunkingchannel1.gif "ChunkingChannel1")</span></span>  
  
 <span data-ttu-id="98d18-147">受信側では、`ChunkingChannel` は内部チャネルからメッセージをプルし、`XmlDictionaryReader` というカスタム `ChunkingReader` に渡します。これにより、受信チャンクから元のメッセージが再構成されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-147">On the receive side, `ChunkingChannel` pulls messages from the inner channel and hands them to a custom `XmlDictionaryReader` called `ChunkingReader`, which reconstitutes the original message from the incoming chunks.</span></span> <span data-ttu-id="98d18-148">`ChunkingChannel` は、この `ChunkingReader` を `Message` というカスタム `ChunkingMessage` 実装でラップし、このメッセージを上の層に戻します。</span><span class="sxs-lookup"><span data-stu-id="98d18-148">`ChunkingChannel` wraps this `ChunkingReader` in a custom `Message` implementation called `ChunkingMessage` and returns this message to the layer above.</span></span> <span data-ttu-id="98d18-149">`ChunkingReader` と `ChunkingMessage` を組み合わせて使用すると、元のメッセージ本文全体をバッファーする代わりに、元のメッセージ本文が上の層によって読み取られるのと同時にメッセージのチャンキング解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="98d18-149">This combination of `ChunkingReader` and `ChunkingMessage` allows us to de-chunk the original message body as it is being read by the layer above instead of having to buffer the entire original message body.</span></span> <span data-ttu-id="98d18-150">`ChunkingReader` には、バッファー対象のチャンクの構成可能な最大数を上限として受信チャンクをバッファーするキューがあります。</span><span class="sxs-lookup"><span data-stu-id="98d18-150">`ChunkingReader` has a queue where it buffers incoming chunks up to a maximum configurable number of buffered chunks.</span></span> <span data-ttu-id="98d18-151">この上限に達すると、リーダーは、上の層によってメッセージがキューから出される (つまり元のメッセージ本文の読み取りだけが行われる) まで待機するか、または受信タイムアウトの上限に達するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="98d18-151">When this maximum limit is reached, the reader waits for messages to be drained from the queue by the layer above (that is, by just reading from the original message body) or until the maximum receive timeout is reached.</span></span>  
  
 <span data-ttu-id="98d18-152">![チャネルのチャンキング](../../../../docs/framework/wcf/samples/media/chunkingchannel2.gif "ChunkingChannel2")</span><span class="sxs-lookup"><span data-stu-id="98d18-152">![Chunking Channel](../../../../docs/framework/wcf/samples/media/chunkingchannel2.gif "ChunkingChannel2")</span></span>  
  
## <a name="chunking-programming-model"></a><span data-ttu-id="98d18-153">プログラミング モデルのチャンキング</span><span class="sxs-lookup"><span data-stu-id="98d18-153">Chunking Programming Model</span></span>  
 <span data-ttu-id="98d18-154">サービス開発者は `ChunkingBehavior` 属性をコントラクト内の操作に適用することにより、チャンク対象のメッセージを指定できます。</span><span class="sxs-lookup"><span data-stu-id="98d18-154">Service developers can specify which messages are to be chunked by applying the `ChunkingBehavior` attribute to operations within the contract.</span></span> <span data-ttu-id="98d18-155">この属性は `AppliesTo` プロパティを公開します。このプロパティを使用すると、開発者は、入力メッセージと出力メッセージのどちらか、またはその両方にチャンキングを適用するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="98d18-155">The attribute exposes an `AppliesTo` property that allows the developer to specify whether chunking applies to the input message, the output message or both.</span></span> <span data-ttu-id="98d18-156">`ChunkingBehavior` 属性の使用方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="98d18-156">The following example shows the usage of `ChunkingBehavior` attribute:</span></span>  
  
```  
[ServiceContract]  
interface ITestService  
{  
    [OperationContract]  
    [ChunkingBehavior(ChunkingAppliesTo.Both)]  
    Stream EchoStream(Stream stream);  
  
    [OperationContract]  
    [ChunkingBehavior(ChunkingAppliesTo.OutMessage)]  
    Stream DownloadStream();  
  
    [OperationContract(IsOneWay=true)]  
    [ChunkingBehavior(ChunkingAppliesTo.InMessage)]  
    void UploadStream(Stream stream);  
  
}  
```  
  
 <span data-ttu-id="98d18-157">このプログラミング モデルから、`ChunkingBindingElement` は、チャンク対象のメッセージを識別するアクション URI のリストをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="98d18-157">From this programming model, the `ChunkingBindingElement` compiles a list of action URIs that identify messages to be chunked.</span></span> <span data-ttu-id="98d18-158">各送信メッセージのアクションはこのリストと比較され、そのメッセージはチャンク対象なのか、または直接送信する必要があるのかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-158">The action of each outgoing message is compared against this list to determine if the message should be chunked or sent directly.</span></span>  
  
## <a name="implementing-the-send-operation"></a><span data-ttu-id="98d18-159">Send 操作の実装</span><span class="sxs-lookup"><span data-stu-id="98d18-159">Implementing the Send Operation</span></span>  
 <span data-ttu-id="98d18-160">高レベルの Send 操作では、送信メッセージをチャンクする必要があるかどうかを最初にチェックし、その必要がない場合は内部チャネルを使用して直接メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="98d18-160">At a high level, the Send operation first checks whether the outgoing message must be chunked and, if not, sends the message directly using the inner channel.</span></span>  
  
 <span data-ttu-id="98d18-161">メッセージのチャンキングが必要な場合、Send は新しい `ChunkingWriter` を作成して、この `WriteBodyContents` を渡す送信メッセージで `ChunkingWriter` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="98d18-161">If the message must be chunked, Send creates a new `ChunkingWriter` and calls `WriteBodyContents` on the outgoing message passing it this `ChunkingWriter`.</span></span> <span data-ttu-id="98d18-162">次に、`ChunkingWriter` はメッセージのチャンキング (およびチャンク開始メッセージへの元のメッセージ ヘッダーのコピー) を行い、内部チャネルを使用してチャンクを送信します。</span><span class="sxs-lookup"><span data-stu-id="98d18-162">The `ChunkingWriter` then does the message chunking (including copying original message headers to the start chunk message) and sends chunks using the inner channel.</span></span>  
  
 <span data-ttu-id="98d18-163">いくつかの細かい点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="98d18-163">A few details worth noting:</span></span>  
  
-   <span data-ttu-id="98d18-164">Send は最初に `ThrowIfDisposedOrNotOpened` を呼び出し、`CommunicationState` が開かれた状態にします。</span><span class="sxs-lookup"><span data-stu-id="98d18-164">Send first calls `ThrowIfDisposedOrNotOpened` to ensure the `CommunicationState` is opened.</span></span>  
  
-   <span data-ttu-id="98d18-165">Send は、セッションごとに一度に 1 つのメッセージだけを送信できるように同期されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-165">Sending is synchronized so that only one message can be sent at a time for each session.</span></span> <span data-ttu-id="98d18-166">`ManualResetEvent` という `sendingDone` があり、これはチャンキングが行われたメッセージが送信されたときにリセットされます。</span><span class="sxs-lookup"><span data-stu-id="98d18-166">There is a `ManualResetEvent` named `sendingDone` that is reset when a chunked message is being sent.</span></span> <span data-ttu-id="98d18-167">チャンク終了メッセージが送信されると、このイベントが設定されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-167">Once the end chunk message is sent, this event is set.</span></span> <span data-ttu-id="98d18-168">Send メソッドは、このイベントが設定されるのを待機した後でメッセージの送信を試行します。</span><span class="sxs-lookup"><span data-stu-id="98d18-168">The Send method waits for this event to be set before it tries to send the outgoing message.</span></span>  
  
-   <span data-ttu-id="98d18-169">Send は `CommunicationObject.ThisLock` をロックし、送信中に同期状態が変更されないようにします。</span><span class="sxs-lookup"><span data-stu-id="98d18-169">Send locks the `CommunicationObject.ThisLock` to prevent synchronized state changes while sending.</span></span> <span data-ttu-id="98d18-170"><xref:System.ServiceModel.Channels.CommunicationObject> の状態とステート マシンの詳細については、<xref:System.ServiceModel.Channels.CommunicationObject> のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98d18-170">See the <xref:System.ServiceModel.Channels.CommunicationObject> documentation for more information about <xref:System.ServiceModel.Channels.CommunicationObject> states and state machine.</span></span>  
  
-   <span data-ttu-id="98d18-171">Send に渡されるタイムアウトは、すべてのチャンクの送信を含む送信操作全体のタイムアウトとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-171">The timeout passed to Send is used as the timeout for the entire send operation which includes sending all of the chunks.</span></span>  
  
-   <span data-ttu-id="98d18-172">元のメッセージ本文全体がバッファされないように、カスタムの `XmlDictionaryWriter` デザインが選択されています。</span><span class="sxs-lookup"><span data-stu-id="98d18-172">The custom `XmlDictionaryWriter` design was chosen to avoid buffering the entire original message body.</span></span> <span data-ttu-id="98d18-173">`XmlDictionaryReader` を使用して本文の `message.GetReaderAtBodyContents` を取得する場合、本文全体がバッファされます。</span><span class="sxs-lookup"><span data-stu-id="98d18-173">If we were to get an `XmlDictionaryReader` on the body using `message.GetReaderAtBodyContents` the entire body would be buffered.</span></span> <span data-ttu-id="98d18-174">この場合は、代わりに、`XmlDictionaryWriter` に渡されるカスタムの `message.WriteBodyContents` があります。</span><span class="sxs-lookup"><span data-stu-id="98d18-174">Instead, we have a custom `XmlDictionaryWriter` that is passed to `message.WriteBodyContents`.</span></span> <span data-ttu-id="98d18-175">メッセージがライタの WriteBase64 を呼び出すと、ライタはチャンクをパッケージ化してメッセージを作成し、内部チャンネルを使用して送信します。</span><span class="sxs-lookup"><span data-stu-id="98d18-175">As the message calls WriteBase64 on the writer, the writer packages up chunks into messages and sends them using the inner channel.</span></span> <span data-ttu-id="98d18-176">WriteBase64 は、チャンクが送信されるまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="98d18-176">WriteBase64 blocks until the chunk is sent.</span></span>  
  
## <a name="implementing-the-receive-operation"></a><span data-ttu-id="98d18-177">Receive 操作の実装</span><span class="sxs-lookup"><span data-stu-id="98d18-177">Implementing the Receive Operation</span></span>  
 <span data-ttu-id="98d18-178">高レベルの Receive 操作では、最初に受信メッセージが `null` でないことをチェックすると共に、アクションが `ChunkingAction` であることをチェックします。</span><span class="sxs-lookup"><span data-stu-id="98d18-178">At a high level, the Receive operation first checks that the incoming message is not `null` and that its action is the `ChunkingAction`.</span></span> <span data-ttu-id="98d18-179">どちらかの条件が満たされていない場合、メッセージは Receive によって変更されないまま返されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-179">If it does not meet both criteria, the message is returned unchanged from Receive.</span></span> <span data-ttu-id="98d18-180">それ以外の場合、Receive は新しい `ChunkingReader` と、それを (`ChunkingMessage` を呼び出して) ラップする新しい `GetNewChunkingMessage` を作成します。</span><span class="sxs-lookup"><span data-stu-id="98d18-180">Otherwise, Receive creates a new `ChunkingReader` and a new `ChunkingMessage` wrapped around it (by calling `GetNewChunkingMessage`).</span></span> <span data-ttu-id="98d18-181">Receive は、新しい `ChunkingMessage` を返す前に、スレッド プールのスレッドを使用して `ReceiveChunkLoop` を実行します。これによってループ内に `innerChannel.Receive` が呼び出され、チャンク終了メッセージを受信するか、または受信タイムアウトに達するまで、チャンクが `ChunkingReader` に渡されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-181">Before returning that new `ChunkingMessage`, Receive uses a threadpool thread to execute `ReceiveChunkLoop`, which calls `innerChannel.Receive` in a loop and hands off chunks to the `ChunkingReader` until the end chunk message is received or the receive timeout is hit.</span></span>  
  
 <span data-ttu-id="98d18-182">いくつかの細かい点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="98d18-182">A few details worth noting:</span></span>  
  
-   <span data-ttu-id="98d18-183">Send と同様、Receive は最初に `ThrowIfDisposedOrNotOepned` を呼び出して、`CommunicationState` が開かれた状態にします。</span><span class="sxs-lookup"><span data-stu-id="98d18-183">Like Send, Receive first calls `ThrowIfDisposedOrNotOepned` to ensure the `CommunicationState` is Opened.</span></span>  
  
-   <span data-ttu-id="98d18-184">また Receive も、セッションから一度に 1 つのメッセージだけを受信できるように同期されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-184">Receive is also synchronized so that only one message can be received at a time from the session.</span></span> <span data-ttu-id="98d18-185">これは特に重要です。チャンク開始メッセージが受信されると、それ以降受信されるすべてのメッセージは、チャンク終了メッセージが受信されるまで、この新しいチャンク シーケンス内のチャンクであると想定されるためです。</span><span class="sxs-lookup"><span data-stu-id="98d18-185">This is especially important because once a start chunk message is received, all subsequent received messages are expected to be chunks within this new chunk sequence until an end chunk message is received.</span></span> <span data-ttu-id="98d18-186">Receive は、現在チャンキングを解除中のメッセージに属するすべてのチャンクが受信されるまでは、内部チャネルからメッセージをプルできません。</span><span class="sxs-lookup"><span data-stu-id="98d18-186">Receive cannot pull messages from the inner channel until all chunks that belong to the message currently being de-chunked are received.</span></span> <span data-ttu-id="98d18-187">これを実現するため、Receive は `ManualResetEvent` という `currentMessageCompleted` を使用します。これはチャンク終了メッセージが受信されたときに設定され、新しいチャンク開始メッセージが受信されたときにリセットされます。</span><span class="sxs-lookup"><span data-stu-id="98d18-187">To accomplish this, Receive uses a `ManualResetEvent` named `currentMessageCompleted`, which is set when the end chunk message is received and reset when a new start chunk message is received.</span></span>  
  
-   <span data-ttu-id="98d18-188">Receive は Send と異なり、受信中に同期状態の遷移を妨げません。</span><span class="sxs-lookup"><span data-stu-id="98d18-188">Unlike Send, Receive does not prevent synchronized state transitions while receiving.</span></span> <span data-ttu-id="98d18-189">たとえば、受信中に Close を呼び出して、保留中の元のメッセージの受信が完了するか、または指定されたタイムアウト値に達するまで待機できます。</span><span class="sxs-lookup"><span data-stu-id="98d18-189">For example, Close can be called while receiving and waits until the pending receive of the original message is completed or the specified timeout value is reached.</span></span>  
  
-   <span data-ttu-id="98d18-190">Receive に渡されるタイムアウトは、すべてのチャンクの受信を含む受信操作全体のタイムアウトとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-190">The timeout passed to Receive is used as the timeout for the entire receive operation, which includes receiving all of the chunks.</span></span>  
  
-   <span data-ttu-id="98d18-191">メッセージを処理するレイヤでメッセージ本文を処理する速度が、チャンク メッセージを受信する速度より遅い場合、`ChunkingReader` は、`ChunkingBindingElement.MaxBufferedChunks` で指定された上限に達するまでこうした受信チャンクをバッファします。</span><span class="sxs-lookup"><span data-stu-id="98d18-191">If the layer that consumes the message is consuming the message body at a rate lower than the rate of incoming chunk messages, the `ChunkingReader` buffers those incoming chunks up to the limit specified by `ChunkingBindingElement.MaxBufferedChunks`.</span></span> <span data-ttu-id="98d18-192">この上限に達すると、バッファされたチャンクが処理されるか、または受信タイムアウトに達するまで、チャンクは下位層からプルされなくなります。</span><span class="sxs-lookup"><span data-stu-id="98d18-192">Once that limit is reached, no more chunks are pulled from the lower layer until either a buffered chunk is consumed or the receive timeout is reached.</span></span>  
  
## <a name="communicationobject-overrides"></a><span data-ttu-id="98d18-193">CommunicationObject のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="98d18-193">CommunicationObject Overrides</span></span>  
  
### <a name="onopen"></a><span data-ttu-id="98d18-194">OnOpen</span><span class="sxs-lookup"><span data-stu-id="98d18-194">OnOpen</span></span>  
 <span data-ttu-id="98d18-195">`OnOpen` は `innerChannel.Open` を呼び出して内部チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="98d18-195">`OnOpen` calls `innerChannel.Open` to open the inner channel.</span></span>  
  
### <a name="onclose"></a><span data-ttu-id="98d18-196">OnClose</span><span class="sxs-lookup"><span data-stu-id="98d18-196">OnClose</span></span>  
 <span data-ttu-id="98d18-197">`OnClose` は、保留状態の `stopReceive` が停止したことを通知するため、最初に `true` を `ReceiveChunkLoop` に設定します。</span><span class="sxs-lookup"><span data-stu-id="98d18-197">`OnClose` first sets `stopReceive` to `true` to signal the pending `ReceiveChunkLoop` to stop.</span></span> <span data-ttu-id="98d18-198">待機しその、 `receiveStopped``ManualResetEvent`、ときに設定されています`ReceiveChunkLoop`を停止します。</span><span class="sxs-lookup"><span data-stu-id="98d18-198">It then waits for the `receiveStopped``ManualResetEvent`, which is set when `ReceiveChunkLoop` stops.</span></span> <span data-ttu-id="98d18-199">`ReceiveChunkLoop` が指定されたタイムアウト内で停止した場合、`OnClose` はタイムアウトの残り時間で `innerChannel.Close` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="98d18-199">Assuming the `ReceiveChunkLoop` stops within the specified timeout, `OnClose` calls `innerChannel.Close` with the remaining timeout.</span></span>  
  
### <a name="onabort"></a><span data-ttu-id="98d18-200">OnAbort</span><span class="sxs-lookup"><span data-stu-id="98d18-200">OnAbort</span></span>  
 <span data-ttu-id="98d18-201">`OnAbort` は、`innerChannel.Abort` を呼び出して内部チャネルを中止します。</span><span class="sxs-lookup"><span data-stu-id="98d18-201">`OnAbort` calls `innerChannel.Abort` to abort the inner channel.</span></span> <span data-ttu-id="98d18-202">保留中の `ReceiveChunkLoop` がある場合は、保留中の `innerChannel.Receive` 呼び出しから例外を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="98d18-202">If there is a pending `ReceiveChunkLoop` it gets an exception from the pending `innerChannel.Receive` call.</span></span>  
  
### <a name="onfaulted"></a><span data-ttu-id="98d18-203">OnFaulted</span><span class="sxs-lookup"><span data-stu-id="98d18-203">OnFaulted</span></span>  
 <span data-ttu-id="98d18-204">チャネルでエラーが発生した場合、`ChunkingChannel` では特別な動作は必要ありません。したがって、`OnFaulted` はオーバーライドされません。</span><span class="sxs-lookup"><span data-stu-id="98d18-204">The `ChunkingChannel` does not require special behavior when the channel is faulted so `OnFaulted` is not overridden.</span></span>  
  
## <a name="implementing-channel-factory"></a><span data-ttu-id="98d18-205">チャネル ファクトリの実装</span><span class="sxs-lookup"><span data-stu-id="98d18-205">Implementing Channel Factory</span></span>  
 <span data-ttu-id="98d18-206">`ChunkingChannelFactory` は `ChunkingDuplexSessionChannel` のインスタンスを作成し、遷移した状態を内部チャネル ファクトリに転送します。</span><span class="sxs-lookup"><span data-stu-id="98d18-206">The `ChunkingChannelFactory` is responsible for creating instances of `ChunkingDuplexSessionChannel` and for cascading state transitions to the inner channel factory.</span></span>  
  
 <span data-ttu-id="98d18-207">`OnCreateChannel` は内部チャネル ファクトリを使用して、`IDuplexSessionChannel` 内部チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="98d18-207">`OnCreateChannel` uses the inner channel factory to create an `IDuplexSessionChannel` inner channel.</span></span> <span data-ttu-id="98d18-208">次に、新しい `ChunkingDuplexSessionChannel` を作成し、それに内部チャネル、チャンク対象のメッセージ アクションのリスト、および受信時にバッファするチャンクの最大数を渡します。</span><span class="sxs-lookup"><span data-stu-id="98d18-208">It then creates a new `ChunkingDuplexSessionChannel` passing it this inner channel along with the list of message actions to be chunked and the maximum number of chunks to buffer upon receive.</span></span> <span data-ttu-id="98d18-209">チャンク対象のメッセージ アクションのリストと、バッファするチャンクの最大数の 2 つは、パラメータとしてコンストラクタの `ChunkingChannelFactory` に渡されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-209">The list of message actions to be chunked and the maximum number of chunks to buffer are two parameters passed to `ChunkingChannelFactory` in its constructor.</span></span> <span data-ttu-id="98d18-210">`ChunkingBindingElement` に関するセクションでは、これらの値の発生元について説明します。</span><span class="sxs-lookup"><span data-stu-id="98d18-210">The section on `ChunkingBindingElement` describes where these values come from.</span></span>  
  
 <span data-ttu-id="98d18-211">`OnOpen`、`OnClose`、`OnAbort`、およびそれぞれと同等の非同期のメソッドは、対応する状態遷移メソッドを内部チャネル ファクトリで呼び出します。</span><span class="sxs-lookup"><span data-stu-id="98d18-211">The `OnOpen`, `OnClose`, `OnAbort` and their asynchronous equivalents call the corresponding state transition method on the inner channel factory.</span></span>  
  
## <a name="implementing-channel-listener"></a><span data-ttu-id="98d18-212">チャネル リスナの実装</span><span class="sxs-lookup"><span data-stu-id="98d18-212">Implementing Channel Listener</span></span>  
 <span data-ttu-id="98d18-213">`ChunkingChannelListener` は、内部チャネル リスナのラッパーです。</span><span class="sxs-lookup"><span data-stu-id="98d18-213">The `ChunkingChannelListener` is a wrapper around an inner channel listener.</span></span> <span data-ttu-id="98d18-214">この主な機能は、内部チャネル リスナへの呼び出しを代行するほか、内部チャネル リスナから受け入れられたチャネルを新しい `ChunkingDuplexSessionChannels` でラップすることです。</span><span class="sxs-lookup"><span data-stu-id="98d18-214">Its main function, besides delegate calls to that inner channel listener, is to wrap new `ChunkingDuplexSessionChannels` around channels accepted from the inner channel listener.</span></span> <span data-ttu-id="98d18-215">これは、`OnAcceptChannel` と `OnEndAcceptChannel` で行われます。</span><span class="sxs-lookup"><span data-stu-id="98d18-215">This is done in `OnAcceptChannel` and `OnEndAcceptChannel`.</span></span> <span data-ttu-id="98d18-216">新しく作成された `ChunkingDuplexSessionChannel` は、以前説明した他のパラメータと共に内部チャネルに渡されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-216">The newly created `ChunkingDuplexSessionChannel` is passed the inner channel along with the other parameters previously described.</span></span>  
  
## <a name="implementing-binding-element-and-binding"></a><span data-ttu-id="98d18-217">バインディング要素とバインディングの実装</span><span class="sxs-lookup"><span data-stu-id="98d18-217">Implementing Binding Element and Binding</span></span>  
 <span data-ttu-id="98d18-218">`ChunkingBindingElement` は、`ChunkingChannelFactory` および `ChunkingChannelListener` を作成します。</span><span class="sxs-lookup"><span data-stu-id="98d18-218">`ChunkingBindingElement` is responsible for creating the `ChunkingChannelFactory` and `ChunkingChannelListener`.</span></span> <span data-ttu-id="98d18-219">`ChunkingBindingElement`を確認するかどうかで T `CanBuildChannelFactory` \<T > と`CanBuildChannelListener` \<T > の種類は`IDuplexSessionChannel`(チャネルのチャンキングでサポートされている唯一のチャネル) と、バインディング内の他のバインド要素がこれをサポートチャネルの種類。</span><span class="sxs-lookup"><span data-stu-id="98d18-219">The `ChunkingBindingElement` checks whether T in `CanBuildChannelFactory`\<T> and `CanBuildChannelListener`\<T> is of type `IDuplexSessionChannel` (the only channel supported by the chunking channel) and that the other binding elements in the binding support this channel type.</span></span>  
  
 <span data-ttu-id="98d18-220">`BuildChannelFactory`\<T > をまず確認要求されたチャネルの種類がビルドすることができ、次にチャンク対象のメッセージ アクションの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="98d18-220">`BuildChannelFactory`\<T> first checks that the requested channel type can be built and then gets a list of message actions to be chunked.</span></span> <span data-ttu-id="98d18-221">詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98d18-221">For more information, see the following section.</span></span> <span data-ttu-id="98d18-222">次に、新しい `ChunkingChannelFactory` を作成し、それに内部チャネル ファクトリ (`context.BuildInnerChannelFactory<IDuplexSessionChannel>` から返されたままの状態での)、メッセージ アクションのリスト、およびバッファするチャンクの最大数を渡します。</span><span class="sxs-lookup"><span data-stu-id="98d18-222">It then creates a new `ChunkingChannelFactory` passing it the inner channel factory (as returned from `context.BuildInnerChannelFactory<IDuplexSessionChannel>`), the list of message actions, and the maximum number of chunks to buffer.</span></span> <span data-ttu-id="98d18-223">チャンクの最大数は、`MaxBufferedChunks` によって公開される `ChunkingBindingElement` というプロパティによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-223">The maximum number of chunks comes from a property called `MaxBufferedChunks` exposed by the `ChunkingBindingElement`.</span></span>  
  
 <span data-ttu-id="98d18-224">`BuildChannelListener<T>` には、`ChunkingChannelListener` を作成してこれに内部チャネル リスナーを渡す同様の実装があります。</span><span class="sxs-lookup"><span data-stu-id="98d18-224">`BuildChannelListener<T>` has a similar implementation for creating `ChunkingChannelListener` and passing it the inner channel listener.</span></span>  
  
 <span data-ttu-id="98d18-225">このサンプルには、`TcpChunkingBinding` というバインディング例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="98d18-225">There is an example binding included in this sample named `TcpChunkingBinding`.</span></span> <span data-ttu-id="98d18-226">このバインディングは、`TcpTransportBindingElement` と `ChunkingBindingElement` の 2 つのバインディング要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="98d18-226">This binding consists of two binding elements: `TcpTransportBindingElement` and `ChunkingBindingElement`.</span></span> <span data-ttu-id="98d18-227">このバインディングは、`MaxBufferedChunks` プロパティを公開する他にも、`TcpTransportBindingElement` プロパティの一部を設定します。たとえば、ヘッダーについて、`MaxReceivedMessageSize` を `ChunkingUtils.ChunkSize` + 100 KB に設定します。</span><span class="sxs-lookup"><span data-stu-id="98d18-227">In addition to exposing the `MaxBufferedChunks` property, the binding also sets some of the `TcpTransportBindingElement` properties such as `MaxReceivedMessageSize` (sets it to `ChunkingUtils.ChunkSize` + 100KB bytes for headers).</span></span>  
  
 <span data-ttu-id="98d18-228">また、`TcpChunkingBinding` は、`IBindingRuntimePreferences` を実装し、`ReceiveSynchronously` メソッドに対して true を返すことで、同期 Receive 呼び出しのみが実装されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="98d18-228">`TcpChunkingBinding` also implements `IBindingRuntimePreferences` and returns true from the `ReceiveSynchronously` method indicating that only the synchronous Receive calls are implemented.</span></span>  
  
### <a name="determining-which-messages-to-chunk"></a><span data-ttu-id="98d18-229">チャンク対象のメッセージの判断</span><span class="sxs-lookup"><span data-stu-id="98d18-229">Determining Which Messages To Chunk</span></span>  
 <span data-ttu-id="98d18-230">チャネルのチャンキングによってチャンクされるメッセージは、`ChunkingBehavior` 属性を介して識別されるメッセージのみです。</span><span class="sxs-lookup"><span data-stu-id="98d18-230">The chunking channel chunks only the messages identified through the `ChunkingBehavior` attribute.</span></span> <span data-ttu-id="98d18-231">`ChunkingBehavior` クラスは `IOperationBehavior` を実装し、`AddBindingParameter` メソッドの呼び出しによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-231">The `ChunkingBehavior` class implements `IOperationBehavior` and is implemented by calling the `AddBindingParameter` method.</span></span> <span data-ttu-id="98d18-232">このメソッドでは、`ChunkingBehavior` が `AppliesTo` プロパティの値 (`InMessage` または`OutMessage` のいずれか、またはその両方) を調べ、どのメッセージがチャンク対象かを判断します。</span><span class="sxs-lookup"><span data-stu-id="98d18-232">In this method, the `ChunkingBehavior` examines the value of its `AppliesTo` property (`InMessage`, `OutMessage` or both) to determine which messages should be chunked.</span></span> <span data-ttu-id="98d18-233">次に、チャンク対象の各メッセージのアクションを (`OperationDescription` の Messages コレクションから) 取得し、これを `ChunkingBindingParameter` のインスタンス内に含まれている文字列コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="98d18-233">It then gets the action of each of those messages (from the Messages collection on `OperationDescription`) and adds it to a string collection contained within an instance of `ChunkingBindingParameter`.</span></span> <span data-ttu-id="98d18-234">そして、この `ChunkingBindingParameter` を指定された `BindingParameterCollection` に追加します。</span><span class="sxs-lookup"><span data-stu-id="98d18-234">It then adds this `ChunkingBindingParameter` to the provided `BindingParameterCollection`.</span></span>  
  
 <span data-ttu-id="98d18-235">この `BindingParameterCollection` は、バインド要素がチャネル ファクトリまたはチャネル リスナを作成するときに、`BindingContext` 内でバインディングの各バインド要素に渡されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-235">This `BindingParameterCollection` is passed inside the `BindingContext` to each binding element in the binding when that binding element builds the channel factory or the channel listener.</span></span> <span data-ttu-id="98d18-236">`ChunkingBindingElement`の実装の`BuildChannelFactory<T>`と`BuildChannelListener<T>`この`ChunkingBindingParameter`のうち、 `BindingContext’`s`BindingParameterCollection`します。</span><span class="sxs-lookup"><span data-stu-id="98d18-236">The `ChunkingBindingElement`'s implementation of `BuildChannelFactory<T>` and `BuildChannelListener<T>` pull this `ChunkingBindingParameter` out of the `BindingContext’`s `BindingParameterCollection`.</span></span> <span data-ttu-id="98d18-237">次に、`ChunkingBindingParameter` に含まれているアクションのコレクションが `ChunkingChannelFactory` または `ChunkingChannelListener` に渡され、その後 `ChunkingDuplexSessionChannel` に渡されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-237">The collection of actions contained within the `ChunkingBindingParameter` is then passed to the `ChunkingChannelFactory` or `ChunkingChannelListener`, which in turn passes it to the `ChunkingDuplexSessionChannel`.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="98d18-238">サンプルの実行</span><span class="sxs-lookup"><span data-stu-id="98d18-238">Running the Sample</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="98d18-239">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="98d18-239">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="98d18-240">次のコマンドを使用して、[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="98d18-240">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="98d18-241">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="98d18-241">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="98d18-242">ソリューションをビルドする手順については、 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="98d18-242">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="98d18-243">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="98d18-243">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="98d18-244">最初に Service.exe を実行して次に Client.exe を実行し、両方のコンソール ウィンドウで出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="98d18-244">Run Service.exe first, then run Client.exe and watch both console windows for output.</span></span>  
  
 <span data-ttu-id="98d18-245">このサンプルを実行すると、次の出力が予測されます。</span><span class="sxs-lookup"><span data-stu-id="98d18-245">When running the sample, the following output is expected.</span></span>  
  
 <span data-ttu-id="98d18-246">クライアント:</span><span class="sxs-lookup"><span data-stu-id="98d18-246">Client:</span></span>  
  
```  
Press enter when service is available  
  
 > Sent chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
```  
  
 <span data-ttu-id="98d18-247">サーバー:</span><span class="sxs-lookup"><span data-stu-id="98d18-247">Server:</span></span>  
  
```  
Service started, press enter to exit  
 < Received chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
```  
  
## <a name="see-also"></a><span data-ttu-id="98d18-248">関連項目</span><span class="sxs-lookup"><span data-stu-id="98d18-248">See also</span></span>
