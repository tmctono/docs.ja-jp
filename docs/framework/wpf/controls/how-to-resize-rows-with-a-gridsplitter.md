---
title: '方法: GridSplitter を使用して行のサイズを変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 6760a7a691af4f666294556cae3bc95a4299730a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074275"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a><span data-ttu-id="076a2-102">方法: GridSplitter を使用して行のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="076a2-102">How to: Resize Rows with a GridSplitter</span></span>
<span data-ttu-id="076a2-103">この例は、水平方向を使用する方法を示します<xref:System.Windows.Controls.GridSplitter>の 2 つの行の間のスペースを再配分を<xref:System.Windows.Controls.Grid>の寸法を変更せず、<xref:System.Windows.Controls.Grid>します。</span><span class="sxs-lookup"><span data-stu-id="076a2-103">This example shows how to use a horizontal <xref:System.Windows.Controls.GridSplitter> to redistribute the space between two rows in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="076a2-104">例</span><span class="sxs-lookup"><span data-stu-id="076a2-104">Example</span></span>  
 **<span data-ttu-id="076a2-105">GridSplitter を作成する方法、行の端</span><span class="sxs-lookup"><span data-stu-id="076a2-105">How to create a GridSplitter that overlays the edge of a row</span></span>**  
  
 <span data-ttu-id="076a2-106">指定する、<xref:System.Windows.Controls.GridSplitter>で隣接する行のサイズを変更する、<xref:System.Windows.Controls.Grid>設定、<xref:System.Windows.Controls.Grid.Row%2A>添付プロパティのサイズを変更する行の 1 つをします。</span><span class="sxs-lookup"><span data-stu-id="076a2-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="076a2-107">場合、<xref:System.Windows.Controls.Grid>が 1 つ以上の列は、設定、<xref:System.Windows.Controls.Grid.ColumnSpan%2A>添付プロパティを列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="076a2-107">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to specify the number of columns.</span></span> <span data-ttu-id="076a2-108">設定し、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>に<xref:System.Windows.VerticalAlignment.Top>または<xref:System.Windows.VerticalAlignment.Bottom>(どちらの配置を設定する依存する 2 つの行のサイズを変更する)。</span><span class="sxs-lookup"><span data-stu-id="076a2-108">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Top> or <xref:System.Windows.VerticalAlignment.Bottom> (which alignment you set depends on which two rows you want to resize).</span></span> <span data-ttu-id="076a2-109">最後に、設定、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティを<xref:System.Windows.HorizontalAlignment.Stretch>します。</span><span class="sxs-lookup"><span data-stu-id="076a2-109">Finally, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>.</span></span>  
  
 <span data-ttu-id="076a2-110">次の例は、水平方向を定義する方法を示します<xref:System.Windows.Controls.GridSplitter>隣接する行のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="076a2-110">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <span data-ttu-id="076a2-111">A<xref:System.Windows.Controls.GridSplitter>独自の行を占有しない他のコントロールに隠される可能性があります、<xref:System.Windows.Controls.Grid>します。</span><span class="sxs-lookup"><span data-stu-id="076a2-111">A <xref:System.Windows.Controls.GridSplitter> that does not occupy its own row may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="076a2-112">この問題の詳しい回避方法については、[GridSplitter を表示されるようにする](how-to-make-sure-that-a-gridsplitter-is-visible.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="076a2-112">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 **<span data-ttu-id="076a2-113">行を占有する GridSplitter を作成する方法</span><span class="sxs-lookup"><span data-stu-id="076a2-113">How to create a GridSplitter that occupies a row</span></span>**  
  
 <span data-ttu-id="076a2-114">指定する、<xref:System.Windows.Controls.GridSplitter>内の行を占有する、 <xref:System.Windows.Controls.Grid>、設定、<xref:System.Windows.Controls.Grid.Row%2A>添付プロパティのサイズを変更する行の 1 つをします。</span><span class="sxs-lookup"><span data-stu-id="076a2-114">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a row in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="076a2-115">場合、<xref:System.Windows.Controls.Grid>が 1 つ以上の列は、設定、<xref:System.Windows.Controls.Grid.ColumnSpan%2A>添付プロパティを列の数。</span><span class="sxs-lookup"><span data-stu-id="076a2-115">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to the number of columns.</span></span> <span data-ttu-id="076a2-116">設定し、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>に<xref:System.Windows.VerticalAlignment.Center>、設定、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティを<xref:System.Windows.HorizontalAlignment.Stretch>、設定と、<xref:System.Windows.Controls.RowDefinition.Height%2A>を含む行の<xref:System.Windows.Controls.GridSplitter>に<xref:System.Windows.GridLength.Auto%2A>。</span><span class="sxs-lookup"><span data-stu-id="076a2-116">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>, and set the <xref:System.Windows.Controls.RowDefinition.Height%2A> of the row that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="076a2-117">次の例は、水平方向を定義する方法を示します<xref:System.Windows.Controls.GridSplitter>を行を占有しのどちら側に行のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="076a2-117">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that occupies a row and resizes the rows on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="076a2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="076a2-118">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="076a2-119">方法のトピック</span><span class="sxs-lookup"><span data-stu-id="076a2-119">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
