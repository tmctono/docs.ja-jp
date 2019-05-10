---
title: '方法: BetweenShowDelay プロパティを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 9b63675ec21294496117860aa5b58af132c4284a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614529"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="e2253-102">方法: BetweenShowDelay プロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="e2253-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="e2253-103">使用する方法を示します、<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>時間プロパティのツールヒントがすぐに表示されるように、ほとんどまたはまったくない遅延が、移動したときに、ユーザー、マウスのポインター 1 つのヒントからを別。</span><span class="sxs-lookup"><span data-stu-id="e2253-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2253-104">例</span><span class="sxs-lookup"><span data-stu-id="e2253-104">Example</span></span>  
 <span data-ttu-id="e2253-105">次の例では、<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>プロパティが 1 秒 (1000 ミリ秒) に設定し、 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 2 秒 (2000 ミリ秒) の両方に設定されている<xref:System.Windows.Shapes.Ellipse>コントロール。</span><span class="sxs-lookup"><span data-stu-id="e2253-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="e2253-106">省略記号のいずれかのツールヒントを表示し、マウス ポインターを移動もう 1 つの楕円に一時停止、2 秒以内にしていて、すぐに 2 番目の楕円のツールヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="e2253-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="e2253-107">次のシナリオのいずれかで、<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>が適用されることが表示されるまで 1 秒間待機する 2 番目の楕円のツールヒントを停止します。</span><span class="sxs-lookup"><span data-stu-id="e2253-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
- <span data-ttu-id="e2253-108">移動にかかる時間 2 番目のボタンは 2 秒以上が。</span><span class="sxs-lookup"><span data-stu-id="e2253-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
- <span data-ttu-id="e2253-109">ツールヒントが最初の楕円の時間間隔の先頭に表示されていない場合。</span><span class="sxs-lookup"><span data-stu-id="e2253-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="e2253-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2253-110">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="e2253-111">方法トピック</span><span class="sxs-lookup"><span data-stu-id="e2253-111">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="e2253-112">ToolTip の概要</span><span class="sxs-lookup"><span data-stu-id="e2253-112">ToolTip Overview</span></span>](tooltip-overview.md)
