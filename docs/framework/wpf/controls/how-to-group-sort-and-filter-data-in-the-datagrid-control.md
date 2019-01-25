---
title: '方法: グループ化、並べ替え、およびデータ グリッド コントロールでデータをフィルター処理'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: f0f80afd982092248bc52590e072c92784dbcbce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650458"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="a9ff2-102">方法: グループ、並べ替え、およびデータ グリッド コントロールでデータのフィルター選択</span><span class="sxs-lookup"><span data-stu-id="a9ff2-102">How to: Group, sort, and filter data in the DataGrid control</span></span>

<span data-ttu-id="a9ff2-103">内のデータを表示すると便利です、<xref:System.Windows.Controls.DataGrid>でさまざまな方法でグループ化、並べ替え、およびデータのフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="a9ff2-104">グループ化、並べ替え、およびデータをフィルター処理、<xref:System.Windows.Controls.DataGrid>にバインドする、<xref:System.Windows.Data.CollectionView>これらの関数をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="a9ff2-105">内のデータを操作することができますし、<xref:System.Windows.Data.CollectionView>基になるソース データには影響しません。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="a9ff2-106">コレクション ビューの変更に反映されます、<xref:System.Windows.Controls.DataGrid>ユーザー インターフェイス (UI)。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>

<span data-ttu-id="a9ff2-107"><xref:System.Windows.Data.CollectionView>クラスには、グループ化と並べ替えを実装するデータ ソースの機能が用意されています、<xref:System.Collections.IEnumerable>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="a9ff2-108"><xref:System.Windows.Data.CollectionViewSource>クラスでは、プロパティを設定することができます、 <xref:System.Windows.Data.CollectionView> XAML から。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>

<span data-ttu-id="a9ff2-109">この例では、コレクションで`Task`にオブジェクトがバインドされている、<xref:System.Windows.Data.CollectionViewSource>します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="a9ff2-110"><xref:System.Windows.Data.CollectionViewSource>として提供される、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>の<xref:System.Windows.Controls.DataGrid>します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="a9ff2-111">グループ化、並べ替え、およびフィルター処理を実行、<xref:System.Windows.Data.CollectionViewSource>に表示されると、 <xref:System.Windows.Controls.DataGrid> UI。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>

<span data-ttu-id="a9ff2-112">![データ グリッド内のデータをグループ化](./media/wpf-datagridgroups.png "WPF_DataGridGroups")データ グリッド内のデータをグループ化</span><span class="sxs-lookup"><span data-stu-id="a9ff2-112">![Grouped data in a DataGrid](./media/wpf-datagridgroups.png "WPF_DataGridGroups") Grouped data in a DataGrid</span></span>

## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="a9ff2-113">ItemsSource として、CollectionViewSource を使用します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-113">Using a CollectionViewSource as an ItemsSource</span></span>

<span data-ttu-id="a9ff2-114">グループ、並べ替え、およびデータのフィルター処理する、<xref:System.Windows.Controls.DataGrid>コントロールをバインドする、<xref:System.Windows.Controls.DataGrid>を<xref:System.Windows.Data.CollectionView>これらの関数をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-114">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="a9ff2-115">この例で、<xref:System.Windows.Controls.DataGrid>にバインドされて、<xref:System.Windows.Data.CollectionViewSource>のこれらの関数を提供する、<xref:System.Collections.Generic.List%601>の`Task`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-115">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="a9ff2-116">データ グリッドを CollectionViewSource にバインドするには</span><span class="sxs-lookup"><span data-stu-id="a9ff2-116">To bind a DataGrid to a CollectionViewSource</span></span>

1. <span data-ttu-id="a9ff2-117">実装するデータ コレクションを作成、<xref:System.Collections.IEnumerable>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-117">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>

    <span data-ttu-id="a9ff2-118">使用する場合<xref:System.Collections.Generic.List%601>、コレクションを作成するから継承する新しいクラスを作成する必要があります<xref:System.Collections.Generic.List%601>のインスタンスをインスタンス化ではなく<xref:System.Collections.Generic.List%601>します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-118">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="a9ff2-119">これにより、XAML 内のコレクションにデータをバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-119">This enables you to data bind to the collection in XAML.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a9ff2-120">コレクション内のオブジェクトを実装する必要があります、<xref:System.ComponentModel.INotifyPropertyChanged>変更されたインターフェイスと<xref:System.ComponentModel.IEditableObject>インターフェイスの順序で、<xref:System.Windows.Controls.DataGrid>プロパティの変更と編集に正しく応答します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-120">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="a9ff2-121">詳細については、「[プロパティの変更通知を実装する](../data/how-to-implement-property-change-notification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-121">For more information, see [Implement Property Change Notification](../data/how-to-implement-property-change-notification.md).</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. <span data-ttu-id="a9ff2-122">XAML コレクション クラスのインスタンスを作成し、設定、 [X:key ディレクティブ](../../../../docs/framework/xaml-services/x-key-directive.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-122">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md).</span></span>

