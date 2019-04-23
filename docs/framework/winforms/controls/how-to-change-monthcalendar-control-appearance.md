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
ms.openlocfilehash: 233143099996759cc006b3f28b984938554a0d18
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199922"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="aa3df-102">方法: Windows フォームの MonthCalendar コントロールの外観を変更する</span><span class="sxs-lookup"><span data-stu-id="aa3df-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="aa3df-103">Windows フォーム<xref:System.Windows.Forms.MonthCalendar>コントロールでは、さまざまな方法で、カレンダーの外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="aa3df-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="aa3df-104">たとえば、配色を設定でき、または週数と現在の日付を非表示に選択できます。</span><span class="sxs-lookup"><span data-stu-id="aa3df-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="aa3df-105">月間予定表の配色を変更するには</span><span class="sxs-lookup"><span data-stu-id="aa3df-105">To change the month calendar's color scheme</span></span>  
  
-   <span data-ttu-id="aa3df-106">プロパティを設定します。 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>、<xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>と<xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="aa3df-107"><xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>も、プロパティは、曜日のフォントの色を決定します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="aa3df-108"><xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>プロパティ直前および直後の表示されている月または数か月の日付の色を決定します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    >  <span data-ttu-id="aa3df-109">以降 Windows vista では、テーマによっては、いくつかのプロパティを設定する可能性がありますいないの外観を変更、予定表。</span><span class="sxs-lookup"><span data-stu-id="aa3df-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="aa3df-110">Windows が設定されて、Aero のテーマを使用する場合の設定など、 <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>、 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>、 <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>、または<xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>プロパティは影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="aa3df-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="aa3df-111">これは、実行時に、現在のオペレーティング システム テーマから派生した外観の予定表の更新バージョンがレンダリングされるためです。</span><span class="sxs-lookup"><span data-stu-id="aa3df-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="aa3df-112">これらのプロパティを使用し、カレンダーの以前のバージョンを有効にする場合は、アプリケーションの visual スタイルが無効にできます。</span><span class="sxs-lookup"><span data-stu-id="aa3df-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="aa3df-113">Visual スタイルを無効にすると、アプリケーションでは、その他のコントロールの動作と外観が影響可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aa3df-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="aa3df-114">Visual Basic での visual スタイルを無効にするには、プロジェクト デザイナーを開きし、オフに、**を有効にする XP visual スタイル**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="aa3df-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="aa3df-115">C# での visual スタイルを無効にする Program.cs を開きをコメント アウト`Application.EnableVisualStyles();`します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="aa3df-116">Visual スタイルの詳細については、次を参照してください。 [Visual スタイルを有効にする](/windows/desktop/controls/cookbook-overview)します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-116">For more information about visual styles, see [Enabling Visual Styles](/windows/desktop/controls/cookbook-overview).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="aa3df-117">コントロールの下部にある現在の日付を表示するには</span><span class="sxs-lookup"><span data-stu-id="aa3df-117">To display the current date at the bottom of the control</span></span>  
  
-   <span data-ttu-id="aa3df-118"><xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="aa3df-119">次の例は、フォームがダブルクリックされたときに、今日の日付を省略すると表示を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="aa3df-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="aa3df-120">(Visual c#、 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、イベント ハンドラーを登録するフォームのコンス トラクターで、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-120">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="aa3df-121">週番号を表示するには</span><span class="sxs-lookup"><span data-stu-id="aa3df-121">To display week numbers</span></span>  
  
-   <span data-ttu-id="aa3df-122"><xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="aa3df-123">コードで、または [プロパティ] ウィンドウで、このプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="aa3df-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="aa3df-124">別の列の週の最初の日の左側に週番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa3df-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="aa3df-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa3df-125">See also</span></span>

- [<span data-ttu-id="aa3df-126">MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="aa3df-126">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="aa3df-127">方法: Windows フォームの MonthCalendar コントロールで日付の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="aa3df-128">方法: 特定の日で、Windows で太字で表示フォームの MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="aa3df-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="aa3df-129">方法: Windows フォームの MonthCalendar コントロールにおいて複数の月を表示します。</span><span class="sxs-lookup"><span data-stu-id="aa3df-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
