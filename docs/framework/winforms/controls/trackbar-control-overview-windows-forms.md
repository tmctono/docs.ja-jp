---
title: TrackBar コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 6901405100df4633c84850757f55b756bc9a0199
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741462"
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="717ed-102">TrackBar コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="717ed-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="717ed-103">Windows フォーム <xref:System.Windows.Forms.TrackBar> コントロール ("スライダー" コントロールとも呼ばれます) は、大量の情報を移動したり、数値設定を視覚的に調整したりするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="717ed-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="717ed-104"><xref:System.Windows.Forms.TrackBar> コントロールには、つまみ (スライダーとも呼ばれます) と目盛りの2つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="717ed-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="717ed-105">つまみは、調整できる部分です。</span><span class="sxs-lookup"><span data-stu-id="717ed-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="717ed-106">その位置は、<xref:System.Windows.Forms.TrackBar.Value%2A> プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="717ed-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="717ed-107">目盛りは、一定の間隔で間隔が一定の視覚的インジケーターです。</span><span class="sxs-lookup"><span data-stu-id="717ed-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="717ed-108">Trackbar は、指定した単位で移動し、水平方向または垂直方向に揃えることができます。</span><span class="sxs-lookup"><span data-stu-id="717ed-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="717ed-109">たとえば、トラックバーを使用して、システムのカーソルの点滅速度またはマウス速度を制御できます。</span><span class="sxs-lookup"><span data-stu-id="717ed-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="717ed-110">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="717ed-110">Key Properties</span></span>  
 <span data-ttu-id="717ed-111"><xref:System.Windows.Forms.TrackBar> コントロールの主要なプロパティは、<xref:System.Windows.Forms.TrackBar.Value%2A>、<xref:System.Windows.Forms.TrackBar.TickFrequency%2A>、<xref:System.Windows.Forms.TrackBar.Minimum%2A>、および <xref:System.Windows.Forms.TrackBar.Maximum%2A>です。</span><span class="sxs-lookup"><span data-stu-id="717ed-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <span data-ttu-id="717ed-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> は、ティックの間隔です。</span><span class="sxs-lookup"><span data-stu-id="717ed-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> is the spacing of the ticks.</span></span> <span data-ttu-id="717ed-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> と <xref:System.Windows.Forms.TrackBar.Maximum%2A> は、トラックバーに表示できる最小値と最大値です。</span><span class="sxs-lookup"><span data-stu-id="717ed-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="717ed-114">もう1つの重要なプロパティは、<xref:System.Windows.Forms.TrackBar.SmallChange%2A> と <xref:System.Windows.Forms.TrackBar.LargeChange%2A>です。</span><span class="sxs-lookup"><span data-stu-id="717ed-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="717ed-115"><xref:System.Windows.Forms.TrackBar.SmallChange%2A> プロパティの値は、左または右方向キーが押されたときに、thumb が移動する位置の数です。</span><span class="sxs-lookup"><span data-stu-id="717ed-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="717ed-116"><xref:System.Windows.Forms.TrackBar.LargeChange%2A> プロパティの値は、pageup キーが押されたとき、またはつまみの両側のトラックバーにマウスクリックが反応したときに、thumb が移動する位置の数です。</span><span class="sxs-lookup"><span data-stu-id="717ed-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="717ed-117">参照</span><span class="sxs-lookup"><span data-stu-id="717ed-117">See also</span></span>

- <xref:System.Windows.Forms.TrackBar>
- [<span data-ttu-id="717ed-118">TrackBar コントロール</span><span class="sxs-lookup"><span data-stu-id="717ed-118">TrackBar Control</span></span>](trackbar-control-windows-forms.md)
