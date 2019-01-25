---
title: '方法: 特定のデータ形式でデータを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: d11374cbc70210e648e93a385c4a9fbca112c09f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718296"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="a841c-102">方法: 特定のデータ形式でデータを取得する</span><span class="sxs-lookup"><span data-stu-id="a841c-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="a841c-103">次の例では、指定された形式でデータ オブジェクトからデータを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a841c-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a841c-104">例</span><span class="sxs-lookup"><span data-stu-id="a841c-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a841c-105">説明</span><span class="sxs-lookup"><span data-stu-id="a841c-105">Description</span></span>  
 <span data-ttu-id="a841c-106">次のコード例を使用して、<xref:System.Windows.DataObject.GetDataPresent%28System.String%29>を最初に指定されたデータが書式設定を確認するオーバー ロードは (ネイティブまたは自動変換を)、例を使用してデータを取得する指定の形式を使用できる場合、<xref:System.Windows.DataObject.GetData%28System.String%29>メソッド。</span><span class="sxs-lookup"><span data-stu-id="a841c-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a841c-107">コード</span><span class="sxs-lookup"><span data-stu-id="a841c-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="a841c-108">例</span><span class="sxs-lookup"><span data-stu-id="a841c-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a841c-109">説明</span><span class="sxs-lookup"><span data-stu-id="a841c-109">Description</span></span>  
 <span data-ttu-id="a841c-110">次のコード例を使用して、<xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>オーバー ロードを最初に指定したデータ形式が使用可能なネイティブを確認する (自動変換できるデータ形式はフィルターされます) 例では、が、を使用して、データを取得する指定の形式を使用できる場合<xref:System.Windows.DataObject.GetData%28System.String%29>。メソッド。</span><span class="sxs-lookup"><span data-stu-id="a841c-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a841c-111">コード</span><span class="sxs-lookup"><span data-stu-id="a841c-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="a841c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a841c-112">See also</span></span>
- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="a841c-113">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="a841c-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
