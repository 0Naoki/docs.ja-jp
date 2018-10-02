---
title: UI オートメーション プロバイダーからのプロパティの返却
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: ac5d539f99fe4f7a20d9030986120318840801bb
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48036939"
---
# <a name="return-properties-from-a-ui-automation-provider"></a><span data-ttu-id="08bcb-102">UI オートメーション プロバイダーからのプロパティの返却</span><span class="sxs-lookup"><span data-stu-id="08bcb-102">Return Properties from a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="08bcb-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="08bcb-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="08bcb-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]に関する最新情報については[Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="08bcb-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="08bcb-105">このトピックのサンプル コードでは、UI オートメーション プロバイダーが、要素のプロパティをクライアント アプリケーションへどのように返すかを示します。</span><span class="sxs-lookup"><span data-stu-id="08bcb-105">This topic contains sample code that shows how a UI Automation provider can return properties of an element to client applications.</span></span>  
  
 <span data-ttu-id="08bcb-106">明示的にサポートしていないプロパティについては、プロバイダーは `null` (Visual Basic では`Nothing` ) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="08bcb-106">For any property it does not explicitly support, the provider must return `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="08bcb-107">これにより、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] はホスト ウィンドウ プロバイダーなど、別のソースからプロパティを取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="08bcb-107">This ensures that [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] attempts to obtain the property from another source, such as the host window provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08bcb-108">例</span><span class="sxs-lookup"><span data-stu-id="08bcb-108">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="08bcb-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="08bcb-109">See Also</span></span>  
 [<span data-ttu-id="08bcb-110">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="08bcb-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="08bcb-111">サーバー側 UI オートメーション プロバイダーの実装</span><span class="sxs-lookup"><span data-stu-id="08bcb-111">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
