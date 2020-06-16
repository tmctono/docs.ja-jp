---
title: '方法: StackPanel にコンテンツを水平方向または垂直方向に配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: 03348aa0eb5b6c1791c27683c1c6c6a5d4a8a9d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771034"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="efb0d-102">方法: StackPanel にコンテンツを水平方向または垂直方向に配置する</span><span class="sxs-lookup"><span data-stu-id="efb0d-102">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="efb0d-103">この例では、<xref:System.Windows.Controls.StackPanel> 要素内のコンテンツの <xref:System.Windows.Controls.StackPanel.Orientation%2A> を調整する方法、および子コンテンツの <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> と <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> を調整する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="efb0d-103">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efb0d-104">例</span><span class="sxs-lookup"><span data-stu-id="efb0d-104">Example</span></span>  
 <span data-ttu-id="efb0d-105">次の例では、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] で 3 つの <xref:System.Windows.Controls.ListBox> 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="efb0d-105">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="efb0d-106">各 <xref:System.Windows.Controls.ListBox> は、<xref:System.Windows.Controls.StackPanel> の <xref:System.Windows.Controls.StackPanel.Orientation%2A>、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A> プロパティの使用可能な値を表します。</span><span class="sxs-lookup"><span data-stu-id="efb0d-106">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="efb0d-107">ユーザーが <xref:System.Windows.Controls.ListBox> 要素のいずれかの値を選択すると、<xref:System.Windows.Controls.StackPanel> の関連付けられたプロパティとその子要素の <xref:System.Windows.Controls.Button> が変更されます。</span><span class="sxs-lookup"><span data-stu-id="efb0d-107">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="efb0d-108">次の分離コード ファイルによって、<xref:System.Windows.Controls.ListBox> 選択の変更に関連付けられているイベントへの変更が定義されます。</span><span class="sxs-lookup"><span data-stu-id="efb0d-108">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="efb0d-109"><xref:System.Windows.Controls.StackPanel> は <xref:System.Windows.FrameworkElement.Name%2A> `sp1` によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="efb0d-109"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="efb0d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="efb0d-110">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [<span data-ttu-id="efb0d-111">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="efb0d-111">Panels Overview</span></span>](panels-overview.md)
