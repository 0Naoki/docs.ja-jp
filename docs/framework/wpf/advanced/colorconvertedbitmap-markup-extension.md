---
title: ColorConvertedBitmap のマークアップ拡張機能
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: e8a36a1b8592146eb2474805638cdc3697adb0c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010658"
---
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="4b5cf-102">ColorConvertedBitmap のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="4b5cf-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="4b5cf-103">ビットマップ ソースが埋め込まれたプロファイルを指定する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="4b5cf-104">色のコンテキスト プロファイルが指定/[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]イメージ ソースとして、[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-104">Color contexts / profiles are specified by [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], as is the image source [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="4b5cf-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="4b5cf-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="4b5cf-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="4b5cf-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="4b5cf-107">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]見積もるビットマップの。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-107">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="4b5cf-108">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]のソース プロファイルの構成。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-108">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="4b5cf-109">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]の移行先のプロファイルの構成</span><span class="sxs-lookup"><span data-stu-id="4b5cf-109">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b5cf-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b5cf-110">Remarks</span></span>  
 <span data-ttu-id="4b5cf-111">このマークアップ拡張機能など、関連する一連のイメージ ソース プロパティの値を入力するものでは<xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>します。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="4b5cf-112">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="4b5cf-113">`ColorConvertedBitmap` (または`ColorConvertedBitmapExtension`) 文字列は、最初のコンス トラクターで値として値が設定のみできるため、プロパティ要素構文では使用できません次の拡張機能の識別子。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="4b5cf-114">`ColorConvertedBitmap` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="4b5cf-115">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="4b5cf-116">すべてのマークアップ拡張機能で[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を使用して、{および} される規則は、それぞれの属性構文内の文字を[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサを認識するマークアップ拡張機能が、属性を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="4b5cf-117">詳細については、次を参照してください。[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b5cf-117">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b5cf-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b5cf-118">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="4b5cf-119">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="4b5cf-119">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="4b5cf-120">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="4b5cf-120">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
