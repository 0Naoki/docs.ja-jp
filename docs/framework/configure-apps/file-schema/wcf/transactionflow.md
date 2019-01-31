---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: ef3d92e07aaf4d4ba9d90e381017db104f2cc8fe
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276992"
---
# <a name="transactionflow"></a><span data-ttu-id="bf89f-101">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="bf89f-101">\<transactionFlow></span></span>
<span data-ttu-id="bf89f-102">カスタム バインドのトランザクション フロー サポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf89f-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="bf89f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bf89f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="bf89f-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="bf89f-104">\<bindings></span></span>  
<span data-ttu-id="bf89f-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="bf89f-105">\<customBinding></span></span>  
<span data-ttu-id="bf89f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="bf89f-106">\<binding></span></span>  
<span data-ttu-id="bf89f-107">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="bf89f-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf89f-108">構文</span><span class="sxs-lookup"><span data-stu-id="bf89f-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf89f-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bf89f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bf89f-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf89f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf89f-111">属性</span><span class="sxs-lookup"><span data-stu-id="bf89f-111">Attributes</span></span>  
  
|<span data-ttu-id="bf89f-112">属性</span><span class="sxs-lookup"><span data-stu-id="bf89f-112">Attribute</span></span>|<span data-ttu-id="bf89f-113">説明</span><span class="sxs-lookup"><span data-stu-id="bf89f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf89f-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="bf89f-114">transactionProtocol</span></span>|<span data-ttu-id="bf89f-115">使用されるトランザクション プロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf89f-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="bf89f-116">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="bf89f-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bf89f-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="bf89f-117">-   OleTransactions</span></span><br /><span data-ttu-id="bf89f-118">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="bf89f-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="bf89f-119">既定値は OleTransactions です。</span><span class="sxs-lookup"><span data-stu-id="bf89f-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="bf89f-120">この属性は <xref:System.ServiceModel.TransactionProtocol> 型です。</span><span class="sxs-lookup"><span data-stu-id="bf89f-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf89f-121">子要素</span><span class="sxs-lookup"><span data-stu-id="bf89f-121">Child Elements</span></span>  
 <span data-ttu-id="bf89f-122">なし。</span><span class="sxs-lookup"><span data-stu-id="bf89f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf89f-123">親要素</span><span class="sxs-lookup"><span data-stu-id="bf89f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bf89f-124">要素</span><span class="sxs-lookup"><span data-stu-id="bf89f-124">Element</span></span>|<span data-ttu-id="bf89f-125">説明</span><span class="sxs-lookup"><span data-stu-id="bf89f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf89f-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="bf89f-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="bf89f-127">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="bf89f-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf89f-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf89f-128">Remarks</span></span>  
 <span data-ttu-id="bf89f-129">この要素により、受信トランザクションの目的のプロトコル形式を指定できるだけでなく、エンドポイントのバインディング設定で受信トランザクション フローを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="bf89f-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="bf89f-130">この構成要素の使用に関する詳細については、次を参照してください。 [ServiceModel トランザクションの構成](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)と[トランザクション フローを有効にする](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)します。</span><span class="sxs-lookup"><span data-stu-id="bf89f-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bf89f-131">`OleTransactions` プロトコルを使用してエンドポイント間でトランザクションをフローさせるとき、フロー先のエンドポイントが `OleTransactions` 以外のプロトコルを使用して再びフローを試みると、トランザクション タイムアウトが失われる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf89f-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="bf89f-132">その結果、OleTransactions ホップより後のすべてのダウンレベル ノードが、予想より遅くタイムアウトする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf89f-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf89f-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf89f-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="bf89f-134">ServiceModel トランザクションの構成</span><span class="sxs-lookup"><span data-stu-id="bf89f-134">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="bf89f-135">トランザクション フローの有効化</span><span class="sxs-lookup"><span data-stu-id="bf89f-135">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="bf89f-136">バインディング</span><span class="sxs-lookup"><span data-stu-id="bf89f-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="bf89f-137">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="bf89f-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="bf89f-138">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="bf89f-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="bf89f-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="bf89f-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
