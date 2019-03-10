---
title: DataGridView コントロールのアーキテクチャ (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: d215eeaa367156c6228615a8f6e0a7f889efdf60
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713814"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="37d3a-102">DataGridView コントロールのアーキテクチャ (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="37d3a-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="37d3a-103"><xref:System.Windows.Forms.DataGridView>コントロールとその関連クラスが表示および表形式のデータを編集するための柔軟で拡張性の高いシステムで設計されています。</span><span class="sxs-lookup"><span data-stu-id="37d3a-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="37d3a-104">これらのクラスがすべてに含まれる、<xref:System.Windows.Forms?displayProperty=nameWithType>名前空間、およびそれらのすべてが"DataGridView"プレフィックスを持つという名前です。</span><span class="sxs-lookup"><span data-stu-id="37d3a-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="37d3a-105">アーキテクチャの要素</span><span class="sxs-lookup"><span data-stu-id="37d3a-105">Architecture Elements</span></span>  
 <span data-ttu-id="37d3a-106">プライマリ<xref:System.Windows.Forms.DataGridView>コンパニオン クラスから派生<xref:System.Windows.Forms.DataGridViewElement>します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="37d3a-107">次のオブジェクト モデルを示しています、<xref:System.Windows.Forms.DataGridViewElement>継承階層。</span><span class="sxs-lookup"><span data-stu-id="37d3a-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="37d3a-108">![DataGridViewElement オブジェクト モデル](./media/datagridviewelement.gif "DataGridViewElement")</span><span class="sxs-lookup"><span data-stu-id="37d3a-108">![DataGridViewElement Object Model](./media/datagridviewelement.gif "DataGridViewElement")</span></span>  
<span data-ttu-id="37d3a-109">DataGridViewElement オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="37d3a-109">DataGridViewElement object model</span></span>  
  
 <span data-ttu-id="37d3a-110"><xref:System.Windows.Forms.DataGridViewElement>クラスは、親への参照を提供<xref:System.Windows.Forms.DataGridView>コントロールであり、<xref:System.Windows.Forms.DataGridViewElement.State%2A>プロパティの値の組み合わせを表す値を保持する、<xref:System.Windows.Forms.DataGridViewElementStates>列挙体。</span><span class="sxs-lookup"><span data-stu-id="37d3a-110">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="37d3a-111">次のセクションで説明します、<xref:System.Windows.Forms.DataGridView>コンパニオン クラスで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-111">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="37d3a-112">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="37d3a-112">DataGridViewElementStates</span></span>  
 <span data-ttu-id="37d3a-113"><xref:System.Windows.Forms.DataGridViewElementStates>列挙には、次の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="37d3a-113">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="37d3a-114">この列挙体の値はビットごとの論理演算子と組み合わせることができますので、<xref:System.Windows.Forms.DataGridViewElement.State%2A>プロパティは、一度に 1 つ以上の状態を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="37d3a-114">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="37d3a-115">たとえば、<xref:System.Windows.Forms.DataGridViewElement>同時に実行できる<xref:System.Windows.Forms.DataGridViewElementStates.Frozen>、<xref:System.Windows.Forms.DataGridViewElementStates.Selected>と<xref:System.Windows.Forms.DataGridViewElementStates.Visible>します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-115">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="37d3a-116">セルとバンド</span><span class="sxs-lookup"><span data-stu-id="37d3a-116">Cells and Bands</span></span>  
 <span data-ttu-id="37d3a-117"><xref:System.Windows.Forms.DataGridView>コントロールには 2 つの基本的な種類のオブジェクトが構成されます。 セルとバンド。</span><span class="sxs-lookup"><span data-stu-id="37d3a-117">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="37d3a-118">すべてのセルから派生して、<xref:System.Windows.Forms.DataGridViewCell>基本クラス。</span><span class="sxs-lookup"><span data-stu-id="37d3a-118">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="37d3a-119">2 つの種類、バンドの<xref:System.Windows.Forms.DataGridViewColumn>と<xref:System.Windows.Forms.DataGridViewRow>から派生両方、<xref:System.Windows.Forms.DataGridViewBand>基本クラス。</span><span class="sxs-lookup"><span data-stu-id="37d3a-119">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="37d3a-120"><xref:System.Windows.Forms.DataGridView>コントロールがいくつかのクラスと相互運用が、最も一般的に見られるは<xref:System.Windows.Forms.DataGridViewCell>、 <xref:System.Windows.Forms.DataGridViewColumn>、および<xref:System.Windows.Forms.DataGridViewRow>します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-120">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="37d3a-121">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="37d3a-121">DataGridViewCell</span></span>  
 <span data-ttu-id="37d3a-122">セルがの相互作用の基本的な単位、<xref:System.Windows.Forms.DataGridView>します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-122">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="37d3a-123">表示が、セルの中央に配置し、多くの場合、データ エントリはセルを実行します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-123">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="37d3a-124">使用してセルにアクセスすることができます、<xref:System.Windows.Forms.DataGridViewRow.Cells%2A>のコレクション、<xref:System.Windows.Forms.DataGridViewRow>を使用して、選択したセルにアクセスできるクラスとする、<xref:System.Windows.Forms.DataGridView.SelectedCells%2A>のコレクション、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="37d3a-124">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="37d3a-125">この使用方法とを示しています、次のオブジェクト モデル、<xref:System.Windows.Forms.DataGridViewCell>継承階層。</span><span class="sxs-lookup"><span data-stu-id="37d3a-125">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="37d3a-126">![DataGridViewCell オブジェクト モデル](./media/datagridviewcell.gif "DataGridViewCell")</span><span class="sxs-lookup"><span data-stu-id="37d3a-126">![DataGridViewCell Object Model](./media/datagridviewcell.gif "DataGridViewCell")</span></span>  
<span data-ttu-id="37d3a-127">DataGridViewCell オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="37d3a-127">DataGridViewCell object model</span></span>  
  
 <span data-ttu-id="37d3a-128"><xref:System.Windows.Forms.DataGridViewCell>型はすべてのセルの型の派生元となる抽象基本クラス。</span><span class="sxs-lookup"><span data-stu-id="37d3a-128">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="37d3a-129"><xref:System.Windows.Forms.DataGridViewCell> その派生型は、Windows フォーム コントロールが一部のホスト Windows フォーム コントロール。</span><span class="sxs-lookup"><span data-stu-id="37d3a-129"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="37d3a-130">セルの数式でサポートされている編集機能は通常、ホストされるコントロールによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="37d3a-130">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="37d3a-131"><xref:System.Windows.Forms.DataGridViewCell> オブジェクトは制御されません、独自の外観と描画機能と同じ方法で Windows フォーム コントロールとして。</span><span class="sxs-lookup"><span data-stu-id="37d3a-131"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="37d3a-132">代わりに、<xref:System.Windows.Forms.DataGridView>の外観は、その<xref:System.Windows.Forms.DataGridViewCell>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="37d3a-132">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="37d3a-133">操作することで大幅にセルの動作と外観に影響することができます、<xref:System.Windows.Forms.DataGridView>コントロールのプロパティおよびイベント。</span><span class="sxs-lookup"><span data-stu-id="37d3a-133">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="37d3a-134">機能を超えているカスタマイズ用の特別な要件がある場合、<xref:System.Windows.Forms.DataGridView>コントロールから派生した独自のクラスを実装する<xref:System.Windows.Forms.DataGridViewCell>またはその子クラスの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="37d3a-134">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="37d3a-135">次の一覧から派生したクラスを示しています<xref:System.Windows.Forms.DataGridViewCell>:。</span><span class="sxs-lookup"><span data-stu-id="37d3a-135">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   <span data-ttu-id="37d3a-136">カスタムのセルの種類を</span><span class="sxs-lookup"><span data-stu-id="37d3a-136">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="37d3a-137">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="37d3a-137">DataGridViewColumn</span></span>  
 <span data-ttu-id="37d3a-138">スキーマ、<xref:System.Windows.Forms.DataGridView>でコントロールの接続されたデータ ストアが表される、<xref:System.Windows.Forms.DataGridView>コントロールの列。</span><span class="sxs-lookup"><span data-stu-id="37d3a-138">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="37d3a-139">アクセスできる、<xref:System.Windows.Forms.DataGridView>コントロールの列を使用して、<xref:System.Windows.Forms.DataGridView.Columns%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="37d3a-139">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="37d3a-140">選択した列を使用してアクセスすることができます、<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="37d3a-140">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="37d3a-141">この使用方法とを示しています、次のオブジェクト モデル、<xref:System.Windows.Forms.DataGridViewColumn>継承階層。</span><span class="sxs-lookup"><span data-stu-id="37d3a-141">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="37d3a-142">![DataGridViewColumn オブジェクト モデル](./media/datagridviewcolumn.gif "DataGridViewColumn")</span><span class="sxs-lookup"><span data-stu-id="37d3a-142">![DataGridViewColumn Object Model](./media/datagridviewcolumn.gif "DataGridViewColumn")</span></span>  
<span data-ttu-id="37d3a-143">DataGridViewColumn オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="37d3a-143">DataGridViewColumn object model</span></span>  
  
 <span data-ttu-id="37d3a-144">一部のキーのセルの種類はある対応する列の種類です。</span><span class="sxs-lookup"><span data-stu-id="37d3a-144">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="37d3a-145">これらから派生、<xref:System.Windows.Forms.DataGridViewColumn>基本クラス。</span><span class="sxs-lookup"><span data-stu-id="37d3a-145">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="37d3a-146">次の一覧から派生したクラスを示しています<xref:System.Windows.Forms.DataGridViewColumn>:。</span><span class="sxs-lookup"><span data-stu-id="37d3a-146">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   <span data-ttu-id="37d3a-147">カスタム列の型</span><span class="sxs-lookup"><span data-stu-id="37d3a-147">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="37d3a-148">DataGridView 編集コントロール</span><span class="sxs-lookup"><span data-stu-id="37d3a-148">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="37d3a-149">通常は高度な編集機能をサポートしているセルは、Windows フォーム コントロールから派生したホストされるコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-149">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="37d3a-150">これらのコントロールの実装も、<xref:System.Windows.Forms.IDataGridViewEditingControl>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="37d3a-150">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="37d3a-151">次のオブジェクト モデルでは、これらのコントロールの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-151">The following object model illustrates the usage of these controls.</span></span>  
  
 <span data-ttu-id="37d3a-152">![DataGridView コントロールのオブジェクト モデルを編集](./media/datagridviewediting.gif "DataGridViewEditing")</span><span class="sxs-lookup"><span data-stu-id="37d3a-152">![DataGridView Editing Control Object Model](./media/datagridviewediting.gif "DataGridViewEditing")</span></span>  
<span data-ttu-id="37d3a-153">DataGridView 編集コントロール オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="37d3a-153">DataGridView editing control object model</span></span>  
  
 <span data-ttu-id="37d3a-154">次の編集コントロールが付属、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="37d3a-154">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="37d3a-155">独自の編集コントロールを作成する方法の詳細については、次を参照してください。[方法。Windows フォーム DataGridView Cells コントロールをホスト](how-to-host-controls-in-windows-forms-datagridview-cells.md)します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-155">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="37d3a-156">次の表は、セルの種類を列の種類、および編集コントロール間の関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="37d3a-156">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="37d3a-157">セルの種類</span><span class="sxs-lookup"><span data-stu-id="37d3a-157">Cell type</span></span>|<span data-ttu-id="37d3a-158">ホストされるコントロール</span><span class="sxs-lookup"><span data-stu-id="37d3a-158">Hosted control</span></span>|<span data-ttu-id="37d3a-159">列の型</span><span class="sxs-lookup"><span data-stu-id="37d3a-159">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="37d3a-160">N/A</span><span class="sxs-lookup"><span data-stu-id="37d3a-160">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="37d3a-161">該当なし</span><span class="sxs-lookup"><span data-stu-id="37d3a-161">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="37d3a-162">該当なし</span><span class="sxs-lookup"><span data-stu-id="37d3a-162">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="37d3a-163">N/A</span><span class="sxs-lookup"><span data-stu-id="37d3a-163">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="37d3a-164">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="37d3a-164">DataGridViewRow</span></span>  
 <span data-ttu-id="37d3a-165"><xref:System.Windows.Forms.DataGridViewRow>をクラスの表示、レコードのデータ フィールドのデータを格納、<xref:System.Windows.Forms.DataGridView>コントロールをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="37d3a-165">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="37d3a-166">アクセスできる、<xref:System.Windows.Forms.DataGridView>コントロールの行を使用して、<xref:System.Windows.Forms.DataGridView.Rows%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="37d3a-166">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="37d3a-167">選択した行を使用してアクセスすることができます、<xref:System.Windows.Forms.DataGridView.SelectedRows%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="37d3a-167">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="37d3a-168">この使用方法とを示しています、次のオブジェクト モデル、<xref:System.Windows.Forms.DataGridViewRow>継承階層。</span><span class="sxs-lookup"><span data-stu-id="37d3a-168">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="37d3a-169">![DataGridViewRow オブジェクト モデル](./media/datagridviewrow.gif "DataGridViewRow")</span><span class="sxs-lookup"><span data-stu-id="37d3a-169">![DataGridViewRow Object Model](./media/datagridviewrow.gif "DataGridViewRow")</span></span>  
<span data-ttu-id="37d3a-170">DataGridViewRow オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="37d3a-170">DataGridViewRow object model</span></span>  
  
 <span data-ttu-id="37d3a-171">独自の型を派生させることができます、<xref:System.Windows.Forms.DataGridViewRow>クラスが、これは通常不要になります。</span><span class="sxs-lookup"><span data-stu-id="37d3a-171">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="37d3a-172"><xref:System.Windows.Forms.DataGridView>コントロールがいくつかの行に関連するイベントおよびプロパティの動作をカスタマイズするため、<xref:System.Windows.Forms.DataGridViewRow>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="37d3a-172">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="37d3a-173">有効にした場合、<xref:System.Windows.Forms.DataGridView>コントロールの<xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>プロパティ、新しい行を追加するための特別な行は、最後の行として表示されます。</span><span class="sxs-lookup"><span data-stu-id="37d3a-173">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="37d3a-174">この行の一部である、<xref:System.Windows.Forms.DataGridView.Rows%2A>が、コレクションが特別な機能に対処することがあります。</span><span class="sxs-lookup"><span data-stu-id="37d3a-174">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="37d3a-175">詳細については、次を参照してください。 [Windows フォームの DataGridView コントロールにおける新規レコードの行を使用して](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="37d3a-175">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d3a-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="37d3a-176">See also</span></span>
- [<span data-ttu-id="37d3a-177">DataGridView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="37d3a-177">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="37d3a-178">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="37d3a-178">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="37d3a-179">Windows フォーム DataGridView コントロールにおける新規レコード行の使用</span><span class="sxs-lookup"><span data-stu-id="37d3a-179">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
