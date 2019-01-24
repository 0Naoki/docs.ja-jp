---
title: '方法: StatusBar コントロールにパネルを追加します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- panels [Windows Forms], status bars
- status bars [Windows Forms], adding panels
- StatusBar control [Windows Forms], adding panels
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
ms.openlocfilehash: f2648ffc9a733266c463c165f4beb77b7c098ca9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746287"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a><span data-ttu-id="958ab-102">方法: StatusBar コントロールにパネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="958ab-102">How to: Add Panels to a StatusBar Control</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="958ab-103"><xref:System.Windows.Forms.StatusStrip>と<xref:System.Windows.Forms.ToolStripStatusLabel>コントロールの置換し、する機能を追加、<xref:System.Windows.Forms.StatusBar>と<xref:System.Windows.Forms.StatusBarPanel>を制御しますただし、、<xref:System.Windows.Forms.StatusBar>と<xref:System.Windows.Forms.StatusBarPanel>場合、下位互換性と将来の使用の両方のコントロールが保持されますします。選択します。</span><span class="sxs-lookup"><span data-stu-id="958ab-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="958ab-104">内のプログラミング可能な領域を[StatusBar コントロール](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md)コントロールのインスタンスから成る、<xref:System.Windows.Forms.StatusBarPanel>クラス。</span><span class="sxs-lookup"><span data-stu-id="958ab-104">The programmable area within a [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) control consists of instances of the <xref:System.Windows.Forms.StatusBarPanel> class.</span></span> <span data-ttu-id="958ab-105">追加機能を追加するには、<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>クラス。</span><span class="sxs-lookup"><span data-stu-id="958ab-105">These are added through additions to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> class.</span></span>  
  
### <a name="to-add-panels-to-a-status-bar"></a><span data-ttu-id="958ab-106">ステータス バー パネルを追加するには</span><span class="sxs-lookup"><span data-stu-id="958ab-106">To add panels to a status bar</span></span>  
  
1.  <span data-ttu-id="958ab-107">プロシージャでは、ステータス バー パネルを追加することによって作成、<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>します。</span><span class="sxs-lookup"><span data-stu-id="958ab-107">In a procedure, create status-bar panels by adding them to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span> <span data-ttu-id="958ab-108">を介して渡されたインデックスを使用して個別のパネルにプロパティの設定を指定、<xref:System.Windows.Forms.StatusBar.Panels%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="958ab-108">Specify property settings for individual panels by using its index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property.</span></span>  
  
     <span data-ttu-id="958ab-109">アイコンの場所は次のコード例で、パスが設定、 **My Documents**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="958ab-109">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="958ab-110">この場所は、Windows オペレーティング システムを実行しているほとんどのコンピューターにはでこのフォルダーが含まれていると想定できるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="958ab-110">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="958ab-111">この場所を選択すると、ユーザーは最小限のシステム アクセスのレベルでアプリケーションを安全に実行もできます。</span><span class="sxs-lookup"><span data-stu-id="958ab-111">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="958ab-112">次の例では、使用して、フォームが必要です、<xref:System.Windows.Forms.StatusBar>コントロールが既に追加されています。</span><span class="sxs-lookup"><span data-stu-id="958ab-112">The following example requires a form with a <xref:System.Windows.Forms.StatusBar> control already added.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="958ab-113"><xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>は、0 から始まるコレクションので、コードがそれに応じて続行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="958ab-113">The <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> is a zero-based collection, so code should proceed accordingly.</span></span>  
  
    ```vb  
    Public Sub CreateStatusBarPanels()  
    ' Create panels and set text property.  
       StatusBar1.Panels.Add("One")  
       StatusBar1.Panels.Add("Two")  
       StatusBar1.Panels.Add("Three")  
    ' Set properties of StatusBar panels.  
    ' Set AutoSize property of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(1).AutoSize = StatusBarPanelAutoSize.Contents  
       StatusBar1.Panels(2).AutoSize = StatusBarPanelAutoSize.Contents  
    ' Set BorderStyle property of panels.  
       StatusBar1.Panels(0).BorderStyle = StatusBarPanelBorderStyle.Raised  
       StatusBar1.Panels(1).BorderStyle = StatusBarPanelBorderStyle.Sunken  
       StatusBar1.Panels(2).BorderStyle = StatusBarPanelBorderStyle.Raised  
    ' Set Icon property of third panel. You should replace the bolded  
    ' icon in the sample below with an icon of your own choosing.  
       StatusBar1.Panels(2).Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
       StatusBar1.ShowPanels = True  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateStatusBarPanels()  
    {  
       // Create panels and set text property.  
       statusBar1.Panels.Add("One");  
       statusBar1.Panels.Add("Two");  
       statusBar1.Panels.Add("Three");  
       // Set properties of StatusBar panels.  
       // Set AutoSize property of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[1].AutoSize = StatusBarPanelAutoSize.Contents;  
       statusBar1.Panels[2].AutoSize = StatusBarPanelAutoSize.Contents;  
       // Set BorderStyle property of panels.  
       statusBar1.Panels[0].BorderStyle =  
          StatusBarPanelBorderStyle.Raised;  
       statusBar1.Panels[1].BorderStyle = StatusBarPanelBorderStyle.Sunken;  
       statusBar1.Panels[2].BorderStyle = StatusBarPanelBorderStyle.Raised;  
       // Set Icon property of third panel. You should replace the bolded  
       // icon in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       statusBar1.Panels[2].Icon =   
          new System.Drawing.Icon (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Icon.ico");  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateStatusBarPanels()  
       {  
          // Create panels and set text property.  
          statusBar1->Panels->Add("One");  
          statusBar1->Panels->Add("Two");  
          statusBar1->Panels->Add("Three");  
          // Set properties of StatusBar panels.  
          // Set AutoSize property of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[1]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          statusBar1->Panels[2]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          // Set BorderStyle property of panels.  
          statusBar1->Panels[0]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          statusBar1->Panels[1]->BorderStyle =  
             StatusBarPanelBorderStyle::Sunken;  
          statusBar1->Panels[2]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          // Set Icon property of third panel.  
          // You should replace the bolded image   
          // in the sample below with an icon of your own choosing.  
          statusBar1->Panels[2]->Icon =  
             gcnew System::Drawing::Icon(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Icon.ico"));  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="958ab-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="958ab-114">See also</span></span>
- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="958ab-115">コレクション エディター ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="958ab-115">Collection Editor Dialog Box</span></span>](https://msdn.microsoft.com/library/53fb3aad-bffa-4da5-ac89-8438e6fc803c)
- [<span data-ttu-id="958ab-116">方法: ステータス バー パネルのサイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="958ab-116">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="958ab-117">チュートリアル: 実行時にステータス バー情報の更新</span><span class="sxs-lookup"><span data-stu-id="958ab-117">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="958ab-118">方法: Windows フォームの StatusBar コントロール パネルのクリックを確認します。</span><span class="sxs-lookup"><span data-stu-id="958ab-118">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="958ab-119">StatusBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="958ab-119">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
