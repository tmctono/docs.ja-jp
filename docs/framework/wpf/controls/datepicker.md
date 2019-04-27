---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 555bf31b27ba233ffa54438077984b02b5e3084a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911985"
---
# <a name="datepicker"></a><span data-ttu-id="5bc97-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="5bc97-102">DatePicker</span></span>
<span data-ttu-id="5bc97-103"><xref:System.Windows.Controls.DatePicker>コントロールによりユーザーはテキスト フィールドにいずれかを入力するか、ドロップダウンを使用して日付を選択する<xref:System.Windows.Controls.Calendar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="5bc97-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="5bc97-104">次の図は、<xref:System.Windows.Controls.DatePicker>します。</span><span class="sxs-lookup"><span data-stu-id="5bc97-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="5bc97-105">![DatePicker コントロール](./media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="5bc97-105">![DatePicker control](./media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="5bc97-106">DatePicker コントロール</span><span class="sxs-lookup"><span data-stu-id="5bc97-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="5bc97-107">多くを<xref:System.Windows.Controls.DatePicker>コントロールのプロパティは、その組み込みを管理するため<xref:System.Windows.Controls.Calendar>と同等のプロパティとまったく同様に関数<xref:System.Windows.Controls.Calendar>します。</span><span class="sxs-lookup"><span data-stu-id="5bc97-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="5bc97-108">具体的には、 <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>、 <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>、 <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>、 <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>、 <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>、 <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>、および<xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType>プロパティ関数と同様に、<xref:System.Windows.Controls.Calendar>の対応します。</span><span class="sxs-lookup"><span data-stu-id="5bc97-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="5bc97-109">詳細については、「 <xref:System.Windows.Controls.Calendar> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc97-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="5bc97-110">ユーザーが日付を入力設定テキスト フィールドに直接、<xref:System.Windows.Controls.DatePicker.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5bc97-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="5bc97-111">場合、<xref:System.Windows.Controls.DatePicker>有効な日付を入力した文字列を変換することはできません、<xref:System.Windows.Controls.DatePicker.DateValidationError>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="5bc97-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="5bc97-112">既定では、これにより、イベント ハンドラーが例外<xref:System.Windows.Controls.DatePicker.DateValidationError>を設定できます、<xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A>プロパティを`false`と例外が発生しているようにします。</span><span class="sxs-lookup"><span data-stu-id="5bc97-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc97-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bc97-113">See also</span></span>

- [<span data-ttu-id="5bc97-114">コントロール</span><span class="sxs-lookup"><span data-stu-id="5bc97-114">Controls</span></span>](index.md)
- [<span data-ttu-id="5bc97-115">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5bc97-115">Styling and Templating</span></span>](styling-and-templating.md)
