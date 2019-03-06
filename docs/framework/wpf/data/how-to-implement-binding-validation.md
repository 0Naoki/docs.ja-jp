---
title: '方法: バインディングの検証の実装'
ms.date: 03/30/2017
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: eefdb3b1205a64221e3e9352f70e3d06dc074eff
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368546"
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="d48e6-102">方法: バインディングの検証の実装</span><span class="sxs-lookup"><span data-stu-id="d48e6-102">How to: Implement Binding Validation</span></span>
<span data-ttu-id="d48e6-103">この例は、使用する方法を示します、<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>し、無効な値を入力したら、ユーザーに通知する視覚的なフィードバックを提供するスタイルのトリガーのカスタム検証規則に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d48e6-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d48e6-104">例</span><span class="sxs-lookup"><span data-stu-id="d48e6-104">Example</span></span>  
 <span data-ttu-id="d48e6-105">テキストの内容、<xref:System.Windows.Controls.TextBox>に次の例では、バインド、 `Age` (int 型) のプロパティをという名前のバインディング ソース オブジェクトの`ods`します。</span><span class="sxs-lookup"><span data-stu-id="d48e6-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="d48e6-106">バインディングは、`AgeRangeRule` という名前の検証規則を使用するよう設定されているため、ユーザーが数字以外の文字、または 21 から 130 の範囲外の値を入力すると、テキスト ボックスの横に赤の感嘆符が表示され、ユーザーがテキスト ボックス上にマウスを置くとエラー メッセージを含んだツール ヒントが示されます。</span><span class="sxs-lookup"><span data-stu-id="d48e6-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>  
  
 [!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="d48e6-107">次の例の実装を示しています。 `AgeRangeRule`、から継承される<xref:System.Windows.Controls.ValidationRule>と上書き、<xref:System.Windows.Controls.ValidationRule.Validate%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="d48e6-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="d48e6-108">Int32.Parse() メソッドは、値に無効な文字が含まれていないことを確認するために、値に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d48e6-108">The Int32.Parse() method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="d48e6-109"><xref:System.Windows.Controls.ValidationRule.Validate%2A>メソッドを返します。 を<xref:System.Windows.Controls.ValidationResult>値が有効である、解析中に例外をキャッチするかどうかと、保存期間の値が下限と上限の外部でがかどうかに基づいていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d48e6-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>  
  
 [!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 <span data-ttu-id="d48e6-110">次の例は、カスタム<xref:System.Windows.Controls.ControlTemplate>`validationTemplate`検証エラーをユーザーに通知する赤い感嘆符を作成します。</span><span class="sxs-lookup"><span data-stu-id="d48e6-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="d48e6-111">コントロール テンプレートは、コントロールの外観を再定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d48e6-111">Control templates are used to redefine the appearance of a control.</span></span>  
  
 [!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 <span data-ttu-id="d48e6-112">次の例で示すように、<xref:System.Windows.Controls.ToolTip>という名前のスタイルを使用して、エラー メッセージが作成されたことを示す`textBoxInError`します。</span><span class="sxs-lookup"><span data-stu-id="d48e6-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="d48e6-113">場合の値<xref:System.Windows.Controls.Validation.HasError%2A>は`true`、トリガー設定の現在のツール ヒント<xref:System.Windows.Controls.TextBox>をその最初の検証エラー。</span><span class="sxs-lookup"><span data-stu-id="d48e6-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="d48e6-114"><xref:System.Windows.Data.Binding.RelativeSource%2A>に設定されている<xref:System.Windows.Data.RelativeSourceMode.Self>、現在の要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="d48e6-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>  
  
 [!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 <span data-ttu-id="d48e6-115">コード例全体については、「[バインディングの検証のサンプル](https://go.microsoft.com/fwlink/?LinkID=159972)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d48e6-115">For the complete example, see [Binding Validation Sample](https://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
 <span data-ttu-id="d48e6-116">カスタムを指定しない場合<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>検証エラーがある場合に、ユーザーに視覚的なフィードバックを提供する既定のエラー テンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d48e6-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="d48e6-117">詳しくは、「[データ バインドの概要](data-binding-overview.md)」の「データの検証」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d48e6-117">See "Data Validation" in [Data Binding Overview](data-binding-overview.md) for more information.</span></span> <span data-ttu-id="d48e6-118">さらに [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] は、バインディング ソース プロパティの更新中にスローされる例外をキャッチするための、組み込みの検証規則を提供します。</span><span class="sxs-lookup"><span data-stu-id="d48e6-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="d48e6-119">詳細については、「 <xref:System.Windows.Controls.ExceptionValidationRule> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48e6-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48e6-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d48e6-120">See also</span></span>
- [<span data-ttu-id="d48e6-121">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="d48e6-121">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="d48e6-122">方法トピック</span><span class="sxs-lookup"><span data-stu-id="d48e6-122">How-to Topics</span></span>](data-binding-how-to-topics.md)
