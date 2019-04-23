---
title: TrackBar コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 1606db73485944f3dfa8b9c084bffda817520c7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200637"
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="4751f-102">TrackBar コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="4751f-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="4751f-103">Windows フォーム<xref:System.Windows.Forms.TrackBar>コントロール ("slider"コントロールと呼ばれることもあります) が大量の情報をナビゲートするのか、数値の設定を視覚的に調整するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4751f-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="4751f-104"><xref:System.Windows.Forms.TrackBar>コントロールに 2 つの部分がある: 一般的に、スライダーとティックとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4751f-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="4751f-105">Thumb は、調整可能な部分です。</span><span class="sxs-lookup"><span data-stu-id="4751f-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="4751f-106">その位置に対応して、<xref:System.Windows.Forms.TrackBar.Value%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4751f-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="4751f-107">目盛りは、一定の間隔で間隔が視覚インジケーターです。</span><span class="sxs-lookup"><span data-stu-id="4751f-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="4751f-108">単位を指定し、水平方向または垂直方向に配置することができますが、トラック バーが移動します。</span><span class="sxs-lookup"><span data-stu-id="4751f-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="4751f-109">たとえば、トラック バーを使用して、システムのカーソルの点滅速度やマウス速度を制御する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4751f-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="4751f-110">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="4751f-110">Key Properties</span></span>  
 <span data-ttu-id="4751f-111">キー プロパティ、<xref:System.Windows.Forms.TrackBar>コントロールは<xref:System.Windows.Forms.TrackBar.Value%2A>、 <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>、 <xref:System.Windows.Forms.TrackBar.Minimum%2A>、および<xref:System.Windows.Forms.TrackBar.Maximum%2A>します。</span><span class="sxs-lookup"><span data-stu-id="4751f-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <span data-ttu-id="4751f-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> 目盛りの間隔です。</span><span class="sxs-lookup"><span data-stu-id="4751f-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> is the spacing of the ticks.</span></span> <span data-ttu-id="4751f-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> <xref:System.Windows.Forms.TrackBar.Maximum%2A>トラック バーを表すことができる最小値と最大値です。</span><span class="sxs-lookup"><span data-stu-id="4751f-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="4751f-114">その他の 2 つの重要なプロパティが<xref:System.Windows.Forms.TrackBar.SmallChange%2A>と<xref:System.Windows.Forms.TrackBar.LargeChange%2A>します。</span><span class="sxs-lookup"><span data-stu-id="4751f-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="4751f-115">値、<xref:System.Windows.Forms.TrackBar.SmallChange%2A>プロパティは、thumb が押された、左または右矢印キーを持つへの応答での位置の数。</span><span class="sxs-lookup"><span data-stu-id="4751f-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="4751f-116">値、<xref:System.Windows.Forms.TrackBar.LargeChange%2A>プロパティがつまみが移動すると、PAGE UP または PAGE DOWN キーを押すと、またはマウスへの応答では、トラック バーのつまみの両側でクリックしての位置の数。</span><span class="sxs-lookup"><span data-stu-id="4751f-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4751f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4751f-117">See also</span></span>

- <xref:System.Windows.Forms.TrackBar>
- [<span data-ttu-id="4751f-118">TrackBar コントロール</span><span class="sxs-lookup"><span data-stu-id="4751f-118">TrackBar Control</span></span>](trackbar-control-windows-forms.md)
