---
title: Model-View-View Model を利用した汎用性のあるクラス ライブラリの使用
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d2f07e471d4f0173f768b0d2a463d756b5be0682
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45625849"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="187cf-102">Model-View-View Model を利用した汎用性のあるクラス ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="187cf-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="187cf-103">.NET Framework を使用して[ポータブル クラス ライブラリ](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)モデル-ビュー-ビュー モデル (MVVM) パターンを実装して、複数のプラットフォームでアセンブリを共有します。</span><span class="sxs-lookup"><span data-stu-id="187cf-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>  

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="187cf-104">MVVM では、基になるビジネス ロジックからユーザー インターフェイスを分離するアプリケーション パターンです。</span><span class="sxs-lookup"><span data-stu-id="187cf-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="187cf-105">モデルとビュー モデル クラスを実装することができます、[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]プロジェクト[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]、し、さまざまなプラットフォーム用にカスタマイズされたビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="187cf-105">You can implement the model and view model classes in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], and then create views that are customized for different platforms.</span></span> <span data-ttu-id="187cf-106">このアプローチでは、データを記述できます。 モデルとビジネス ロジックを 1 回だけ、.NET Framework、Silverlight、Windows Phone のコードを使用および[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]アプリは、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="187cf-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="187cf-107">![MVVM のダイアグラムを含むポータブル](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span><span class="sxs-lookup"><span data-stu-id="187cf-107">![Portable with MVVM diagram](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span></span>  
  
 <span data-ttu-id="187cf-108">このトピックでは、MVVM パターンに関する一般的な情報は提供されません。</span><span class="sxs-lookup"><span data-stu-id="187cf-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="187cf-109">使用する方法についての情報を提供するだけ[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]MVVM を実装します。</span><span class="sxs-lookup"><span data-stu-id="187cf-109">It only provides information about how to use [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] to implement MVVM.</span></span> <span data-ttu-id="187cf-110">MVVM の詳細については、次を参照してください。、 [MVVM のクイック スタート](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="187cf-110">For more information about MVVM, see the [MVVM Quickstart](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).</span></span>  
  
## <a name="classes-that-support-mvvm"></a><span data-ttu-id="187cf-111">MVVM をサポートするクラス</span><span class="sxs-lookup"><span data-stu-id="187cf-111">Classes That Support MVVM</span></span>  
 <span data-ttu-id="187cf-112">対象とする場合、 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]、 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]、Silverlight、または Windows Phone 7.5 for、[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]プロジェクトでは、次のクラスは MVVM パターンを実装するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="187cf-112">When you target the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, the following classes are available for implementing the MVVM pattern:</span></span>  
  
-   <span data-ttu-id="187cf-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="187cf-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="187cf-123">すべてのクラス、<xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType>名前空間</span><span class="sxs-lookup"><span data-stu-id="187cf-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>  
  
## <a name="implementing-mvvm"></a><span data-ttu-id="187cf-124">MVVM の実装</span><span class="sxs-lookup"><span data-stu-id="187cf-124">Implementing MVVM</span></span>  
 <span data-ttu-id="187cf-125">MVVM を実装するために通常作成モデルとでは、ビュー モデルの両方を[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]、ため、プロジェクト、[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]プロジェクトがポータブルでないプロジェクトを参照できません。</span><span class="sxs-lookup"><span data-stu-id="187cf-125">To implement MVVM, you typically create both the model and the view model in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, because a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project cannot reference a non-portable project.</span></span> <span data-ttu-id="187cf-126">モデルとビュー モデルは、同じプロジェクト内、または別のプロジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="187cf-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="187cf-127">個別のプロジェクトを使用する場合は、モデル プロジェクトにビューのモデル プロジェクトからの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="187cf-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>  
  
 <span data-ttu-id="187cf-128">モデルをコンパイルし、モデル プロジェクトを表示すると後、は、ビューを含むアプリでそれらのアセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="187cf-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="187cf-129">ビューは、ビュー モデルとのみやり取りをする場合のみ、ビュー モデルを含むアセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="187cf-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>  
  
### <a name="model"></a><span data-ttu-id="187cf-130">モデル</span><span class="sxs-lookup"><span data-stu-id="187cf-130">Model</span></span>  
 <span data-ttu-id="187cf-131">次の例にある単純なモデル クラスを示しています、[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="187cf-131">The following example shows a simplified model class that could reside in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 <span data-ttu-id="187cf-132">次の例では、設定、取得、およびデータを更新する簡単な方法を示しています、[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="187cf-132">The following example shows a simple way to populate, retrieve, and update the data in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span> <span data-ttu-id="187cf-133">実際のアプリでは、Windows Communication Foundation (WCF) サービスなどのソースからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="187cf-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a><span data-ttu-id="187cf-134">ビュー モデル</span><span class="sxs-lookup"><span data-stu-id="187cf-134">View Model</span></span>  
 <span data-ttu-id="187cf-135">MVVM パターンを実装するときに、ビュー モデルの基本クラスが頻繁に追加されます。</span><span class="sxs-lookup"><span data-stu-id="187cf-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="187cf-136">次の例では、基本クラスを示します。</span><span class="sxs-lookup"><span data-stu-id="187cf-136">The following example shows a base class.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 <span data-ttu-id="187cf-137">実装、<xref:System.Windows.Input.ICommand>インターフェイスは、MVVM パターンでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="187cf-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="187cf-138"><xref:System.Windows.Input.ICommand> インターフェイスを実装する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="187cf-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 <span data-ttu-id="187cf-139">次の例では、簡略化されたビュー モデルを示します。</span><span class="sxs-lookup"><span data-stu-id="187cf-139">The following example shows a simplified view model.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="187cf-140">表示</span><span class="sxs-lookup"><span data-stu-id="187cf-140">View</span></span>  
 <span data-ttu-id="187cf-141">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]アプリ、[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]アプリ、Silverlight ベースのアプリまたは Windows Phone 7.5 アプリの場合は、モデルとビュー モデル プロジェクトを含むアセンブリを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="187cf-141">From a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="187cf-142">対話するビューを作成するには、ビュー モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="187cf-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="187cf-143">取得し、ビュー モデルからデータを更新する Windows Presentation Foundation (WPF) アプリを簡略化されたは、次の例です。</span><span class="sxs-lookup"><span data-stu-id="187cf-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="187cf-144">Windows Phone、Silverlight で同様のビューを作成または[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]アプリ。</span><span class="sxs-lookup"><span data-stu-id="187cf-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="187cf-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="187cf-145">See also</span></span>

- [<span data-ttu-id="187cf-146">ポータブル クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="187cf-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
