---
title: '軽減策: WPF ウィンドウのレンダリング'
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d54751ae0492e25f824eee6362e0f3bca446d75e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147629"
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="8cddf-102">軽減策: WPF ウィンドウのレンダリング</span><span class="sxs-lookup"><span data-stu-id="8cddf-102">Mitigation: WPF Window Rendering</span></span>
<span data-ttu-id="8cddf-103">Windows 8 以上で実行している [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] では、マルチ モニターのシナリオで 1 つのディスプレイの外部にウィンドウを拡張すると、ウィンドウ全体がクリッピングなしでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="8cddf-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="8cddf-104">影響</span><span class="sxs-lookup"><span data-stu-id="8cddf-104">Impact</span></span>  
 <span data-ttu-id="8cddf-105">一般に、複数のモニターで、クリッピングなしでウィンドウ全体を表示することが期待の動作です。</span><span class="sxs-lookup"><span data-stu-id="8cddf-105">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="8cddf-106">ただし、Windows 7 以前のバージョンでは、2 つ目のモニターにウィンドウの一部をレンダリングするとパフォーマンスに大きな影響があるため、WPF ウィンドウが 1 つのディスプレイの外部に拡張されるときにはクリッピングされます。</span><span class="sxs-lookup"><span data-stu-id="8cddf-106">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>  
  
 <span data-ttu-id="8cddf-107">Windows 8 以上で複数のモニターに WPF ウィンドウをレンダリングする際の詳細な影響は、多数の要因に依存しているために、正確に数量化することはできません。</span><span class="sxs-lookup"><span data-stu-id="8cddf-107">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="8cddf-108">場合によっては、グラフィックを多用するアプリケーションを実行するユーザーや複数のモニターに及ぶウィンドウを使用するユーザーの場合は特に、依然としてパフォーマンスに望ましくない影響が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="8cddf-108">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="8cddf-109">または、.NET Framework の複数のバージョン間で一貫性のある動作が実現できれば十分な場合もあります 。</span><span class="sxs-lookup"><span data-stu-id="8cddf-109">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="8cddf-110">軽減策</span><span class="sxs-lookup"><span data-stu-id="8cddf-110">Mitigation</span></span>  
 <span data-ttu-id="8cddf-111">この変更を無効にして、WPF ウィンドウが 1 つのディスプレイを超える場合にクリッピングされるという、以前の動作に戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="8cddf-111">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="8cddf-112">これには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="8cddf-112">There are two ways to do this:</span></span>  
  
-   <span data-ttu-id="8cddf-113">`<EnableMultiMonitorDisplayClipping>` 要素をアプリケーションの構成ファイルの `<appSettings>` セクションに追加することにより、Windows 8 以降で実行中のアプリケーションでこの動作を無効にしたり有効にしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8cddf-113">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="8cddf-114">たとえば、次の構成セクションにより、クリッピングなしのレンダリングが無効になります。</span><span class="sxs-lookup"><span data-stu-id="8cddf-114">For example, the following configuration section disables rendering without clipping:</span></span>  
  
    ```xml  
    <appSettings>  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
      </appSettings>  
    ```  
  
     <span data-ttu-id="8cddf-115">`<EnableMultiMonitorDisplayClipping>` 構成設定には、次の 2 つの値のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8cddf-115">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>  
  
    -   <span data-ttu-id="8cddf-116">`true` を指定すると、レンダリングの際にウィンドウをモニターの境界でクリッピングすることを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8cddf-116">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>  
  
    -   <span data-ttu-id="8cddf-117">`false` を指定すると、レンダリングの際にウィンドウをモニターの境界でクリッピングすることを無効にします。</span><span class="sxs-lookup"><span data-stu-id="8cddf-117">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>  
  
-   <span data-ttu-id="8cddf-118">これを行うには、アプリの起動時に <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="8cddf-118">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cddf-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cddf-119">See also</span></span>

- [<span data-ttu-id="8cddf-120">ランタイムの変更点</span><span class="sxs-lookup"><span data-stu-id="8cddf-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
