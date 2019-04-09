---
title: '方法: システム フォント キーを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: e924f4c14d98380d9f4c0defe27d9f98c3293114
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148929"
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="9123b-102">方法: システム フォント キーを使用する</span><span class="sxs-lookup"><span data-stu-id="9123b-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="9123b-103">システム リソースは、開発者がシステム設定と一貫性のあるビジュアルを作成できるようにするために、多くのシステム メトリックをリソースとして公開します。</span><span class="sxs-lookup"><span data-stu-id="9123b-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <xref:System.Windows.SystemFonts> <span data-ttu-id="9123b-104">システム フォント値と値にバインドされるシステム フォント リソースの両方を含むクラスは、— たとえば、<xref:System.Windows.SystemFonts.CaptionFontFamily%2A>と<xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>します。</span><span class="sxs-lookup"><span data-stu-id="9123b-104">is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="9123b-105">システム フォント メトリックは、静的なリソースとしても、動的なリソースとしても使用できます。</span><span class="sxs-lookup"><span data-stu-id="9123b-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="9123b-106">アプリケーションの実行時にフォント メトリックを自動的に更新する場合は、動的リソースを使用します。それ以外の場合は、静的リソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="9123b-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9123b-107">動的リソースにキーワードを指定する*キー*プロパティ名に追加されます。</span><span class="sxs-lookup"><span data-stu-id="9123b-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="9123b-108">次の例では、システム フォント動的リソースにアクセスして使用し、ボタンのスタイル設定またはカスタマイズを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9123b-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="9123b-109">これは、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を割り当てるボタン スタイルを作成する例<xref:System.Windows.SystemFonts>をボタンの値。</span><span class="sxs-lookup"><span data-stu-id="9123b-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9123b-110">例</span><span class="sxs-lookup"><span data-stu-id="9123b-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="9123b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9123b-111">See also</span></span>

- [<span data-ttu-id="9123b-112">システム ブラシで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="9123b-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="9123b-113">SystemParameters を使用する</span><span class="sxs-lookup"><span data-stu-id="9123b-113">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="9123b-114">SystemFonts を使用する</span><span class="sxs-lookup"><span data-stu-id="9123b-114">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
