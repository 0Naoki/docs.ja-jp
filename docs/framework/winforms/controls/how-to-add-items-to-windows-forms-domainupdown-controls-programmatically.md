---
title: '方法 : Windows フォーム DomainUpDown コントロールにプログラムで項目を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 7359310b092e84b250c09153ef86d44c70d413fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="fd2f9-102">方法 : Windows フォーム DomainUpDown コントロールにプログラムで項目を追加する</span><span class="sxs-lookup"><span data-stu-id="fd2f9-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="fd2f9-103">Windows フォームに項目を追加することができます<xref:System.Windows.Forms.DomainUpDown>コード内でコントロール。</span><span class="sxs-lookup"><span data-stu-id="fd2f9-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="fd2f9-104">呼び出す、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>または<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>のメソッド、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>をコントロールの項目を追加するクラス<xref:System.Windows.Forms.DomainUpDown.Items%2A>プロパティです。</span><span class="sxs-lookup"><span data-stu-id="fd2f9-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="fd2f9-105"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>メソッドは、コレクションの末尾に項目を追加中に、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>メソッドが、指定した位置に項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="fd2f9-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="fd2f9-106">新しい項目を追加するには</span><span class="sxs-lookup"><span data-stu-id="fd2f9-106">To add a new item</span></span>  
  
1.  <span data-ttu-id="fd2f9-107">使用して、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>項目のリストの末尾に項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="fd2f9-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="fd2f9-108">- または -</span><span class="sxs-lookup"><span data-stu-id="fd2f9-108">-or-</span></span>  
  
2.  <span data-ttu-id="fd2f9-109">使用して、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>メソッドを指定した位置にある一覧に項目を挿入します。</span><span class="sxs-lookup"><span data-stu-id="fd2f9-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fd2f9-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd2f9-110">See Also</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>  
 <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="fd2f9-111">DomainUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="fd2f9-111">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [<span data-ttu-id="fd2f9-112">DomainUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="fd2f9-112">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
