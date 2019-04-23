---
title: '方法: Windows フォームの MonthCalendar コントロールを使用して特定の日付を太字で表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
ms.openlocfilehash: 27b19e47d108b9af43a6d8882264d62c726ffe56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343268"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="f4726-102">方法: Windows フォームの MonthCalendar コントロールを使用して特定の日付を太字で表示する</span><span class="sxs-lookup"><span data-stu-id="f4726-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="f4726-103">Windows フォーム<xref:System.Windows.Forms.MonthCalendar>コントロールは、単数形の日付または繰り返しごとに、太字での日を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f4726-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="f4726-104">休日や週末などの特別な日に注目させるためにこれを行う場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4726-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="f4726-105">次の 3 つのプロパティは、この機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="f4726-105">Three properties control this feature.</span></span> <span data-ttu-id="f4726-106"><xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>プロパティには、1 つの日付が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4726-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="f4726-107"><xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>プロパティには、毎年を太字で表示される日付が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4726-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="f4726-108"><xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>プロパティには、毎月を太字で表示される日付が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4726-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="f4726-109">これらの各プロパティの配列を含む<xref:System.DateTime>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f4726-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="f4726-110">を追加またはこれらのリストのいずれかから日付を削除するには、追加または削除する必要があります、<xref:System.DateTime>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f4726-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="f4726-111">日付を太字で表示するには</span><span class="sxs-lookup"><span data-stu-id="f4726-111">To make a date appear in bold type</span></span>  
  
1. <span data-ttu-id="f4726-112">作成、<xref:System.DateTime>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f4726-112">Create the <xref:System.DateTime> objects.</span></span>  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2. <span data-ttu-id="f4726-113">呼び出すことによって、1 つの日付を太字、 <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>、 <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>、または<xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A>のメソッド、<xref:System.Windows.Forms.MonthCalendar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="f4726-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="f4726-114">または</span><span class="sxs-lookup"><span data-stu-id="f4726-114">–or–</span></span>  
  
     <span data-ttu-id="f4726-115">太字に日付のセットを一度にすべての配列を作成して<xref:System.DateTime>オブジェクトとプロパティのいずれかに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f4726-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="f4726-116">日付を通常のフォントで表示するには</span><span class="sxs-lookup"><span data-stu-id="f4726-116">To make a date appear in the regular font</span></span>  
  
1. <span data-ttu-id="f4726-117">1 つの太字で表示される日付を呼び出すことによって通常フォントで表示、 <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>、 <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>、または<xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="f4726-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="f4726-118">または</span><span class="sxs-lookup"><span data-stu-id="f4726-118">–or–</span></span>  
  
     <span data-ttu-id="f4726-119">3 つのリストのいずれかから呼び出すことによって、すべての太字で表示される日付を削除、 <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>、 <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>、または<xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="f4726-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <span data-ttu-id="f4726-120">呼び出すことによって、フォントの外観を更新、<xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="f4726-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f4726-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4726-121">See also</span></span>

- [<span data-ttu-id="f4726-122">MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="f4726-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="f4726-123">方法: Windows フォームの MonthCalendar コントロールで日付の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4726-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="f4726-124">方法: Windows フォーム MonthCalendar コントロールの外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="f4726-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="f4726-125">方法: Windows フォームの MonthCalendar コントロールにおいて複数の月を表示します。</span><span class="sxs-lookup"><span data-stu-id="f4726-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