3. <span data-ttu-id="a9ff2-123">XAML でのインスタンスを作成、<xref:System.Windows.Data.CollectionViewSource>クラス、設定、 [X:key ディレクティブ](../../../../docs/framework/xaml-services/x-key-directive.md)、として、コレクション クラスのインスタンスを設定し、 <xref:System.Windows.Data.CollectionViewSource.Source%2A>。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-123">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. <span data-ttu-id="a9ff2-124">インスタンスを作成、<xref:System.Windows.Controls.DataGrid>クラスし、設定、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>プロパティを<xref:System.Windows.Data.CollectionViewSource>します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-124">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. <span data-ttu-id="a9ff2-125">アクセスする、 <xref:System.Windows.Data.CollectionViewSource> 、コードから使用して、<xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A>への参照を取得するメソッド、<xref:System.Windows.Data.CollectionViewSource>します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-125">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="a9ff2-126">データ グリッド内の項目をグループ化</span><span class="sxs-lookup"><span data-stu-id="a9ff2-126">Grouping items in a DataGrid</span></span>

<span data-ttu-id="a9ff2-127">項目をグループ化する方法を指定する、<xref:System.Windows.Controls.DataGrid>を使用する、<xref:System.Windows.Data.PropertyGroupDescription>ソース ビュー内の項目をグループ化する型。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-127">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>

### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="a9ff2-128">XAML を使用してデータ グリッド内の項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="a9ff2-128">To group items in a DataGrid using XAML</span></span>

1. <span data-ttu-id="a9ff2-129">作成、<xref:System.Windows.Data.PropertyGroupDescription>でグループ化するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-129">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="a9ff2-130">XAML またはコードでプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-130">You can specify the property in XAML or in code.</span></span>

   1. <span data-ttu-id="a9ff2-131">XAML、設定、<xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A>でグループ化するプロパティの名前にします。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-131">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>

   2. <span data-ttu-id="a9ff2-132">コードでは、コンス トラクターにグループ化するプロパティの名前を渡します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-132">In code, pass the name of the property to group by to the constructor.</span></span>

2. <span data-ttu-id="a9ff2-133">追加、<xref:System.Windows.Data.PropertyGroupDescription>を<xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType>コレクション。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-133">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="a9ff2-134">インスタンスを追加<xref:System.Windows.Data.PropertyGroupDescription>を<xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>複数レベルのグループ化を追加するコレクション。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-134">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. <span data-ttu-id="a9ff2-135">グループを削除するには、削除、<xref:System.Windows.Data.PropertyGroupDescription>から、<xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-135">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>

5. <span data-ttu-id="a9ff2-136">すべてのグループを削除するには、呼び出し、<xref:System.Collections.ObjectModel.Collection%601.Clear%2A>のメソッド、<xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-136">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

<span data-ttu-id="a9ff2-137">項目をグループ化するときに、 <xref:System.Windows.Controls.DataGrid>、定義することができます、<xref:System.Windows.Controls.GroupStyle>各グループの外観を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-137">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="a9ff2-138">適用する、<xref:System.Windows.Controls.GroupStyle>に追加することによって、 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> DataGrid のコレクション。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-138">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="a9ff2-139">複数のレベルのグループ化した場合は、グループ レベルごとに異なるスタイルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-139">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="a9ff2-140">スタイルが定義されている順序で適用されます。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-140">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="a9ff2-141">たとえば、2 つのスタイルを定義する場合、最初適用して、最上位レベルの行グループには。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-141">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="a9ff2-142">2 番目のスタイルは、2 番目のレベルですべての行グループに適用されると下限になります。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-142">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="a9ff2-143"><xref:System.Windows.FrameworkElement.DataContext%2A>の<xref:System.Windows.Controls.GroupStyle>は、<xref:System.Windows.Data.CollectionViewGroup>グループを表す。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-143">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>

### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="a9ff2-144">行グループ ヘッダーの外観を変更するには</span><span class="sxs-lookup"><span data-stu-id="a9ff2-144">To change the appearance of row group headers</span></span>

1. <span data-ttu-id="a9ff2-145">作成、<xref:System.Windows.Controls.GroupStyle>行グループの外観を定義します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-145">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>

2. <span data-ttu-id="a9ff2-146">配置、<xref:System.Windows.Controls.GroupStyle>内で、`<DataGrid.GroupStyle>`タグ。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-146">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="a9ff2-147">データ グリッド内の項目を並べ替え</span><span class="sxs-lookup"><span data-stu-id="a9ff2-147">Sorting items in a DataGrid</span></span>

