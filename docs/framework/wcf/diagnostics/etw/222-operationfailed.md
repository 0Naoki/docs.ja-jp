---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: c49aad0f93ce47b66306d75741267530dc6d3fe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781642"
---
# <a name="222---operationfailed"></a><span data-ttu-id="1ed67-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="1ed67-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="1ed67-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1ed67-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ed67-104">ID</span><span class="sxs-lookup"><span data-stu-id="1ed67-104">ID</span></span>|<span data-ttu-id="1ed67-105">222</span><span class="sxs-lookup"><span data-stu-id="1ed67-105">222</span></span>|  
|<span data-ttu-id="1ed67-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="1ed67-106">Keywords</span></span>|<span data-ttu-id="1ed67-107">EndToEndMonitoring、HealthMonitoring、Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1ed67-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1ed67-108">レベル</span><span class="sxs-lookup"><span data-stu-id="1ed67-108">Level</span></span>|<span data-ttu-id="1ed67-109">警告</span><span class="sxs-lookup"><span data-stu-id="1ed67-109">Warning</span></span>|  
|<span data-ttu-id="1ed67-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="1ed67-110">Channel</span></span>|<span data-ttu-id="1ed67-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1ed67-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1ed67-112">説明</span><span class="sxs-lookup"><span data-stu-id="1ed67-112">Description</span></span>  
 <span data-ttu-id="1ed67-113">このイベントは、サービス モデルの既定の `OperationInvoker` が、そのメソッドを呼び出している間に例外に遭遇すると生成されます。</span><span class="sxs-lookup"><span data-stu-id="1ed67-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="1ed67-114">`FaultException` から派生する例外では、このイベントは生成されません。</span><span class="sxs-lookup"><span data-stu-id="1ed67-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1ed67-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="1ed67-115">Message</span></span>  
 <span data-ttu-id="1ed67-116">OperationInvoker によって呼び出されたメソッド '%1' で、ハンドルされない例外がスローされました。</span><span class="sxs-lookup"><span data-stu-id="1ed67-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="1ed67-117">メソッド呼び出し時間は '%2' ミリ秒でした。</span><span class="sxs-lookup"><span data-stu-id="1ed67-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1ed67-118">説明</span><span class="sxs-lookup"><span data-stu-id="1ed67-118">Details</span></span>  
  
|<span data-ttu-id="1ed67-119">データ項目名</span><span class="sxs-lookup"><span data-stu-id="1ed67-119">Data Item Name</span></span>|<span data-ttu-id="1ed67-120">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="1ed67-120">Data Item Type</span></span>|<span data-ttu-id="1ed67-121">説明</span><span class="sxs-lookup"><span data-stu-id="1ed67-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1ed67-122">メソッド名</span><span class="sxs-lookup"><span data-stu-id="1ed67-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="1ed67-123">`OperationInvoker` によって呼び出されたメソッドの CLR 名。</span><span class="sxs-lookup"><span data-stu-id="1ed67-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="1ed67-124">存続期間</span><span class="sxs-lookup"><span data-stu-id="1ed67-124">Duration</span></span>|`xs:long`|<span data-ttu-id="1ed67-125">`OperationInvoker` でメソッドを呼び出すのにかかった時間 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="1ed67-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="1ed67-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="1ed67-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="1ed67-127">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="1ed67-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1ed67-128">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="1ed67-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1ed67-129">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="1ed67-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1ed67-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1ed67-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1ed67-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="1ed67-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
