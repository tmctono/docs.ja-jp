---
title: '方法: Windows フォームの MonthCalendar コントロールの外観を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 5582624d881b2d8039bcd5e8ac45e548c7b38f57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929049"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="85a31-102">方法: Windows フォームの MonthCalendar コントロールの外観を変更する</span><span class="sxs-lookup"><span data-stu-id="85a31-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="85a31-103">Windows フォーム<xref:System.Windows.Forms.MonthCalendar>コントロールを使用すると、さまざまな方法でカレンダーの外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="85a31-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="85a31-104">たとえば、配色を設定し、週番号と現在の日付を表示または非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="85a31-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="85a31-105">月の予定表の配色を変更するには</span><span class="sxs-lookup"><span data-stu-id="85a31-105">To change the month calendar's color scheme</span></span>  
  
- <span data-ttu-id="85a31-106">、、などの<xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>プロパティを設定します。<xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A></span><span class="sxs-lookup"><span data-stu-id="85a31-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="85a31-107">プロパティ<xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>は、曜日のフォントの色も決定します。</span><span class="sxs-lookup"><span data-stu-id="85a31-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="85a31-108">プロパティ<xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>は、表示される月または月の前と後の日付の色を決定します。</span><span class="sxs-lookup"><span data-stu-id="85a31-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="85a31-109">Windows Vista 以降では、テーマによっては、一部のプロパティを設定しても予定表の外観が変更されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="85a31-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="85a31-110">たとえば、Windows が Aero テーマを使用するように設定されて<xref:System.Windows.Forms.MonthCalendar.BackColor%2A>いる<xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>場合<xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>、、 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 、、またはの各プロパティを設定しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="85a31-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="85a31-111">これは、更新されたバージョンのカレンダーが、現在のオペレーティングシステムのテーマから実行時に生成された外観でレンダリングされるためです。</span><span class="sxs-lookup"><span data-stu-id="85a31-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="85a31-112">これらのプロパティを使用して、カレンダーの以前のバージョンを有効にする場合は、アプリケーションの視覚スタイルを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="85a31-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="85a31-113">視覚スタイルを無効にすると、アプリケーション内の他のコントロールの外観と動作に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85a31-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="85a31-114">Visual Basic で視覚スタイルを無効にするには、プロジェクトデザイナーを開き、[ **XP visual スタイルを有効に**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="85a31-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="85a31-115">でC#視覚スタイルを無効にするには、Program.cs `Application.EnableVisualStyles();`を開き、コメントアウトします。</span><span class="sxs-lookup"><span data-stu-id="85a31-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="85a31-116">視覚スタイルの詳細については、「 [Visual スタイルの有効化](/windows/desktop/controls/cookbook-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a31-116">For more information about visual styles, see [Enabling Visual Styles](/windows/desktop/controls/cookbook-overview).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="85a31-117">コントロールの下部に現在の日付を表示するには</span><span class="sxs-lookup"><span data-stu-id="85a31-117">To display the current date at the bottom of the control</span></span>  
  
- <span data-ttu-id="85a31-118"><xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="85a31-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="85a31-119">次の例では、フォームがダブルクリックされたときの今日の日付の表示と非表示を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="85a31-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     <span data-ttu-id="85a31-120">(ビジュアルC#、ビジュアルC++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="85a31-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="85a31-121">週番号を表示するには</span><span class="sxs-lookup"><span data-stu-id="85a31-121">To display week numbers</span></span>  
  
- <span data-ttu-id="85a31-122"><xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="85a31-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="85a31-123">このプロパティは、コードまたはプロパティウィンドウで設定できます。</span><span class="sxs-lookup"><span data-stu-id="85a31-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="85a31-124">週番号は、週の最初の曜日の左側にある別の列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="85a31-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="85a31-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="85a31-125">See also</span></span>

- [<span data-ttu-id="85a31-126">MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="85a31-126">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="85a31-127">方法: Windows フォーム MonthCalendar コントロールで日付の範囲を選択する</span><span class="sxs-lookup"><span data-stu-id="85a31-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="85a31-128">方法: Windows フォーム MonthCalendar コントロールを使用して特定の日を太字で表示する</span><span class="sxs-lookup"><span data-stu-id="85a31-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="85a31-129">方法: Windows フォーム MonthCalendar コントロールに複数の月を表示する</span><span class="sxs-lookup"><span data-stu-id="85a31-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
