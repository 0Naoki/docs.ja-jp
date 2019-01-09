---
title: '&lt;routing&gt; の &lt;filters&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 4a6a079264c54ac481c3a8996b74ac924c33bdc7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150891"
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="c3f07-102">&lt;routing&gt; の &lt;filters&gt;</span><span class="sxs-lookup"><span data-stu-id="c3f07-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="c3f07-103">Windows Communication Foundation (WCF) の種類を指定するルーティング フィルター セットを定義する構成セクションを表します。<xref:System.ServiceModel.Dispatcher.MessageFilter>受信メッセージを評価するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3f07-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="c3f07-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="c3f07-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="c3f07-105">&nbsp;&nbsp;[**\<ルーティング >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="c3f07-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="c3f07-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<フィルター >**</span><span class="sxs-lookup"><span data-stu-id="c3f07-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c3f07-107">構文</span><span class="sxs-lookup"><span data-stu-id="c3f07-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3f07-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c3f07-108">Attributes and elements</span></span>

<span data-ttu-id="c3f07-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3f07-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c3f07-110">属性</span><span class="sxs-lookup"><span data-stu-id="c3f07-110">Attributes</span></span>

<span data-ttu-id="c3f07-111">なし</span><span class="sxs-lookup"><span data-stu-id="c3f07-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c3f07-112">子要素</span><span class="sxs-lookup"><span data-stu-id="c3f07-112">Child elements</span></span>

|     | <span data-ttu-id="c3f07-113">説明</span><span class="sxs-lookup"><span data-stu-id="c3f07-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c3f07-114">**\<フィルター >**</span><span class="sxs-lookup"><span data-stu-id="c3f07-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="c3f07-115">Windows Communication Foundation (WCF) の種類を決定するルーティング フィルターを含む<xref:System.ServiceModel.Dispatcher.MessageFilter>受信メッセージの評価時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3f07-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="c3f07-116">親要素</span><span class="sxs-lookup"><span data-stu-id="c3f07-116">Parent elements</span></span>

|     | <span data-ttu-id="c3f07-117">説明</span><span class="sxs-lookup"><span data-stu-id="c3f07-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c3f07-118">**\<ルーティング >**</span><span class="sxs-lookup"><span data-stu-id="c3f07-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="c3f07-119">Windows Communication Foundation (WCF) の種類を指定するルーティング フィルター セットを定義する構成セクションを表します<xref:System.ServiceModel.Dispatcher.MessageFilter>受信メッセージの評価とルーティング テーブルをするターゲット エンドポイントを定義するときに使用される。フィルターが一致したときにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c3f07-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c3f07-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3f07-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
