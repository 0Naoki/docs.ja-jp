---
title: UI オートメーション プロバイダーからのイベントの発生
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 328adccc2224d27230a06e8d98a691d12c5be218
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539052"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="92109-102">UI オートメーション プロバイダーからのイベントの発生</span><span class="sxs-lookup"><span data-stu-id="92109-102">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="92109-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="92109-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="92109-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="92109-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="92109-105">このトピックには、UI オートメーション プロバイダーからイベントを発生させる方法を示すコード例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="92109-105">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92109-106">例</span><span class="sxs-lookup"><span data-stu-id="92109-106">Example</span></span>  
 <span data-ttu-id="92109-107">次の例では、カスタム ボタン コントロールの実装で [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="92109-107">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="92109-108">実装により、UI オートメーション クライアント アプリケーションがボタンのクリックをシミュレートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="92109-108">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="92109-109">不要な処理を回避するために、例では <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> をチェックして、イベントが発生するかどうかを確認しています。</span><span class="sxs-lookup"><span data-stu-id="92109-109">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="92109-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="92109-110">See also</span></span>
- [<span data-ttu-id="92109-111">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="92109-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
