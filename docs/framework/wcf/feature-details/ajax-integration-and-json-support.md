---
title: AJAX の統合と JSON のサポート
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: bcf1cab9386d9d9503af6258c1bb39f8744c073b
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2018
ms.locfileid: "46479625"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="f1f5b-102">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="f1f5b-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="f1f5b-103">ASP.NET Asynchronous JavaScript and XML (AJAX) の Windows Communication Foundation (WCF) のサポートと JavaScript Object Notation (JSON) データ形式は、AJAX クライアントに操作を公開する WCF サービスを許可します。</span><span class="sxs-lookup"><span data-stu-id="f1f5b-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="f1f5b-104">AJAX クライアントは、JavaScript コードを実行して、HTTP 要求を使用してこれらの WCF サービスへのアクセスの Web ページです。</span><span class="sxs-lookup"><span data-stu-id="f1f5b-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="f1f5b-105">このセクションのトピックでは、このサポートと実装方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f5b-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="f1f5b-106">ASP.NET 2.0 との統合と ASP.NET AJAX の詳細については、次を参照してください。 [ASP.NET AJAX の概要](https://go.microsoft.com/fwlink/?LinkId=96725)します。</span><span class="sxs-lookup"><span data-stu-id="f1f5b-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1f5b-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f1f5b-107">In This Section</span></span>  
 [<span data-ttu-id="f1f5b-108">ASP.NET AJAX 用の WCF サービスの作成</span><span class="sxs-lookup"><span data-stu-id="f1f5b-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="f1f5b-109">WCF サービスを公開する方法 AJAX クライアントに構成を適切な AJAX エンドポイントを追加することで、または、サービス ホスト ファクトリを自動的に AJAX エンドポイントを構成するサービス ホストを生成するようにカスタマイズを使用して、について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f5b-109">Describes how an WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="f1f5b-110">ASP.NET を使用せずに WCF AJAX サービスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f1f5b-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="f1f5b-111">ASP.NET を使用せずに、WCF サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f5b-111">Describes how to create an WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="f1f5b-112">JSON などのデータ転送形式のサポート</span><span class="sxs-lookup"><span data-stu-id="f1f5b-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="f1f5b-113">ASP.NET AJAX サービスとのメッセージングで、XML の代わりに一般に使用される JSON 形式のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f5b-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="f1f5b-114">方法 : AJAX 対応 ASP.NET Web サービスを WCF に移行する</span><span class="sxs-lookup"><span data-stu-id="f1f5b-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="f1f5b-115">WCF Web サービスに AJAX 対応 ASP.NET Web サービスを移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f5b-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f5b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1f5b-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="f1f5b-117">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="f1f5b-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
