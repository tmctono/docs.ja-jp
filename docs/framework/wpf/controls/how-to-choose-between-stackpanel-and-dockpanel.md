---
title: '方法: StackPanel または DockPanel を選択する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
ms.openlocfilehash: 8338421dfb1bea856c15edf9d324cec955584f9f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206968"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="b2f89-102">方法: StackPanel または DockPanel を選択する</span><span class="sxs-lookup"><span data-stu-id="b2f89-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="b2f89-103">この例では、使用するか、<xref:System.Windows.Controls.StackPanel>または<xref:System.Windows.Controls.DockPanel>でコンテンツをスタックする、<xref:System.Windows.Controls.Panel>します。</span><span class="sxs-lookup"><span data-stu-id="b2f89-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2f89-104">例</span><span class="sxs-lookup"><span data-stu-id="b2f89-104">Example</span></span>  
 <span data-ttu-id="b2f89-105">いずれかを使用できますが、<xref:System.Windows.Controls.DockPanel>または<xref:System.Windows.Controls.StackPanel>を子要素をスタックには、2 つのコントロールは、常に結果を生成しない、同じです。</span><span class="sxs-lookup"><span data-stu-id="b2f89-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="b2f89-106">たとえば、子要素を配置する順序は内の子要素のサイズに影響を<xref:System.Windows.Controls.DockPanel>ではなく、<xref:System.Windows.Controls.StackPanel>します。</span><span class="sxs-lookup"><span data-stu-id="b2f89-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="b2f89-107">このさまざまな問題の原因<xref:System.Windows.Controls.StackPanel>で積み重ねの方向にメジャー <xref:System.Double>.<xref:System.Double.PositiveInfinity>。 ただし、<xref:System.Windows.Controls.DockPanel>のみ使用可能なサイズを測定します。</span><span class="sxs-lookup"><span data-stu-id="b2f89-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at <xref:System.Double>.<xref:System.Double.PositiveInfinity>; however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>  
  
 <span data-ttu-id="b2f89-108">次の例では、この主な違い<xref:System.Windows.Controls.DockPanel>と<xref:System.Windows.Controls.StackPanel>します。</span><span class="sxs-lookup"><span data-stu-id="b2f89-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b2f89-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2f89-109">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="b2f89-110">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="b2f89-110">Panels Overview</span></span>](panels-overview.md)
