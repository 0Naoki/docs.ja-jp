---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760637"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="4a40a-101">ローカライズされたビルドで RibbonGroup の背景が透明に設定される</span><span class="sxs-lookup"><span data-stu-id="4a40a-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4a40a-102">説明</span><span class="sxs-lookup"><span data-stu-id="4a40a-102">Details</span></span>|<span data-ttu-id="4a40a-103">ローカライズされたビルドの <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> の背景が常に透明のブラシで塗りつぶされており、UI の操作性が低下していました。</span><span class="sxs-lookup"><span data-stu-id="4a40a-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="4a40a-104">これは、.NET Framework 4.7 WPF 修正プログラムで修正されます。<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> のローカライズされたリソースが更新され、正しいブラシが確実に選択されるようになります。</span><span class="sxs-lookup"><span data-stu-id="4a40a-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="4a40a-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4a40a-105">Suggestion</span></span>|<span data-ttu-id="4a40a-106">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="4a40a-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="4a40a-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="4a40a-107">Scope</span></span>|<span data-ttu-id="4a40a-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="4a40a-108">Edge</span></span>|
|<span data-ttu-id="4a40a-109">Version</span><span class="sxs-lookup"><span data-stu-id="4a40a-109">Version</span></span>|<span data-ttu-id="4a40a-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="4a40a-110">4.6.2</span></span>|
|<span data-ttu-id="4a40a-111">型</span><span class="sxs-lookup"><span data-stu-id="4a40a-111">Type</span></span>|<span data-ttu-id="4a40a-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="4a40a-112">Runtime</span></span>|

