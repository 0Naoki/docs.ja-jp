---
title: '方法 : Windows フォーム コントロールに属性を適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 1ab54b0c6828a0648fecfc293b6a7143b012ad6a
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44269346"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="146c4-102">方法 : Windows フォーム コントロールに属性を適用する</span><span class="sxs-lookup"><span data-stu-id="146c4-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="146c4-103">デザイン環境を正しく操作しを実行時に正しく実行するコンポーネントとコントロールを開発するには、クラスとメンバーに属性を正しく適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="146c4-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="146c4-104">例</span><span class="sxs-lookup"><span data-stu-id="146c4-104">Example</span></span>  
 <span data-ttu-id="146c4-105">次のコード例では、カスタム コントロールでいくつかの属性を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="146c4-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="146c4-106">コントロールでは、単純なログ記録機能を示します。</span><span class="sxs-lookup"><span data-stu-id="146c4-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="146c4-107">コントロールがデータ ソースにバインドされると、内のデータ ソースから送信された値が表示されます、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="146c4-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="146c4-108">値で指定された値を超えた場合、`Threshold`プロパティ、`ThresholdExceeded`イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="146c4-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="146c4-109">`AttributesDemoControl`値をログに記録する`LogEntry`クラス。</span><span class="sxs-lookup"><span data-stu-id="146c4-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="146c4-110">`LogEntry`クラスは、ログを記録する型でパラメーター化されたことを意味するテンプレート クラスです。</span><span class="sxs-lookup"><span data-stu-id="146c4-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="146c4-111">たとえば場合、`AttributesDemoControl`型の値をログ記録は、 `float`、それぞれ`LogEntry`インスタンスが宣言され、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="146c4-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="146c4-112">`LogEntry`パラメーター化された任意の型によって、パラメーターの型を操作する、リフレクションを使用する必要がありますに。</span><span class="sxs-lookup"><span data-stu-id="146c4-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="146c4-113">しきい値機能するには、パラメーターの型を`T`実装する必要があります、<xref:System.IComparable>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="146c4-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="146c4-114">フォームをホストする、`AttributesDemoControl`パフォーマンス カウンターを定期的に照会します。</span><span class="sxs-lookup"><span data-stu-id="146c4-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="146c4-115">パッケージ化された各値を`LogEntry`適切な種類のフォームの追加と<xref:System.Windows.Forms.BindingSource>。</span><span class="sxs-lookup"><span data-stu-id="146c4-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="146c4-116">`AttributesDemoControl` 、データ バインディングを使用値を受け取っての値を表示、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="146c4-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="146c4-117">最初のコード例は、`AttributesDemoControl`実装します。</span><span class="sxs-lookup"><span data-stu-id="146c4-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="146c4-118">2 番目のコード例に示しますを使用する形式、`AttributesDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="146c4-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="146c4-119">クラス レベルの属性</span><span class="sxs-lookup"><span data-stu-id="146c4-119">Class-level Attributes</span></span>  
 <span data-ttu-id="146c4-120">いくつかの属性は、クラス レベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="146c4-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="146c4-121">次のコード例では、一般的に、Windows フォーム コントロールに適用される属性を示します。</span><span class="sxs-lookup"><span data-stu-id="146c4-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="146c4-122">TypeConverter 属性</span><span class="sxs-lookup"><span data-stu-id="146c4-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="146c4-123"><xref:System.ComponentModel.TypeConverterAttribute> 一般的に使用されるもう 1 つのクラス レベル属性です。</span><span class="sxs-lookup"><span data-stu-id="146c4-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="146c4-124">次のコード例の使用を示しています、`LogEntry`クラス。</span><span class="sxs-lookup"><span data-stu-id="146c4-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="146c4-125">この例では、実装も示しています、<xref:System.ComponentModel.TypeConverter>の`LogEntry`と呼ばれる型`LogEntryTypeConverter`します。</span><span class="sxs-lookup"><span data-stu-id="146c4-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="146c4-126">メンバー レベルの属性</span><span class="sxs-lookup"><span data-stu-id="146c4-126">Member-level Attributes</span></span>  
 <span data-ttu-id="146c4-127">いくつかの属性は、メンバー レベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="146c4-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="146c4-128">次のコード例では、一般的に Windows フォーム コントロールのプロパティに適用されるいくつかの属性を示します。</span><span class="sxs-lookup"><span data-stu-id="146c4-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="146c4-129">AmbientValue 属性</span><span class="sxs-lookup"><span data-stu-id="146c4-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="146c4-130">次の例で、<xref:System.ComponentModel.AmbientValueAttribute>し、デザイン環境とのやり取りをサポートするコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="146c4-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="146c4-131">この操作を呼び出す*アンビエンス*します。</span><span class="sxs-lookup"><span data-stu-id="146c4-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="146c4-132">データ バインド属性</span><span class="sxs-lookup"><span data-stu-id="146c4-132">Databinding Attributes</span></span>  
 <span data-ttu-id="146c4-133">次の例では、複合データ バインディングの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="146c4-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="146c4-134">クラス レベル<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>のように、以前を指定します、`DataSource`と`DataMember`データ バインドに使用するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="146c4-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="146c4-135"><xref:System.ComponentModel.AttributeProviderAttribute>対象の型を指定します、`DataSource`プロパティにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="146c4-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="146c4-136">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="146c4-136">Compiling the Code</span></span>  
  
-   <span data-ttu-id="146c4-137">フォームをホストする、`AttributesDemoControl`への参照が必要です、`AttributesDemoControl`アセンブリをビルドするためにします。</span><span class="sxs-lookup"><span data-stu-id="146c4-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="146c4-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="146c4-138">See Also</span></span>  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="146c4-139">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="146c4-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="146c4-140">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="146c4-140">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="146c4-141">方法: designerserializationvisibilityattribute を使用、基本データ型のコレクションをシリアル化</span><span class="sxs-lookup"><span data-stu-id="146c4-141">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
