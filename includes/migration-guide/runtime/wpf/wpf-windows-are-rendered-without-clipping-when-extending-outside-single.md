---
ms.openlocfilehash: 2e974d277d6659aaada321b2a7e7a604df78a7bd
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761321"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="a48d4-101">1 つのモニターの外部に拡張すると、クリッピングなしで WPF ウィンドウがレンダリングされる</span><span class="sxs-lookup"><span data-stu-id="a48d4-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a48d4-102">説明</span><span class="sxs-lookup"><span data-stu-id="a48d4-102">Details</span></span>|<span data-ttu-id="a48d4-103">Windows 8 以上で実行している .NET Framework 4.6 では、マルチ モニターのシナリオで 1 つのディスプレイの外部にウィンドウを拡張すると、ウィンドウ全体がクリッピングなしでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="a48d4-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="a48d4-104">これは、1 つのディスプレイを超える WPF ウィンドウをクリッピングする、以前のバージョンの .NET Framework とは異なります。</span><span class="sxs-lookup"><span data-stu-id="a48d4-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>|
|<span data-ttu-id="a48d4-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a48d4-105">Suggestion</span></span>|<span data-ttu-id="a48d4-106">この動作 (クリッピングするかどうか) は、アプリケーションの構成ファイルの <code>&lt;appSettings&gt;</code> で <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> 要素を使用するか、アプリの起動時に <code>EnableMultiMonitorDisplayClipping</code> プロパティを設定することで明示的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="a48d4-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>|
|<span data-ttu-id="a48d4-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="a48d4-107">Scope</span></span>|<span data-ttu-id="a48d4-108">マイナー</span><span class="sxs-lookup"><span data-stu-id="a48d4-108">Minor</span></span>|
|<span data-ttu-id="a48d4-109">Version</span><span class="sxs-lookup"><span data-stu-id="a48d4-109">Version</span></span>|<span data-ttu-id="a48d4-110">4.6</span><span class="sxs-lookup"><span data-stu-id="a48d4-110">4.6</span></span>|
|<span data-ttu-id="a48d4-111">型</span><span class="sxs-lookup"><span data-stu-id="a48d4-111">Type</span></span>|<span data-ttu-id="a48d4-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="a48d4-112">Runtime</span></span>|

