---
title: MonthCalendar コントロールに複数の月を表示する
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
ms.openlocfilehash: 5d3925bc19ddcd67742f0ab8b5b2e45530820f38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745899"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="0eb5e-102">方法 : Windows フォームの MonthCalendar コントロールにおいて複数の月を表示する</span><span class="sxs-lookup"><span data-stu-id="0eb5e-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="0eb5e-103">Windows フォーム <xref:System.Windows.Forms.MonthCalendar> コントロールには、一度に最大12か月を表示できます。</span><span class="sxs-lookup"><span data-stu-id="0eb5e-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="0eb5e-104">既定では、コントロールに表示されるのは1か月のみですが、表示される月の数と、コントロール内での表示方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0eb5e-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="0eb5e-105">カレンダーの寸法を変更すると、コントロールのサイズが変更されます。そのため、フォームには新しい寸法用に十分な余裕があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0eb5e-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="0eb5e-106">複数の月を表示するには</span><span class="sxs-lookup"><span data-stu-id="0eb5e-106">To display multiple months</span></span>  
  
- <span data-ttu-id="0eb5e-107"><xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> プロパティを、水平方向および垂直方向に表示する月数に設定します。</span><span class="sxs-lookup"><span data-stu-id="0eb5e-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0eb5e-108">参照</span><span class="sxs-lookup"><span data-stu-id="0eb5e-108">See also</span></span>

- [<span data-ttu-id="0eb5e-109">MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="0eb5e-109">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="0eb5e-110">方法: Windows フォームの MonthCalendar コントロールで日付の範囲を選択する</span><span class="sxs-lookup"><span data-stu-id="0eb5e-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="0eb5e-111">方法: Windows フォームの MonthCalendar コントロールの外観を変更する</span><span class="sxs-lookup"><span data-stu-id="0eb5e-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
