---
ms.openlocfilehash: 297af393e86c65e84ea7271d98eab36dbc6dbb0e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774477"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="94c43-101">一部の WorkFlow ドラッグ アンド ドロップ API が廃止されました</span><span class="sxs-lookup"><span data-stu-id="94c43-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="94c43-102">説明</span><span class="sxs-lookup"><span data-stu-id="94c43-102">Details</span></span>|<span data-ttu-id="94c43-103">この WorkFlow ドラッグ アンド ドロップ API は廃止され、アプリが 4.5 向けにリビルドされた場合、コンパイラ警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="94c43-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>|
|<span data-ttu-id="94c43-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="94c43-104">Suggestion</span></span>|<span data-ttu-id="94c43-105">複数オブジェクトでの操作をサポートする新しい <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name> API を代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c43-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="94c43-106">または、ビルド警告を抑制するか、古いコンパイラを使用して警告を回避できます。</span><span class="sxs-lookup"><span data-stu-id="94c43-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="94c43-107">API は、まだサポートされています。</span><span class="sxs-lookup"><span data-stu-id="94c43-107">The APIs are still supported.</span></span>|
|<span data-ttu-id="94c43-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="94c43-108">Scope</span></span>|<span data-ttu-id="94c43-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="94c43-109">Minor</span></span>|
|<span data-ttu-id="94c43-110">Version</span><span class="sxs-lookup"><span data-stu-id="94c43-110">Version</span></span>|<span data-ttu-id="94c43-111">4.5</span><span class="sxs-lookup"><span data-stu-id="94c43-111">4.5</span></span>|
|<span data-ttu-id="94c43-112">型</span><span class="sxs-lookup"><span data-stu-id="94c43-112">Type</span></span>|<span data-ttu-id="94c43-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="94c43-113">Retargeting</span></span>|
|<span data-ttu-id="94c43-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="94c43-114">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType></li></ul>|
