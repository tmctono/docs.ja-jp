---
title: '方法: Windows フォームの DateTimePicker コントロールを使用してカスタム形式で日付を表示する'
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
ms.openlocfilehash: 08d5a505229cd434dbf82e8ae4624bb418efd379
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335941"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="2a8cb-102">方法: Windows フォームの DateTimePicker コントロールを使用してカスタム形式で日付を表示する</span><span class="sxs-lookup"><span data-stu-id="2a8cb-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="2a8cb-103">Windows フォーム<xref:System.Windows.Forms.DateTimePicker>柔軟にコントロールで日付と時刻の表示の書式設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="2a8cb-104"><xref:System.Windows.Forms.DateTimePicker.Format%2A>プロパティに表示される定義済みの形式から選択することができます、<xref:System.Windows.Forms.DateTimePickerFormat>します。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="2a8cb-105">形式指定文字を使用して、独自の書式スタイルを作成するには、目的のための適切な場合、これらのいずれも<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>します。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="2a8cb-106">カスタム形式を表示するには</span><span class="sxs-lookup"><span data-stu-id="2a8cb-106">To display a custom format</span></span>  
  
1. <span data-ttu-id="2a8cb-107"><xref:System.Windows.Forms.DateTimePicker.Format%2A> プロパティを `DateTimePickerFormat.Custom` に設定します。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="2a8cb-108">設定、<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>プロパティを書式指定文字列。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="2a8cb-109">テキスト書式設定された値を追加するには</span><span class="sxs-lookup"><span data-stu-id="2a8cb-109">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="2a8cb-110">"M"のような書式指定文字またはなどの区切り記号以外の任意の文字を囲む単一引用符を使用して":"です。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="2a8cb-111">たとえば、次の書式指定文字列には、形式で現在の日付が表示されます。"今日は。05時 30分: 31 金曜日 March 02、2012"英語 (米国) カルチャ。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="2a8cb-112">カルチャの設定に応じて単一引用符で囲まれていない文字は変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="2a8cb-113">たとえば、上記の書式指定文字列には、形式の現在の日付が表示されます。"今日は。05時 30分: 31 金曜日 March 02、2012"英語 (米国) カルチャ。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="2a8cb-114">"Hh:mm:ss"であるため、区切り記号をするものではありませんので、最初のコロンが単一引用符で囲まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="2a8cb-115">別のカルチャでは、形式がありますとして表示されます"今日は。05.30.31 金曜日 March 02、2012"。</span><span class="sxs-lookup"><span data-stu-id="2a8cb-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a8cb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a8cb-116">See also</span></span>

- [<span data-ttu-id="2a8cb-117">DateTimePicker コントロール</span><span class="sxs-lookup"><span data-stu-id="2a8cb-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="2a8cb-118">方法: Windows フォームの DateTimePicker コントロールを設定し、戻り値の日付</span><span class="sxs-lookup"><span data-stu-id="2a8cb-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
