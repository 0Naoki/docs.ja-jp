---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: fb2b324a2c128b470f1a9a21343408280c5e1862
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743245"
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="20e11-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="20e11-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="20e11-103">名前空間とプレフィックスのマッピングを含む要素セットを定義する構成セクションを表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="20e11-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="20e11-104">**\<system.serviceModel>** </span><span class="sxs-lookup"><span data-stu-id="20e11-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="20e11-105">&nbsp;&nbsp;**\<ルーティング >** </span><span class="sxs-lookup"><span data-stu-id="20e11-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="20e11-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="20e11-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="20e11-107">構文</span><span class="sxs-lookup"><span data-stu-id="20e11-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20e11-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="20e11-108">Attributes and elements</span></span>

<span data-ttu-id="20e11-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="20e11-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="20e11-110">属性</span><span class="sxs-lookup"><span data-stu-id="20e11-110">Attributes</span></span>

<span data-ttu-id="20e11-111">なし</span><span class="sxs-lookup"><span data-stu-id="20e11-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="20e11-112">子要素</span><span class="sxs-lookup"><span data-stu-id="20e11-112">Child elements</span></span>

|     | <span data-ttu-id="20e11-113">説明</span><span class="sxs-lookup"><span data-stu-id="20e11-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="20e11-114">**\<フィルター >**</span><span class="sxs-lookup"><span data-stu-id="20e11-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="20e11-115">XPath 式に使用される名前空間とプレフィックスのマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="20e11-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="20e11-116">親要素</span><span class="sxs-lookup"><span data-stu-id="20e11-116">Parent elements</span></span>

|     | <span data-ttu-id="20e11-117">説明</span><span class="sxs-lookup"><span data-stu-id="20e11-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="20e11-118">**\<ルーティング >**</span><span class="sxs-lookup"><span data-stu-id="20e11-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="20e11-119">Windows Communication Foundation (WCF) の種類を指定するルーティング フィルター セットを定義する構成セクションを表します<xref:System.ServiceModel.Dispatcher.MessageFilter>受信メッセージの評価とルーティング テーブルをするターゲット エンドポイントを定義するときに使用される。フィルターが一致したときにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="20e11-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="20e11-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="20e11-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
