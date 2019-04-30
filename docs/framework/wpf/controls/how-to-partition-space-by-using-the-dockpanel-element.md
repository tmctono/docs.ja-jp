---
title: '方法: DockPanel 要素を使用して領域を分割する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: ab51270644bf370944ebc933c765b40c528681c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052184"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="fc98e-102">方法: DockPanel 要素を使用して領域を分割する</span><span class="sxs-lookup"><span data-stu-id="fc98e-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="fc98e-103">次の例では、単純な[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]フレームワークを使用して、<xref:System.Windows.Controls.DockPanel>要素。</span><span class="sxs-lookup"><span data-stu-id="fc98e-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="fc98e-104"><xref:System.Windows.Controls.DockPanel>子要素に使用可能な領域をパーティション分割します。</span><span class="sxs-lookup"><span data-stu-id="fc98e-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc98e-105">例</span><span class="sxs-lookup"><span data-stu-id="fc98e-105">Example</span></span>  
 <span data-ttu-id="fc98e-106">この例では、<xref:System.Windows.Controls.DockPanel.Dock%2A>プロパティで、同一の 2 つをドッキングするのには、添付プロパティ<xref:System.Windows.Controls.Border>要素で、<xref:System.Windows.Controls.Dock.Top>のパーティション分割された領域。</span><span class="sxs-lookup"><span data-stu-id="fc98e-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="fc98e-107">3 番目<xref:System.Windows.Controls.Border>に要素がドッキングされている、 <xref:System.Windows.Controls.Dock.Left>、その幅 200 ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="fc98e-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="fc98e-108">4 番目<xref:System.Windows.Controls.Border>にドッキングされて、<xref:System.Windows.Controls.Dock.Bottom>画面。</span><span class="sxs-lookup"><span data-stu-id="fc98e-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="fc98e-109">最後の<xref:System.Windows.Controls.Border>要素は、残りの領域を自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="fc98e-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="fc98e-110">既定での最後の子、<xref:System.Windows.Controls.DockPanel>要素は、残りの未割り当て領域を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="fc98e-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="fc98e-111">この動作にしない場合は、`LastChildFill="False"`を設定します。</span><span class="sxs-lookup"><span data-stu-id="fc98e-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="fc98e-112">コンパイル済みのアプリケーションでは、次のような新しい UI を生成します。</span><span class="sxs-lookup"><span data-stu-id="fc98e-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="fc98e-113">![代表的な DockPanel シナリオ: ](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="fc98e-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc98e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc98e-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="fc98e-115">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="fc98e-115">Panels Overview</span></span>](panels-overview.md)
