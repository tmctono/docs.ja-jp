---
title: '方法: TreeView のパフォーマンスを改善する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: de1b46da2a7c6c3db0c0c19cdbb654fcf2fbbd6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771008"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="28def-102">方法: TreeView のパフォーマンスを改善する</span><span class="sxs-lookup"><span data-stu-id="28def-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="28def-103"><xref:System.Windows.Controls.TreeView> に含まれる項目が多い場合、ユーザー インターフェイスで読み込みにかかる時間が大幅に遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28def-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="28def-104">`VirtualizingStackPanel.IsVirtualizing` 添付プロパティを `true` に設定して、読み込み時間を改善することができます。</span><span class="sxs-lookup"><span data-stu-id="28def-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="28def-105">また、ユーザーがマウス ホイールを使用したり、スクロール バーのつまみをドラッグしたりして、ユーザーが <xref:System.Windows.Controls.TreeView> をスクロールするときの UI の反応も遅くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="28def-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="28def-106">`VirtualizingStackPanel.VirtualizationMode` 添付プロパティを <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> に設定することで、ユーザーがスクロールしたときの <xref:System.Windows.Controls.TreeView> のパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="28def-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28def-107">例</span><span class="sxs-lookup"><span data-stu-id="28def-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="28def-108">説明</span><span class="sxs-lookup"><span data-stu-id="28def-108">Description</span></span>  
<span data-ttu-id="28def-109">次の例では、`VirtualizingStackPanel.IsVirtualizing` 添付プロパティを true に設定し、`VirtualizingStackPanel.VirtualizationMode` 添付プロパティを <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> に設定して <xref:System.Windows.Controls.TreeView> を作成し、そのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="28def-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="28def-110">コード</span><span class="sxs-lookup"><span data-stu-id="28def-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="28def-111">次の例は、前の例で使用するデータを示しています。</span><span class="sxs-lookup"><span data-stu-id="28def-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="28def-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="28def-112">See also</span></span>

- [<span data-ttu-id="28def-113">コントロール</span><span class="sxs-lookup"><span data-stu-id="28def-113">Controls</span></span>](../advanced/optimizing-performance-controls.md)
