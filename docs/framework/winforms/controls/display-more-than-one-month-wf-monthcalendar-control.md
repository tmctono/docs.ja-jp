---
title: '方法: Windows フォームの MonthCalendar コントロールにおいて複数の月を表示します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], formatting display
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], multiple months
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
ms.openlocfilehash: febed820bae460f51bb19f08caa6027011abd55d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715348"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="de481-102">方法: Windows フォームの MonthCalendar コントロールにおいて複数の月を表示します。</span><span class="sxs-lookup"><span data-stu-id="de481-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="de481-103">Windows フォーム<xref:System.Windows.Forms.MonthCalendar>コントロールは、一度に最大 12 か月を表示できます。</span><span class="sxs-lookup"><span data-stu-id="de481-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="de481-104">既定では、コントロールには、1 か月が表示されますが、数か月間が表示され、コントロール内の配置方法を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="de481-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="de481-105">Calendar ディメンションを変更すると、コントロールのサイズ変更、あるため、新しいディメンションのフォームに十分な空き領域があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de481-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="de481-106">複数の月を表示するには</span><span class="sxs-lookup"><span data-stu-id="de481-106">To display multiple months</span></span>  
  
-   <span data-ttu-id="de481-107">設定、<xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>プロパティに水平および垂直に表示する月の数。</span><span class="sxs-lookup"><span data-stu-id="de481-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="de481-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="de481-108">See also</span></span>
- [<span data-ttu-id="de481-109">MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="de481-109">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="de481-110">方法: Windows フォームの MonthCalendar コントロールで日付の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="de481-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="de481-111">方法: Windows フォーム MonthCalendar コントロールの外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="de481-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
