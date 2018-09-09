---
title: '方法 : バインド コントロールを作成して表示データの書式を設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 8f4d3c4c738e31ab83d506dc7afb4e49b142765b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2018
ms.locfileid: "44228027"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="b76b4-102">方法 : バインド コントロールを作成して表示データの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="b76b4-102">How to: Create a Bound Control and Format the Displayed Data</span></span>
<span data-ttu-id="b76b4-103">Windows フォーム データ バインディングでは、データ バインド コントロールを使用して表示データの書式を設定することができます、**フォーマットと詳細バインド** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b76b4-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b76b4-104">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b76b4-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b76b4-105">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b76b4-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b76b4-106">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b76b4-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="b76b4-107">コントロールをバインドして表示データの書式を設定するには</span><span class="sxs-lookup"><span data-stu-id="b76b4-107">To bind a control and format the displayed data</span></span>  
  
1.  <span data-ttu-id="b76b4-108">データ ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="b76b4-108">Connect to a data source.</span></span>  
  
     <span data-ttu-id="b76b4-109">詳細については、次を参照してください。[データ ソースに接続する](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)します。</span><span class="sxs-lookup"><span data-stu-id="b76b4-109">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="b76b4-110">フォームでコントロールを選択し、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b76b4-110">In the form, select the control, and then open the Properties window.</span></span>  
  
3.  <span data-ttu-id="b76b4-111">展開、 **(DataBindings)** プロパティ、し、 **(詳細)** ボックスで、省略記号ボタンをクリックします (![VisualStudioEllipsesButton スクリーン ショット](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) を表示する、**フォーマットと詳細バインド**ダイアログ ボックスで、そのコントロールのプロパティの完全な一覧があります。</span><span class="sxs-lookup"><span data-stu-id="b76b4-111">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>  
  
4.  <span data-ttu-id="b76b4-112">クリックして、バインド プロパティを選択、**バインド**矢印。</span><span class="sxs-lookup"><span data-stu-id="b76b4-112">Select the property you want to bind, and then click the **Binding** arrow.</span></span>  
  
     <span data-ttu-id="b76b4-113">使用できるデータ ソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b76b4-113">A list of available data sources is displayed.</span></span>  
  
5.  <span data-ttu-id="b76b4-114">目的の 1 つのデータ要素が見つかるまで、バインド先のデータ ソースを展開します。</span><span class="sxs-lookup"><span data-stu-id="b76b4-114">Expand the data source you want to bind to until you find the single data element you want.</span></span>  
  
     <span data-ttu-id="b76b4-115">たとえば、データセットのテーブル内の列の値にバインドする場合は、データセットの名前を展開し、次にテーブル名を展開して、列名を表示します。</span><span class="sxs-lookup"><span data-stu-id="b76b4-115">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
6.  <span data-ttu-id="b76b4-116">バインド先の要素の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b76b4-116">Click the name of an element to bind to.</span></span>  
  
7.  <span data-ttu-id="b76b4-117">**種類の形式を**ボックスに、コントロールに表示されるデータに適用する形式をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b76b4-117">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>  
  
     <span data-ttu-id="b76b4-118">どの形式でも、データ ソースに <xref:System.DBNull> が含まれている場合には、コントロールに表示する値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b76b4-118">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="b76b4-119">それ以外の場合、オプションは、選択する形式の種類に応じて多少変わります。</span><span class="sxs-lookup"><span data-stu-id="b76b4-119">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="b76b4-120">次の表に、形式の種類とオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="b76b4-120">The following table shows the format types and options.</span></span>  
  
    |<span data-ttu-id="b76b4-121">形式の種類</span><span class="sxs-lookup"><span data-stu-id="b76b4-121">Format type</span></span>|<span data-ttu-id="b76b4-122">書式設定のオプション</span><span class="sxs-lookup"><span data-stu-id="b76b4-122">Formatting option</span></span>|  
    |-----------------|-----------------------|  
    |<span data-ttu-id="b76b4-123">書式設定なし</span><span class="sxs-lookup"><span data-stu-id="b76b4-123">No Formatting</span></span>|<span data-ttu-id="b76b4-124">オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="b76b4-124">No options.</span></span>|  
    |<span data-ttu-id="b76b4-125">数字</span><span class="sxs-lookup"><span data-stu-id="b76b4-125">Numeric</span></span>|<span data-ttu-id="b76b4-126">使用して小数点以下桁数を指定**小数点**アップダウン コントロール。</span><span class="sxs-lookup"><span data-stu-id="b76b4-126">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="b76b4-127">通貨</span><span class="sxs-lookup"><span data-stu-id="b76b4-127">Currency</span></span>|<span data-ttu-id="b76b4-128">使用して小数点以下桁数を指定**小数点**アップダウン コントロール。</span><span class="sxs-lookup"><span data-stu-id="b76b4-128">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="b76b4-129">日付と時刻</span><span class="sxs-lookup"><span data-stu-id="b76b4-129">Date Time</span></span>|<span data-ttu-id="b76b4-130">日付と時刻を内の項目のいずれかを選択して表示する必要がある方法を選択、**型**選択ボックス。</span><span class="sxs-lookup"><span data-stu-id="b76b4-130">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|  
    |<span data-ttu-id="b76b4-131">指数</span><span class="sxs-lookup"><span data-stu-id="b76b4-131">Scientific</span></span>|<span data-ttu-id="b76b4-132">使用して小数点以下桁数を指定**小数点**アップダウン コントロール。</span><span class="sxs-lookup"><span data-stu-id="b76b4-132">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="b76b4-133">カスタム</span><span class="sxs-lookup"><span data-stu-id="b76b4-133">Custom</span></span>|<span data-ttu-id="b76b4-134">カスタム書式指定文字列を使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="b76b4-134">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="b76b4-135">詳細については、[型の書式設定](../../../docs/standard/base-types/formatting-types.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b76b4-135">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="b76b4-136">**注:** カスタム書式指定文字列は、データ ソースとバインドされたコントロール間のラウンド トリップが正常に保証されていません。</span><span class="sxs-lookup"><span data-stu-id="b76b4-136">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="b76b4-137">その代わりに、バインディングで <xref:System.Windows.Forms.Binding.Parse> イベントまたは <xref:System.Windows.Forms.Binding.Format> イベントを処理し、イベント処理コードでカスタム書式を適用します。</span><span class="sxs-lookup"><span data-stu-id="b76b4-137">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|  
  
8.  <span data-ttu-id="b76b4-138">をクリックして**OK**を閉じる、**フォーマットと詳細バインド** ダイアログ ボックスと プロパティ ウィンドウに戻ります。</span><span class="sxs-lookup"><span data-stu-id="b76b4-138">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76b4-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="b76b4-139">See Also</span></span>  
 [<span data-ttu-id="b76b4-140">方法: Windows フォームに単純バインド コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="b76b4-140">How to: Create a Simple-Bound Control on a Windows Form</span></span>](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [<span data-ttu-id="b76b4-141">Windows フォームでのユーザー入力の検証</span><span class="sxs-lookup"><span data-stu-id="b76b4-141">User Input Validation in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [<span data-ttu-id="b76b4-142">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="b76b4-142">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
