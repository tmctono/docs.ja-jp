---
title: HScrollBar コントロールと VScrollBar コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: d4a7912a5781fc583357affa728f7d81059b5cf9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928575"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="f5369-102">HScrollBar コントロールと VScrollBar コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="f5369-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="f5369-103">Windows フォーム<xref:System.Windows.Forms.ScrollBar>または垂直方向に水平方向にスクロールすることにより、アプリケーションまたはコントロール内の項目または大量の情報の長いリストを簡単にナビゲートを提供するコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5369-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="f5369-104">スクロール バー、Windows インターフェイスの一般的な要素は、そのため、<xref:System.Windows.Forms.ScrollBar>から派生していないコントロールのコントロールが使用される多くの場合、<xref:System.Windows.Forms.ScrollableControl>クラス。</span><span class="sxs-lookup"><span data-stu-id="f5369-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="f5369-105">同様に、多くの開発者が組み込む選択、<xref:System.Windows.Forms.ScrollBar>独自のユーザー コントロールを作成するときを制御します。</span><span class="sxs-lookup"><span data-stu-id="f5369-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="f5369-106"><xref:System.Windows.Forms.HScrollBar> (水平) と<xref:System.Windows.Forms.VScrollBar>(垂直) コントロールは、他のコントロールから独立して動作し、イベント、プロパティ、およびメソッドの独自セットがあります。</span><span class="sxs-lookup"><span data-stu-id="f5369-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <span data-ttu-id="f5369-107"><xref:System.Windows.Forms.ScrollBar> コントロールは、テキスト ボックス、リスト ボックス、コンボ ボックス、または MDI フォームにアタッチされている組み込みのスクロール バーと同じではありません (、<xref:System.Windows.Forms.TextBox>コントロールが、<xref:System.Windows.Forms.TextBox.ScrollBars%2A>コントロールに関連付けられているスクロール バーを非表示プロパティ)。</span><span class="sxs-lookup"><span data-stu-id="f5369-107"><xref:System.Windows.Forms.ScrollBar> controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="f5369-108"><xref:System.Windows.Forms.ScrollBar>使用を制御、<xref:System.Windows.Forms.ScrollBar.Scroll>に沿ってスクロール バーのスクロール ボックス (つまみとも呼ばれます) の動きを監視するイベントです。</span><span class="sxs-lookup"><span data-stu-id="f5369-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="f5369-109">使用して、<xref:System.Windows.Forms.ScrollBar.Scroll>イベントがドラッグされているようにスクロール バーの値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f5369-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="f5369-110">Value プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5369-110">Value Property</span></span>  
 <span data-ttu-id="f5369-111"><xref:System.Windows.Forms.ScrollBar.Value%2A>プロパティ (つまり、既定では、0) は、`integer`スクロール バーのスクロール ボックスの位置に対応する値。</span><span class="sxs-lookup"><span data-stu-id="f5369-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="f5369-112">スクロール ボックスの位置は、最小値では、(水平スクロール バー) の左端の位置または (垂直スクロール バーの上端の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="f5369-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="f5369-113">スクロール ボックスが最大値、一番右にスクロール ボックスの移動、または下部にある位置にある場合です。</span><span class="sxs-lookup"><span data-stu-id="f5369-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="f5369-114">同様に、範囲の上端と下端の中間値は、スクロール バーの途中でのスクロール ボックスのリーディング エッジを配置します。</span><span class="sxs-lookup"><span data-stu-id="f5369-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="f5369-115">マウスのクリックを使用して、スクロール バーの値を変更する、だけでなく、ユーザーがバーに沿って任意の時点のスクロール ボックスをドラッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f5369-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="f5369-116">結果の値は、スクロール ボックスの位置によって異なりますが、範囲の中では常に、<xref:System.Windows.Forms.ScrollBar.Minimum%2A>に<xref:System.Windows.Forms.ScrollBar.Maximum%2A>ユーザーによって設定されるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="f5369-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="f5369-117">LargeChange と SmallChange プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5369-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="f5369-118">PAGE UP または PAGE DOWN キーを押すか、スクロール バーのトラック、スクロール ボックスのいずれかの側をクリックしたときに、<xref:System.Windows.Forms.ScrollBar.Value%2A>プロパティの変更で設定された値に従って、<xref:System.Windows.Forms.ScrollBar.LargeChange%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f5369-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="f5369-119">キーまたはスクロール バーのボタンのクリックしたとき、ユーザーが矢印の 1 つ、<xref:System.Windows.Forms.ScrollBar.Value%2A>プロパティの変更で設定された値に従って、<xref:System.Windows.Forms.ScrollBar.SmallChange%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f5369-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5369-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5369-120">See also</span></span>

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [<span data-ttu-id="f5369-121">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="f5369-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