<span data-ttu-id="a9ff2-148">項目の並べ替え方法を指定する、<xref:System.Windows.Controls.DataGrid>を使用する、<xref:System.ComponentModel.SortDescription>ソース ビューの項目を並べ替える型。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-148">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>

### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="a9ff2-149">DataGrid の項目を並べ替える</span><span class="sxs-lookup"><span data-stu-id="a9ff2-149">To sort items in a DataGrid</span></span>

1. <span data-ttu-id="a9ff2-150">作成、<xref:System.ComponentModel.SortDescription>を並べ替えるには、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-150">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="a9ff2-151">XAML またはコードでプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-151">You can specify the property in XAML or in code.</span></span>

    1. <span data-ttu-id="a9ff2-152">XAML では、設定、<xref:System.ComponentModel.SortDescription.PropertyName%2A>を並べ替えるには、プロパティの名前にします。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-152">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>

    2. <span data-ttu-id="a9ff2-153">コードを並べ替えるにはプロパティの名前を渡すと、<xref:System.ComponentModel.ListSortDirection>コンス トラクターにします。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-153">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>

2. <span data-ttu-id="a9ff2-154">追加、<xref:System.ComponentModel.SortDescription>を<xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType>コレクション。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-154">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="a9ff2-155">インスタンスを追加<xref:System.ComponentModel.SortDescription>を<xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A>コレクションに追加のプロパティを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-155">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="a9ff2-156">データ グリッド内の項目をフィルター処理</span><span class="sxs-lookup"><span data-stu-id="a9ff2-156">Filtering items in a DataGrid</span></span>

<span data-ttu-id="a9ff2-157">項目をフィルター処理する、<xref:System.Windows.Controls.DataGrid>を使用して、 <xref:System.Windows.Data.CollectionViewSource>、用のハンドラーでフィルタ リング ロジックを提供する、<xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType>イベント。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-157">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>

### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="a9ff2-158">データ グリッド内の項目をフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="a9ff2-158">To filter items in a DataGrid</span></span>

1. <span data-ttu-id="a9ff2-159">ハンドラーを追加、<xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType>イベント。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-159">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>

2. <span data-ttu-id="a9ff2-160"><xref:System.Windows.Data.CollectionViewSource.Filter>イベント ハンドラーでは、フィルタ リング ロジックを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-160">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>

    <span data-ttu-id="a9ff2-161">ビューが更新されるたびに、フィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-161">The filter will be applied every time the view is refreshed.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

<span data-ttu-id="a9ff2-162">内の項目をフィルター処理する代わりに、<xref:System.Windows.Controls.DataGrid>フィルター処理のロジックと設定を提供するメソッドを作成して、<xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType>フィルターを適用するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-162">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="a9ff2-163">このメソッドの例を表示するには、次を参照してください。[ビュー内のフィルター データ](../data/how-to-filter-data-in-a-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-163">To see an example of this method, see [Filter Data in a View](../data/how-to-filter-data-in-a-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a9ff2-164">例</span><span class="sxs-lookup"><span data-stu-id="a9ff2-164">Example</span></span>

<span data-ttu-id="a9ff2-165">次の例は、グループ化、並べ替え、およびフィルター処理`Task`内のデータを<xref:System.Windows.Data.CollectionViewSource>表示、並べ替え、フィルターにグループ化、および`Task`内のデータを<xref:System.Windows.Controls.DataGrid>します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-165">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="a9ff2-166"><xref:System.Windows.Data.CollectionViewSource>として提供される、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>の<xref:System.Windows.Controls.DataGrid>します。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-166">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="a9ff2-167">グループ化、並べ替え、およびフィルター処理を実行、<xref:System.Windows.Data.CollectionViewSource>に表示されると、 <xref:System.Windows.Controls.DataGrid> UI。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-167">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>

<span data-ttu-id="a9ff2-168">この例をテストするには、プロジェクト名と一致する DGGroupSortFilterExample 名前を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-168">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="a9ff2-169">Visual Basic を使用している場合は、クラス名を変更する必要があります。<xref:System.Windows.Window>以下。</span><span class="sxs-lookup"><span data-stu-id="a9ff2-169">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a><span data-ttu-id="a9ff2-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9ff2-170">See also</span></span>

- [<span data-ttu-id="a9ff2-171">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="a9ff2-171">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="a9ff2-172">ObservableCollection を作成およびバインドする</span><span class="sxs-lookup"><span data-stu-id="a9ff2-172">Create and Bind to an ObservableCollection</span></span>](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [<span data-ttu-id="a9ff2-173">ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a9ff2-173">Filter Data in a View</span></span>](../data/how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="a9ff2-174">ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="a9ff2-174">Sort Data in a View</span></span>](../data/how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="a9ff2-175">XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="a9ff2-175">Sort and Group Data Using a View in XAML</span></span>](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
