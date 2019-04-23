---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 1f34486296465b3ea0b5b05bd9492062c85ad8c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134434"
---
# <a name="wsdlimporter"></a><span data-ttu-id="e2634-101">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="e2634-101">\<wsdlImporter></span></span>
<span data-ttu-id="e2634-102">WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2634-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="e2634-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e2634-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e2634-104">\<client></span><span class="sxs-lookup"><span data-stu-id="e2634-104">\<client></span></span>  
<span data-ttu-id="e2634-105">\<matadata></span><span class="sxs-lookup"><span data-stu-id="e2634-105">\<metadata></span></span>  
<span data-ttu-id="e2634-106">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="e2634-106">\<wsdlImporters></span></span>  
<span data-ttu-id="e2634-107">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="e2634-107">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2634-108">構文</span><span class="sxs-lookup"><span data-stu-id="e2634-108">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2634-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e2634-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e2634-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2634-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2634-111">属性</span><span class="sxs-lookup"><span data-stu-id="e2634-111">Attributes</span></span>  
  
|<span data-ttu-id="e2634-112">属性</span><span class="sxs-lookup"><span data-stu-id="e2634-112">Attribute</span></span>|<span data-ttu-id="e2634-113">説明</span><span class="sxs-lookup"><span data-stu-id="e2634-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e2634-114">この要素の型です。</span><span class="sxs-lookup"><span data-stu-id="e2634-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2634-115">子要素</span><span class="sxs-lookup"><span data-stu-id="e2634-115">Child Elements</span></span>  
 <span data-ttu-id="e2634-116">なし。</span><span class="sxs-lookup"><span data-stu-id="e2634-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2634-117">親要素</span><span class="sxs-lookup"><span data-stu-id="e2634-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e2634-118">要素</span><span class="sxs-lookup"><span data-stu-id="e2634-118">Element</span></span>|<span data-ttu-id="e2634-119">説明</span><span class="sxs-lookup"><span data-stu-id="e2634-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2634-120">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="e2634-120">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="e2634-121">WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2634-121">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2634-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="e2634-122">Remarks</span></span>  
 <span data-ttu-id="e2634-123">WSDL インポーターは、メタデータのインポートに加えて、コントラクトおよびエンドポイント情報を表すさまざまなクラスにその情報を変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2634-123">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="e2634-124">コントラクトおよびエンドポイントの情報やプロパティを選択的にインポートできます。これらは、任意のインポート エラーを公開し、インポートおよび変換プロセスに関連する型情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e2634-124">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="e2634-125">また、任意のポリシー ドキュメント、WSDL ドキュメント、WSDL 拡張、および XML スキーマ ドキュメントにアクセスするためのバインディング情報およびプロパティのインポートもサポートします。</span><span class="sxs-lookup"><span data-stu-id="e2634-125">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2634-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2634-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="e2634-127">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="e2634-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="e2634-128">クライアント</span><span class="sxs-lookup"><span data-stu-id="e2634-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
