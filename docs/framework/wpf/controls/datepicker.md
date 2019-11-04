---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 3e66b2306c11c54db14eb05cc6860257635cc653
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460356"
---
# <a name="datepicker"></a><span data-ttu-id="5dcc0-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="5dcc0-102">DatePicker</span></span>
<span data-ttu-id="5dcc0-103"><xref:System.Windows.Controls.DatePicker> コントロールを使用すると、ユーザーはテキストフィールドに入力するか、ドロップダウン <xref:System.Windows.Controls.Calendar> コントロールを使用して、日付を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5dcc0-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="5dcc0-104">次の図は、<xref:System.Windows.Controls.DatePicker>を示しています。</span><span class="sxs-lookup"><span data-stu-id="5dcc0-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="5dcc0-105">![DatePicker コントロール](./media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="5dcc0-105">![DatePicker control](./media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="5dcc0-106">DatePicker コントロール</span><span class="sxs-lookup"><span data-stu-id="5dcc0-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="5dcc0-107"><xref:System.Windows.Controls.DatePicker> コントロールのプロパティの多くは、組み込みの <xref:System.Windows.Controls.Calendar>を管理するためのものであり、<xref:System.Windows.Controls.Calendar>の同等のプロパティと同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="5dcc0-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="5dcc0-108">特に、<xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>、および <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> の各プロパティは、対応する <xref:System.Windows.Controls.Calendar> と同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="5dcc0-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="5dcc0-109">詳細については、「<xref:System.Windows.Controls.Calendar>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dcc0-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="5dcc0-110">ユーザーは、テキストフィールドに日付を直接入力できます。これにより、<xref:System.Windows.Controls.DatePicker.Text%2A> プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="5dcc0-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="5dcc0-111"><xref:System.Windows.Controls.DatePicker> が、入力した文字列を有効な日付に変換できない場合は、<xref:System.Windows.Controls.DatePicker.DateValidationError> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="5dcc0-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="5dcc0-112">既定では、これによって例外が発生しますが、<xref:System.Windows.Controls.DatePicker.DateValidationError> のイベントハンドラーは、<xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> プロパティを `false` に設定し、例外が発生しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5dcc0-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dcc0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dcc0-113">See also</span></span>

- [<span data-ttu-id="5dcc0-114">コントロール</span><span class="sxs-lookup"><span data-stu-id="5dcc0-114">Controls</span></span>](index.md)
- [<span data-ttu-id="5dcc0-115">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5dcc0-115">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
