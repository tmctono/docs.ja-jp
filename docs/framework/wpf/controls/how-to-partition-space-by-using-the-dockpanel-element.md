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
ms.openlocfilehash: d22a808ce3ab95e3b351408bf4cc372a335da553
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960198"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="388d3-102">方法: DockPanel 要素を使用して領域を分割する</span><span class="sxs-lookup"><span data-stu-id="388d3-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="388d3-103">次の例では、 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.Controls.DockPanel>要素を使用して単純なフレームワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="388d3-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="388d3-104">は<xref:System.Windows.Controls.DockPanel> 、子要素に使用できる領域をパーティション分割します。</span><span class="sxs-lookup"><span data-stu-id="388d3-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="388d3-105">例</span><span class="sxs-lookup"><span data-stu-id="388d3-105">Example</span></span>  
 <span data-ttu-id="388d3-106">この例では<xref:System.Windows.Controls.DockPanel.Dock%2A> 、添付プロパティであるプロパティを使用して、パーティション<xref:System.Windows.Controls.Border>分割され<xref:System.Windows.Controls.Dock.Top>た領域のに同一の2つの要素をドッキングします。</span><span class="sxs-lookup"><span data-stu-id="388d3-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="388d3-107">3番<xref:System.Windows.Controls.Border>目の要素は<xref:System.Windows.Controls.Dock.Left>にドッキングされ、幅は200ピクセルに設定されます。</span><span class="sxs-lookup"><span data-stu-id="388d3-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="388d3-108">4番<xref:System.Windows.Controls.Border>目のは画面<xref:System.Windows.Controls.Dock.Bottom>のにドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="388d3-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="388d3-109">最後<xref:System.Windows.Controls.Border>の要素は、残りの領域を自動的に入力します。</span><span class="sxs-lookup"><span data-stu-id="388d3-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> <span data-ttu-id="388d3-110">既定では、 <xref:System.Windows.Controls.DockPanel>要素の最後の子が残りの未割り当て領域を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="388d3-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="388d3-111">この動作にしない場合は、`LastChildFill="False"`を設定します。</span><span class="sxs-lookup"><span data-stu-id="388d3-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="388d3-112">コンパイル済みのアプリケーションでは、次のような新しい UI を生成します。</span><span class="sxs-lookup"><span data-stu-id="388d3-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="388d3-113">![代表的な DockPanel シナリオ: ](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="388d3-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388d3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="388d3-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="388d3-115">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="388d3-115">Panels Overview</span></span>](panels-overview.md)
