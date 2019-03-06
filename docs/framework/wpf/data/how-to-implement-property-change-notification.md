---
title: '方法: プロパティの変更通知を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: 93a291b6dd35f9cc13c3c6f88aca5dc376b8bc1b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352751"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="16fc5-102">方法: プロパティの変更通知を実装する</span><span class="sxs-lookup"><span data-stu-id="16fc5-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="16fc5-103">（たとえば、ユーザーがフォームを編集したときに自動的にプレビューペインを更新する）バインディングの動的な変更を自動的にバインディングのターゲットとなるプロパティに反映するために、<xref:System.Windows.Data.BindingMode.OneWay>または<xref:System.Windows.Data.BindingMode.TwoWay>のバインディングをサポートするには、適切なプロパティ変更通知を提供しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="16fc5-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="16fc5-104">次の例は、<xref:System.ComponentModel.INotifyPropertyChanged>を実装するクラスの作り方を示します。</span><span class="sxs-lookup"><span data-stu-id="16fc5-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16fc5-105">例</span><span class="sxs-lookup"><span data-stu-id="16fc5-105">Example</span></span>  
 <span data-ttu-id="16fc5-106"><xref:System.ComponentModel.INotifyPropertyChanged>を実装するために、<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>イベントを宣言して、`OnPropertyChanged`メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="16fc5-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="16fc5-107">次に、変更を通知する必要のある各プロパティについて、そのプロパティが更新されるたびに `OnPropertyChanged` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="16fc5-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="16fc5-108">`Person`クラスがどのように<xref:System.Windows.Data.BindingMode.TwoWay>バインドをサポートしているか、[ TextBox テキストで、ソースを更新するタイミングを制御する](how-to-control-when-the-textbox-text-updates-the-source.md)を参照して下さい。</span><span class="sxs-lookup"><span data-stu-id="16fc5-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16fc5-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="16fc5-109">See also</span></span>
- [<span data-ttu-id="16fc5-110">バインディング ソースの概要</span><span class="sxs-lookup"><span data-stu-id="16fc5-110">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="16fc5-111">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="16fc5-111">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="16fc5-112">方法トピック</span><span class="sxs-lookup"><span data-stu-id="16fc5-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
