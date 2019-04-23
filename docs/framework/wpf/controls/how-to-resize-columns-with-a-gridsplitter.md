---
title: '方法: GridSplitter を使用して列のサイズを変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: f743e9ccf8a984a646a4b8f05ee99162e5bc73ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210439"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a><span data-ttu-id="dc545-102">方法: GridSplitter を使用して列のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="dc545-102">How to: Resize Columns with a GridSplitter</span></span>
<span data-ttu-id="dc545-103">この例は、垂直線を作成する方法を示します<xref:System.Windows.Controls.GridSplitter>で 2 つの列間のスペースを再配布するために、<xref:System.Windows.Controls.Grid>の大きさを変更することがなく、<xref:System.Windows.Controls.Grid>します。</span><span class="sxs-lookup"><span data-stu-id="dc545-103">This example shows how to create a vertical <xref:System.Windows.Controls.GridSplitter> in order to redistribute the space between two columns in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc545-104">例</span><span class="sxs-lookup"><span data-stu-id="dc545-104">Example</span></span>  
 <span data-ttu-id="dc545-105">**列の端に重なって表示される GridSplitter を作成する方法**</span><span class="sxs-lookup"><span data-stu-id="dc545-105">**How to create a GridSplitter that overlays the edge of a column**</span></span>  
  
 <span data-ttu-id="dc545-106">指定する、<xref:System.Windows.Controls.GridSplitter>で隣接する列のサイズを変更する、<xref:System.Windows.Controls.Grid>設定、<xref:System.Windows.Controls.Grid.Column%2A>添付プロパティのサイズを変更する列の 1 つをします。</span><span class="sxs-lookup"><span data-stu-id="dc545-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent columns in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="dc545-107">場合、<xref:System.Windows.Controls.Grid>が 1 つ以上の行では、設定、<xref:System.Windows.Controls.Grid.RowSpan%2A>添付プロパティを行の数。</span><span class="sxs-lookup"><span data-stu-id="dc545-107">If your <xref:System.Windows.Controls.Grid> has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="dc545-108">設定し、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティを<xref:System.Windows.HorizontalAlignment.Left>または<xref:System.Windows.HorizontalAlignment.Right>(どちらの配置を設定する依存する 2 つの列のサイズを変更する)。</span><span class="sxs-lookup"><span data-stu-id="dc545-108">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Left> or <xref:System.Windows.HorizontalAlignment.Right> (which alignment you set depends on which two columns you want to resize).</span></span> <span data-ttu-id="dc545-109">最後に、設定、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>プロパティを<xref:System.Windows.VerticalAlignment.Stretch>します。</span><span class="sxs-lookup"><span data-stu-id="dc545-109">Finally, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <span data-ttu-id="dc545-110">A<xref:System.Windows.Controls.GridSplitter>独自の列を持たない他のコントロールに隠される可能性があります、<xref:System.Windows.Controls.Grid>します。</span><span class="sxs-lookup"><span data-stu-id="dc545-110">A <xref:System.Windows.Controls.GridSplitter> that does not have its own column may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="dc545-111">この問題の詳しい回避方法については、[GridSplitter を表示されるようにする](how-to-make-sure-that-a-gridsplitter-is-visible.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc545-111">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="dc545-112">**列を占有する GridSplitter を作成する方法**</span><span class="sxs-lookup"><span data-stu-id="dc545-112">**How to create a GridSplitter that occupies a column**</span></span>  
  
 <span data-ttu-id="dc545-113">指定する、<xref:System.Windows.Controls.GridSplitter>で列を占有する、 <xref:System.Windows.Controls.Grid>、設定、<xref:System.Windows.Controls.Grid.Column%2A>添付プロパティのサイズを変更する列の 1 つをします。</span><span class="sxs-lookup"><span data-stu-id="dc545-113">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a column in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="dc545-114">グリッドには、複数の行がある場合は、設定、<xref:System.Windows.Controls.Grid.RowSpan%2A>添付プロパティを行の数。</span><span class="sxs-lookup"><span data-stu-id="dc545-114">If your Grid has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="dc545-115">設定し、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>に<xref:System.Windows.HorizontalAlignment.Center>、設定、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>プロパティを<xref:System.Windows.VerticalAlignment.Stretch>、設定と、<xref:System.Windows.Controls.ColumnDefinition.Width%2A>を含む列の<xref:System.Windows.Controls.GridSplitter>に<xref:System.Windows.GridLength.Auto%2A>。</span><span class="sxs-lookup"><span data-stu-id="dc545-115">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> to <xref:System.Windows.HorizontalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>, and set the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the column that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="dc545-116">次の例は、垂直方向を定義する方法を示します<xref:System.Windows.Controls.GridSplitter>列を占有してのいずれかの側の列のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="dc545-116">The following example shows how to define a vertical <xref:System.Windows.Controls.GridSplitter> that occupies a column and resizes the columns on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="dc545-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc545-117">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="dc545-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="dc545-118">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
