---
title: '方法: Windows フォームの MonthCalendar コントロールで日付の範囲を選択します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
ms.openlocfilehash: 21cda9fb11edd3f6148d7128621fbde8d3ff913c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723817"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="532cd-102">方法: Windows フォームの MonthCalendar コントロールで日付の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="532cd-102">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="532cd-103">Windows フォームの重要な特徴<xref:System.Windows.Forms.MonthCalendar>コントロールは、ユーザーが日付の範囲を選択できます。</span><span class="sxs-lookup"><span data-stu-id="532cd-103">An important feature of the Windows Forms <xref:System.Windows.Forms.MonthCalendar> control is that the user can select a range of dates.</span></span> <span data-ttu-id="532cd-104">この機能が、日付選択機能の改良、<xref:System.Windows.Forms.DateTimePicker>のみユーザーが 1 つの日付/時刻値を選択できるようにするコントロール。</span><span class="sxs-lookup"><span data-stu-id="532cd-104">This feature is an improvement over the date-selection feature of the <xref:System.Windows.Forms.DateTimePicker> control, which only enables the user to select a single date/time value.</span></span> <span data-ttu-id="532cd-105">日付の範囲を設定または選択範囲のプロパティを使用して、ユーザーが設定を取得できます、<xref:System.Windows.Forms.MonthCalendar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="532cd-105">You can set a range of dates or get a selection range set by the user by using properties of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span> <span data-ttu-id="532cd-106">次のコード例では、選択範囲を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="532cd-106">The following code example demonstrates how to set a selection range.</span></span>  
  
### <a name="to-select-a-range-of-dates"></a><span data-ttu-id="532cd-107">日付の範囲を選択するには</span><span class="sxs-lookup"><span data-stu-id="532cd-107">To select a range of dates</span></span>  
  
1.  <span data-ttu-id="532cd-108">作成<xref:System.DateTime>範囲の最初と最後の日付を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="532cd-108">Create <xref:System.DateTime> objects that represent the first and last dates in a range.</span></span>  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2.  <span data-ttu-id="532cd-109"><xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="532cd-109">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> property.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     <span data-ttu-id="532cd-110">または</span><span class="sxs-lookup"><span data-stu-id="532cd-110">–or–</span></span>  
  
     <span data-ttu-id="532cd-111"><xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> プロパティと <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="532cd-111">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> and <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> properties.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="532cd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="532cd-112">See also</span></span>
- [<span data-ttu-id="532cd-113">MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="532cd-113">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="532cd-114">方法: Windows フォーム MonthCalendar コントロールの外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="532cd-114">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="532cd-115">方法: 特定の日で、Windows で太字で表示フォームの MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="532cd-115">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="532cd-116">方法: Windows フォームの MonthCalendar コントロールにおいて複数の月を表示します。</span><span class="sxs-lookup"><span data-stu-id="532cd-116">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
