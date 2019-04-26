---
title: '方法: よく使用する場所をファイル ダイアログ ボックスに追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 79836dd260cb13912ccba43cfb4a0a3e0ad195fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011204"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="b5758-102">方法: よく使用する場所をファイル ダイアログ ボックスに追加する</span><span class="sxs-lookup"><span data-stu-id="b5758-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="b5758-103">[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] の既定の 開く] ダイアログ ボックスと 保存] ダイアログ ボックスには、左側に **[お気に入りリンク]** というタイトルの領域があります。</span><span class="sxs-lookup"><span data-stu-id="b5758-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="b5758-104">この領域にはカスタム プレイスという名称が付いています。</span><span class="sxs-lookup"><span data-stu-id="b5758-104">This area is called custom places.</span></span> <span data-ttu-id="b5758-105"><xref:System.Windows.Forms.OpenFileDialog>と<xref:System.Windows.Forms.SaveFileDialog>クラスを使用すると、フォルダーを追加する、<xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="b5758-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5758-106">カスタムの場所に表示するために、<xref:System.Windows.Forms.OpenFileDialog>または<xref:System.Windows.Forms.SaveFileDialog>、<xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A>にプロパティを設定する必要があります`true`(既定)。</span><span class="sxs-lookup"><span data-stu-id="b5758-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="b5758-107">ファイル ダイアログ ボックスにカスタム プレイスを追加するには</span><span class="sxs-lookup"><span data-stu-id="b5758-107">To add a custom place to a file dialog box</span></span>  
  
-   <span data-ttu-id="b5758-108">パスを既知のフォルダー GUID を使用して、追加、または<xref:System.Windows.Forms.FileDialogCustomPlace>オブジェクトを<xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>ダイアログ ボックスのコレクション。</span><span class="sxs-lookup"><span data-stu-id="b5758-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="b5758-109">次のコード例は、パスを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b5758-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b5758-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5758-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b5758-111">ファイル ダイアログ ボックスのカスタム プレイス用既知のフォルダー GUID</span><span class="sxs-lookup"><span data-stu-id="b5758-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
