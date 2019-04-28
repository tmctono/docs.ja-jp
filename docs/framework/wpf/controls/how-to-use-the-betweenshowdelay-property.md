---
title: '方法: BetweenShowDelay プロパティを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: b6d55c72c8264546949833fc086937a8b1fe2540
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696055"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="0ad61-102">方法: BetweenShowDelay プロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="0ad61-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="0ad61-103">使用する方法を示します、<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>時間プロパティのツールヒントがすぐに表示されるように、ほとんどまたはまったくない遅延が、移動したときに、ユーザー、マウスのポインター 1 つのヒントからを別。</span><span class="sxs-lookup"><span data-stu-id="0ad61-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ad61-104">例</span><span class="sxs-lookup"><span data-stu-id="0ad61-104">Example</span></span>  
 <span data-ttu-id="0ad61-105">次の例では、<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>プロパティが 1 秒 (1000 ミリ秒) に設定し、 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 2 秒 (2000 ミリ秒) の両方に設定されている<xref:System.Windows.Shapes.Ellipse>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0ad61-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="0ad61-106">省略記号のいずれかのツールヒントを表示し、マウス ポインターを移動もう 1 つの楕円に一時停止、2 秒以内にしていて、すぐに 2 番目の楕円のツールヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="0ad61-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="0ad61-107">次のシナリオのいずれかで、<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>が適用されることが表示されるまで 1 秒間待機する 2 番目の楕円のツールヒントを停止します。</span><span class="sxs-lookup"><span data-stu-id="0ad61-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
- <span data-ttu-id="0ad61-108">移動にかかる時間 2 番目のボタンは 2 秒以上が。</span><span class="sxs-lookup"><span data-stu-id="0ad61-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
- <span data-ttu-id="0ad61-109">ツールヒントが最初の楕円の時間間隔の先頭に表示されていない場合。</span><span class="sxs-lookup"><span data-stu-id="0ad61-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="0ad61-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ad61-110">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="0ad61-111">方法トピック</span><span class="sxs-lookup"><span data-stu-id="0ad61-111">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="0ad61-112">ToolTip の概要</span><span class="sxs-lookup"><span data-stu-id="0ad61-112">ToolTip Overview</span></span>](tooltip-overview.md)
