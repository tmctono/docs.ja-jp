---
title: DateTimePicker コントロールを使用してカスタム形式で日付を表示する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: a27dbe737b81af86c0ac50b791bcd87bafe05b4f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745932"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="742c5-102">方法 : Windows フォームの DateTimePicker コントロールを使用してカスタム形式で日付を表示する</span><span class="sxs-lookup"><span data-stu-id="742c5-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="742c5-103">Windows フォーム <xref:System.Windows.Forms.DateTimePicker> コントロールを使用すると、コントロールの日付と時刻の表示形式を柔軟に設定できます。</span><span class="sxs-lookup"><span data-stu-id="742c5-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="742c5-104"><xref:System.Windows.Forms.DateTimePicker.Format%2A> プロパティを使用すると、<xref:System.Windows.Forms.DateTimePickerFormat>に示されている定義済みの形式から選択できます。</span><span class="sxs-lookup"><span data-stu-id="742c5-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="742c5-105">これらのいずれも目的に適していない場合は、<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>に記載されている書式設定文字を使用して独自の書式スタイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="742c5-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="742c5-106">カスタム書式を表示するには</span><span class="sxs-lookup"><span data-stu-id="742c5-106">To display a custom format</span></span>  
  
1. <span data-ttu-id="742c5-107"><xref:System.Windows.Forms.DateTimePicker.Format%2A> プロパティを `DateTimePickerFormat.Custom` に設定します。</span><span class="sxs-lookup"><span data-stu-id="742c5-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="742c5-108"><xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> プロパティを書式設定文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="742c5-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="742c5-109">書式設定された値にテキストを追加するには</span><span class="sxs-lookup"><span data-stu-id="742c5-109">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="742c5-110">"M" のような書式指定文字ではない任意の文字、または ":" のような区切り記号を使用するには、単一引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="742c5-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="742c5-111">たとえば、次の書式設定文字列では、英語 (米国) カルチャの現在の日付が "Today は、05:30:31 年3月 02, 2012" の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="742c5-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     <span data-ttu-id="742c5-112">カルチャの設定によっては、単一引用符で囲まれていない文字は変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="742c5-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="742c5-113">たとえば、上記の書式指定文字列は、現在の日付を英語 (米国) カルチャの "Today は05:30:31 年3月 02, 2012" の形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="742c5-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="742c5-114">先頭のコロンは、"hh: mm: ss" のように区切り文字として使用されないため、単一引用符で囲まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="742c5-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="742c5-115">別のカルチャでは、"今日は: 05.30.31 金曜日3月 02, 2012" と表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="742c5-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="742c5-116">参照</span><span class="sxs-lookup"><span data-stu-id="742c5-116">See also</span></span>

- [<span data-ttu-id="742c5-117">DateTimePicker コントロール</span><span class="sxs-lookup"><span data-stu-id="742c5-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="742c5-118">方法: Windows フォームの DateTimePicker コントロールを使用して日付を設定および取得する</span><span class="sxs-lookup"><span data-stu-id="742c5-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
