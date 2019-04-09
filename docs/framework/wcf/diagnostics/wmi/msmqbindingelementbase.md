---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 1df4b32feda246a536183a42ac11b113bc4bb259
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093762"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="b95a4-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="b95a4-102">MsmqBindingElementBase</span></span>
<span data-ttu-id="b95a4-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="b95a4-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b95a4-104">構文</span><span class="sxs-lookup"><span data-stu-id="b95a4-104">Syntax</span></span>  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b95a4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b95a4-105">Methods</span></span>  
 <span data-ttu-id="b95a4-106">MsmqBindingElementBase クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="b95a4-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b95a4-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b95a4-107">Properties</span></span>  
 <span data-ttu-id="b95a4-108">MsmqBindingElementBase クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b95a4-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="b95a4-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="b95a4-109">CustomDeadLetterQueue</span></span>  
 <span data-ttu-id="b95a4-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b95a4-110">Data type: string</span></span>  
  
 <span data-ttu-id="b95a4-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-112">アプリケーションごとの配信不能キューの場所が含まれている URI です。ここには、期限切れのメッセージや、転送または配信に失敗したメッセージが配置されます。</span><span class="sxs-lookup"><span data-stu-id="b95a4-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="b95a4-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="b95a4-113">DeadLetterQueue</span></span>  
 <span data-ttu-id="b95a4-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b95a4-114">Data type: string</span></span>  
  
 <span data-ttu-id="b95a4-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-116">使用する配信不能キューの型を示す列挙型の値です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="b95a4-117">Durable</span><span class="sxs-lookup"><span data-stu-id="b95a4-117">Durable</span></span>  
 <span data-ttu-id="b95a4-118">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="b95a4-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b95a4-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-120">このバインディングによって処理されるメッセージが永続的なものか不安定なものかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="b95a4-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="b95a4-121">ExactlyOnce</span></span>  
 <span data-ttu-id="b95a4-122">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="b95a4-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b95a4-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-124">このバインディングで処理されるメッセージが正確に 1 回だけ受信されるかどうかを示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="b95a4-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="b95a4-125">MaxRetryCycles</span></span>  
 <span data-ttu-id="b95a4-126">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="b95a4-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="b95a4-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-128">受信アプリケーションにメッセージを配信する再試行サイクルの最大数です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="b95a4-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="b95a4-129">ReceiveErrorHandling</span></span>  
 <span data-ttu-id="b95a4-130">データ型: string</span><span class="sxs-lookup"><span data-stu-id="b95a4-130">Data type: string</span></span>  
  
 <span data-ttu-id="b95a4-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-132">有害メッセージの処理の設定です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="b95a4-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="b95a4-133">ReceiveRetryCount</span></span>  
 <span data-ttu-id="b95a4-134">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="b95a4-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="b95a4-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-136">アプリケーション キューから読み取られるメッセージの即時再試行の最大回数です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="b95a4-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="b95a4-137">RetryCycleDelay</span></span>  
 <span data-ttu-id="b95a4-138">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="b95a4-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="b95a4-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-140">すぐに配信できなかったメッセージを配信しようとするときの、再試行サイクルの時間遅延を示す値です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="b95a4-141">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="b95a4-141">TimeToLive</span></span>  
 <span data-ttu-id="b95a4-142">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="b95a4-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="b95a4-143">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-144">このバインディングで処理されるメッセージの期限が切れるまで、メッセージをキュー内で保持する時間です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="b95a4-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="b95a4-145">UseMsmqTracing</span></span>  
 <span data-ttu-id="b95a4-146">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="b95a4-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="b95a4-147">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-148">このバインディングにより処理されるメッセージをトレースするかどうかを示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="b95a4-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="b95a4-149">UseSourceJournal</span></span>  
 <span data-ttu-id="b95a4-150">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="b95a4-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="b95a4-151">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="b95a4-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b95a4-152">このバインディングにより処理されるメッセージのコピーをソース ジャーナル キューに保存するかどうかを示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="b95a4-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b95a4-153">必要条件</span><span class="sxs-lookup"><span data-stu-id="b95a4-153">Requirements</span></span>  
  
|<span data-ttu-id="b95a4-154">MOF</span><span class="sxs-lookup"><span data-stu-id="b95a4-154">MOF</span></span>|<span data-ttu-id="b95a4-155">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="b95a4-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b95a4-156">名前空間</span><span class="sxs-lookup"><span data-stu-id="b95a4-156">Namespace</span></span>|<span data-ttu-id="b95a4-157">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="b95a4-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b95a4-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="b95a4-158">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
