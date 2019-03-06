---
title: '方法: データ オブジェクトを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
ms.openlocfilehash: f7bdfbf3dba0c700513348195c1d031d4c2c8b65
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370593"
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="bd65c-102">方法: データ オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="bd65c-102">How to: Create a Data Object</span></span>
<span data-ttu-id="bd65c-103">次の例では、さまざまな方法で提供されるコンス トラクターを使用して、データ オブジェクトを作成する、<xref:System.Windows.DataObject>クラス。</span><span class="sxs-lookup"><span data-stu-id="bd65c-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd65c-104">例</span><span class="sxs-lookup"><span data-stu-id="bd65c-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bd65c-105">説明</span><span class="sxs-lookup"><span data-stu-id="bd65c-105">Description</span></span>  
 <span data-ttu-id="bd65c-106">次のコード例は、新しいデータ オブジェクトを作成し、オーバー ロードされたコンス トラクターのいずれかを使用して (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) を文字列でデータ オブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="bd65c-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="bd65c-107">この場合、格納されたデータの種類に応じて、適切なデータ形式を自動的に決定され、既定では、格納されたデータの自動変換が許可されています。</span><span class="sxs-lookup"><span data-stu-id="bd65c-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd65c-108">コード</span><span class="sxs-lookup"><span data-stu-id="bd65c-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="bd65c-109">説明</span><span class="sxs-lookup"><span data-stu-id="bd65c-109">Description</span></span>  
 <span data-ttu-id="bd65c-110">次のコード例は、上記のコードの要約バージョンです。</span><span class="sxs-lookup"><span data-stu-id="bd65c-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd65c-111">コード</span><span class="sxs-lookup"><span data-stu-id="bd65c-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="bd65c-112">例</span><span class="sxs-lookup"><span data-stu-id="bd65c-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bd65c-113">説明</span><span class="sxs-lookup"><span data-stu-id="bd65c-113">Description</span></span>  
 <span data-ttu-id="bd65c-114">次のコード例は、新しいデータ オブジェクトを作成し、オーバー ロードされたコンス トラクターのいずれかを使用して (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) 文字列と指定したデータ形式でデータ オブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="bd65c-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="bd65c-115">文字列でデータ形式を指定するこの場合<xref:System.Windows.DataFormats>クラスは、一連の事前定義された型の文字列を提供します。</span><span class="sxs-lookup"><span data-stu-id="bd65c-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="bd65c-116">格納されているデータの自動変換は、既定で許可されます。</span><span class="sxs-lookup"><span data-stu-id="bd65c-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd65c-117">コード</span><span class="sxs-lookup"><span data-stu-id="bd65c-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="bd65c-118">説明</span><span class="sxs-lookup"><span data-stu-id="bd65c-118">Description</span></span>  
 <span data-ttu-id="bd65c-119">次のコード例は、上記のコードの要約バージョンです。</span><span class="sxs-lookup"><span data-stu-id="bd65c-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd65c-120">コード</span><span class="sxs-lookup"><span data-stu-id="bd65c-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="bd65c-121">例</span><span class="sxs-lookup"><span data-stu-id="bd65c-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bd65c-122">説明</span><span class="sxs-lookup"><span data-stu-id="bd65c-122">Description</span></span>  
 <span data-ttu-id="bd65c-123">次のコード例は、新しいデータ オブジェクトを作成し、オーバー ロードされたコンス トラクターのいずれかを使用して (<xref:System.Windows.DataObject.%23ctor%2A>) 文字列と指定したデータ形式でデータ オブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="bd65c-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="bd65c-124">この場合、データ形式がで指定された、<xref:System.Type>パラメーター。</span><span class="sxs-lookup"><span data-stu-id="bd65c-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="bd65c-125">格納されているデータの自動変換は、既定で許可されます。</span><span class="sxs-lookup"><span data-stu-id="bd65c-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd65c-126">コード</span><span class="sxs-lookup"><span data-stu-id="bd65c-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="bd65c-127">説明</span><span class="sxs-lookup"><span data-stu-id="bd65c-127">Description</span></span>  
 <span data-ttu-id="bd65c-128">次のコード例は、上記のコードの要約バージョンです。</span><span class="sxs-lookup"><span data-stu-id="bd65c-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd65c-129">コード</span><span class="sxs-lookup"><span data-stu-id="bd65c-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="bd65c-130">例</span><span class="sxs-lookup"><span data-stu-id="bd65c-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bd65c-131">説明</span><span class="sxs-lookup"><span data-stu-id="bd65c-131">Description</span></span>  
 <span data-ttu-id="bd65c-132">次のコード例は、新しいデータ オブジェクトを作成し、オーバー ロードされたコンス トラクターのいずれかを使用して (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) 文字列と指定したデータ形式でデータ オブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="bd65c-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="bd65c-133">文字列でデータ形式を指定するこの場合<xref:System.Windows.DataFormats>クラスは、一連の事前定義された型の文字列を提供します。</span><span class="sxs-lookup"><span data-stu-id="bd65c-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="bd65c-134">この特定のコンス トラクター オーバー ロードには、自動変換が許可されているかどうかを指定する呼び出し元ができるようにします。</span><span class="sxs-lookup"><span data-stu-id="bd65c-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd65c-135">コード</span><span class="sxs-lookup"><span data-stu-id="bd65c-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="bd65c-136">説明</span><span class="sxs-lookup"><span data-stu-id="bd65c-136">Description</span></span>  
 <span data-ttu-id="bd65c-137">次のコード例は、上記のコードの要約バージョンです。</span><span class="sxs-lookup"><span data-stu-id="bd65c-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd65c-138">コード</span><span class="sxs-lookup"><span data-stu-id="bd65c-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="bd65c-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd65c-139">See also</span></span>
- <xref:System.Windows.IDataObject>
