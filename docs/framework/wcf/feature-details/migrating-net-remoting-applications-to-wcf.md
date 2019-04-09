---
title: .NET リモート処理アプリケーションの WCF への移行
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 4040fb0ac223f91705a49b733f6a1f42d144068e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091123"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="43de9-102">.NET リモート処理アプリケーションの WCF への移行</span><span class="sxs-lookup"><span data-stu-id="43de9-102">Migrating .NET Remoting Applications to WCF</span></span>
**<span data-ttu-id="43de9-103">このトピックの対象は、既存のアプリケーションとの下位互換性のために残されているレガシ テクノロジに特定されています。新規の開発には、このトピックを適用しないでください。</span><span class="sxs-lookup"><span data-stu-id="43de9-103">This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development.</span></span> <span data-ttu-id="43de9-104">WCF を使用して、分散アプリケーションを開発する必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="43de9-104">Distributed applications should now be developed using WCF.</span></span>**  
  
 <span data-ttu-id="43de9-105">既存の .NET リモート処理アプリケーションと WCF を活用するために 2 つの方法があります。 統合と移行します。</span><span class="sxs-lookup"><span data-stu-id="43de9-105">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="43de9-106">統合では、.NET Remoting 2.0 と WCF を並行して実行されている、既存の .NET Remoting 2.0 コードを変更することがなく同時に両方のテクノロジを同じビジネス オブジェクトを公開することができます。</span><span class="sxs-lookup"><span data-stu-id="43de9-106">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="43de9-107">統合では、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 以降が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43de9-107">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="43de9-108">WCF の機能を利用して、Remoting 2.0 システムとの互換性を配線する必要はない場合、は、サービス全体を WCF に移行することができます。</span><span class="sxs-lookup"><span data-stu-id="43de9-108">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="43de9-109">.NET Remoting 2.0 から WCF への移行では、リモート オブジェクトのインターフェイスとその構成設定の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="43de9-109">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="43de9-110">両方のトピックに掲載されて[を Windows Communication Foundation からリモート処理](https://go.microsoft.com/fwlink/?LinkId=74403)します。</span><span class="sxs-lookup"><span data-stu-id="43de9-110">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43de9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="43de9-111">See also</span></span>

- [<span data-ttu-id="43de9-112">概念</span><span class="sxs-lookup"><span data-stu-id="43de9-112">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
