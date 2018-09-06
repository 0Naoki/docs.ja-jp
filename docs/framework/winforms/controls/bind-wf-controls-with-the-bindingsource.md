---
title: '方法 : デザイナーを使用して Windows フォーム コントロールを BindingSource コンポーネントにバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 95f375d8845c60441aa5eefdd37e32541ea2d5a7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042310"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="7c514-102">方法 : デザイナーを使用して Windows フォーム コントロールを BindingSource コンポーネントにバインドする</span><span class="sxs-lookup"><span data-stu-id="7c514-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="7c514-103">コントロールがフォームに追加し、アプリケーションのユーザー インターフェイスを決定したら後、は、実行時に、ユーザーは変更して、アプリケーションに関連するデータを保存できるように、データ ソースにコントロールをバインドできます。</span><span class="sxs-lookup"><span data-stu-id="7c514-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>  
  
 <span data-ttu-id="7c514-104">使用して最も簡単に実現は、Windows フォーム コントロールまたは一連のコントロールをバインドする、<xref:System.Windows.Forms.BindingSource>コントロールをフォーム上のコントロールとデータ ソース間のブリッジとして。</span><span class="sxs-lookup"><span data-stu-id="7c514-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>  
  
 <span data-ttu-id="7c514-105">フォーム上の 1 つまたは複数のコントロールをデータにバインドできます。次の手順で、<xref:System.Windows.Forms.TextBox>コントロールがデータ ソースにバインドします。</span><span class="sxs-lookup"><span data-stu-id="7c514-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>  
  
 <span data-ttu-id="7c514-106">データベースから取得したデータ ソースにバインドすることは、手順を完了するには、と見なされます。</span><span class="sxs-lookup"><span data-stu-id="7c514-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="7c514-107">その他のデータ ストアからデータ ソースを作成する方法の詳細については、次を参照してください。[新しいデータ ソースの追加](/visualstudio/data-tools/add-new-data-sources)します。</span><span class="sxs-lookup"><span data-stu-id="7c514-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c514-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c514-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7c514-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c514-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7c514-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c514-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="7c514-111">デザイン時にコントロールをバインドするには</span><span class="sxs-lookup"><span data-stu-id="7c514-111">To bind a control at design time</span></span>  
  
1.  <span data-ttu-id="7c514-112">ドラッグ、<xref:System.Windows.Forms.TextBox>コントロールをフォームにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7c514-112">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>  
  
2.  <span data-ttu-id="7c514-113">**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="7c514-113">In the **Properties** window:</span></span>  
  
    1.  <span data-ttu-id="7c514-114">展開、 **(DataBindings)** ノード。</span><span class="sxs-lookup"><span data-stu-id="7c514-114">Expand the **(DataBindings)** node.</span></span>  
  
    2.  <span data-ttu-id="7c514-115">矢印をクリックして、<xref:System.Windows.Forms.TextBox.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7c514-115">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
         <span data-ttu-id="7c514-116">**DataSource** UI 型エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c514-116">The **DataSource** UI type editor opens.</span></span>  
  
         <span data-ttu-id="7c514-117">プロジェクトまたはフォームのデータ ソースが構成されていた場合は、表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c514-117">If a data source has previously been configured for the project or form, it will appear.</span></span>  
  
3.  <span data-ttu-id="7c514-118">**[プロジェクト データ ソースの追加]** をクリックしてデータに接続し、データ ソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c514-118">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
4.  <span data-ttu-id="7c514-119">**データ ソース構成ウィザード**の開始ページで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c514-119">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7c514-120">**データ ソースの種類を選択**] ページで、[**データベース**します。</span><span class="sxs-lookup"><span data-stu-id="7c514-120">On the **Choose a Data Source Type** page, select **Database**.</span></span>  
  
6.  <span data-ttu-id="7c514-121">**データ接続の選択** ページで、利用可能な接続の一覧からデータ接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c514-121">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="7c514-122">目的のデータ接続が使用可能な選択ではない場合**新しい接続**新しいデータ接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="7c514-122">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>  
  
7.  <span data-ttu-id="7c514-123">選択**接続を [はい] に、保存**をアプリケーション構成ファイルで接続文字列を保存します。</span><span class="sxs-lookup"><span data-stu-id="7c514-123">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
8.  <span data-ttu-id="7c514-124">アプリケーションで使用するデータベース オブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c514-124">Select the database objects to bring into your application.</span></span> <span data-ttu-id="7c514-125">この場合、希望するテーブルでフィールドを選び、<xref:System.Windows.Forms.TextBox>を表示します。</span><span class="sxs-lookup"><span data-stu-id="7c514-125">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>  
  
9. <span data-ttu-id="7c514-126">必要な場合は、既定のデータセット名を変更します。</span><span class="sxs-lookup"><span data-stu-id="7c514-126">Replace the default dataset name if you want.</span></span>  
  
10. <span data-ttu-id="7c514-127">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c514-127">Click **Finish**.</span></span>  
  
11. <span data-ttu-id="7c514-128">**プロパティ**ウィンドウで、矢印をクリックして、<xref:System.Windows.Forms.TextBox.Text%2A>プロパティを再度します。</span><span class="sxs-lookup"><span data-stu-id="7c514-128">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="7c514-129">**DataSource** UI 型エディターでは、バインドするフィールドの名前を選択する、<xref:System.Windows.Forms.TextBox>にします。</span><span class="sxs-lookup"><span data-stu-id="7c514-129">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>  
  
     <span data-ttu-id="7c514-130">**DataSource** UI 型エディターが終了し、データ セット<xref:System.Windows.Forms.BindingSource>およびテーブル アダプターをフォームにデータ接続が追加されたことを特定します。</span><span class="sxs-lookup"><span data-stu-id="7c514-130">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c514-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c514-131">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [<span data-ttu-id="7c514-132">新しいデータ ソースの追加</span><span class="sxs-lookup"><span data-stu-id="7c514-132">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)  
 [<span data-ttu-id="7c514-133">データ ソース ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7c514-133">Data Sources Window</span></span>](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
