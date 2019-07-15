---
ms.openlocfilehash: 2674edc595d8e4e1e4c2ee42b39aa59265127462
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803166"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="65814-101">カスタム DataTemplate を使用しているとき、断続的に、ItemsControl (ListBox や DataGrid など) 内の最後の項目までスクロールできない</span><span class="sxs-lookup"><span data-stu-id="65814-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

|   |   |
|---|---|
|<span data-ttu-id="65814-102">説明</span><span class="sxs-lookup"><span data-stu-id="65814-102">Details</span></span>|<span data-ttu-id="65814-103">場合によっては、.NET Framework 4.5 のバグにより、カスタム DataTemplate を使用していると、ItemsControl (<xref:System.Windows.Controls.ListBox?displayProperty=name>、<xref:System.Windows.Controls.ComboBox?displayProperty=name>、<xref:System.Windows.Controls.DataGrid?displayProperty=name> など) の最後の項目までスクロールできません。</span><span class="sxs-lookup"><span data-stu-id="65814-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=name>, <xref:System.Windows.Controls.ComboBox?displayProperty=name>, <xref:System.Windows.Controls.DataGrid?displayProperty=name>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="65814-104">(上へスクロールした後で) もう一度スクロールを試みると、今度はスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="65814-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>|
|<span data-ttu-id="65814-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="65814-105">Suggestion</span></span>|<span data-ttu-id="65814-106">この問題は .NET Framework 4.5.2 で修正されたため、このバージョン (またはそれ以降のバージョン) の .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="65814-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="65814-107">または、ユーザーは、スクロール バーをこれらのコレクションの最後の項目までドラッグできますが、2 回試みなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="65814-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>|
|<span data-ttu-id="65814-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="65814-108">Scope</span></span>|<span data-ttu-id="65814-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="65814-109">Minor</span></span>|
|<span data-ttu-id="65814-110">Version</span><span class="sxs-lookup"><span data-stu-id="65814-110">Version</span></span>|<span data-ttu-id="65814-111">4.5</span><span class="sxs-lookup"><span data-stu-id="65814-111">4.5</span></span>|
|<span data-ttu-id="65814-112">型</span><span class="sxs-lookup"><span data-stu-id="65814-112">Type</span></span>|<span data-ttu-id="65814-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="65814-113">Runtime</span></span>|

