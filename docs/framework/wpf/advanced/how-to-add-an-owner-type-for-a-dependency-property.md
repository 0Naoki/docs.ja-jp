---
title: '方法: 依存関係プロパティの所有者の種類を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 03ffec87c98c88452aa8fde89c64646eaf48a8da
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369592"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="21669-102">方法: 依存関係プロパティの所有者の種類を追加する</span><span class="sxs-lookup"><span data-stu-id="21669-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="21669-103">この例では、異なる種類の登録されている依存関係プロパティの所有者としてクラスを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="21669-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="21669-104">この手順を実行して、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]リーダーとプロパティ システムの両方のプロパティの追加の所有者としてクラスを認識することができます。</span><span class="sxs-lookup"><span data-stu-id="21669-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="21669-105">必要に応じて所有者として追加すると、型固有のメタデータを提供する追加のクラスができます。</span><span class="sxs-lookup"><span data-stu-id="21669-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="21669-106">次の例では、`StateProperty`によってプロパティが登録、`MyStateControl`クラス。</span><span class="sxs-lookup"><span data-stu-id="21669-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="21669-107">クラスは、`UnrelatedStateControl`自体の所有者として追加、`StateProperty`を使用して、<xref:System.Windows.DependencyProperty.AddOwner%2A>メソッド、具体的には、追加の型に存在する依存関係プロパティの新しいメタデータは、署名を使用します。</span><span class="sxs-lookup"><span data-stu-id="21669-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="21669-108">提供する必要がありますに注意してください[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]に示した例のようなプロパティのアクセサー、[依存関係プロパティを実装して](how-to-implement-a-dependency-property.md)など、追加されるクラスの依存関係プロパティ識別子を再公開所有者。</span><span class="sxs-lookup"><span data-stu-id="21669-108">Notice that you should provide [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] accessors for the property similar to the example shown in the [Implement a Dependency Property](how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="21669-109">ラッパーの依存関係プロパティは機能を使用したプログラムによるアクセスの観点から<xref:System.Windows.DependencyObject.GetValue%2A>または<xref:System.Windows.DependencyObject.SetValue%2A>します。</span><span class="sxs-lookup"><span data-stu-id="21669-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="21669-110">通常の場合は、このプロパティ システム動作するには、[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]プロパティ ラッパー。</span><span class="sxs-lookup"><span data-stu-id="21669-110">But you typically want to parallel this property-system behavior with the [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrappers.</span></span> <span data-ttu-id="21669-111">ラッパーがプログラムで、依存関係プロパティを設定するが容易し、としてのプロパティを設定することを可能[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性。</span><span class="sxs-lookup"><span data-stu-id="21669-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="21669-112">既定のメタデータをオーバーライドする方法についてを参照してください。[依存関係プロパティのメタデータをオーバーライド](how-to-override-metadata-for-a-dependency-property.md)します。</span><span class="sxs-lookup"><span data-stu-id="21669-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21669-113">例</span><span class="sxs-lookup"><span data-stu-id="21669-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="21669-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="21669-114">See also</span></span>
- [<span data-ttu-id="21669-115">カスタム依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="21669-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="21669-116">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="21669-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
