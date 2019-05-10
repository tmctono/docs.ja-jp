---
title: '方法: Windows フォーム DataGridView コントロールの各セルにツールヒントを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: d0e9b3ad742633b135a2fe1c00af3fa72af7b44a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663454"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="4ccd8-102">方法: Windows フォーム DataGridView コントロールの各セルにツールヒントを追加する</span><span class="sxs-lookup"><span data-stu-id="4ccd8-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4ccd8-103">既定では、ツールヒントを使用しての値を表示する<xref:System.Windows.Forms.DataGridView>は小さすぎて全体の内容を表示するセル。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="4ccd8-104">ただし、この動作をオーバーライドする個々 のセルのツールヒントのテキスト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="4ccd8-105">これは、セルに関する追加情報をユーザーに表示する、または他のセルの内容の説明をユーザーに提供するには便利です。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="4ccd8-106">たとえば、状態アイコンを表示する行がある場合は、場合、ツールヒントを使用した説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="4ccd8-107">セル レベルのツールヒントの表示を無効にすることもできます、<xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="4ccd8-108">セルにツールヒントを追加するには</span><span class="sxs-lookup"><span data-stu-id="4ccd8-108">To add a ToolTip to a cell</span></span>  
  
- <span data-ttu-id="4ccd8-109">
  <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4ccd8-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4ccd8-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="4ccd8-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-111">This example requires:</span></span>  
  
- <span data-ttu-id="4ccd8-112">A<xref:System.Windows.Forms.DataGridView>という名前のコントロール`dataGridView1`という名前の列を格納している`Rating`4 つのアスタリスクを 1 つの文字列値を表示する ("\*") 記号です。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="4ccd8-113"><xref:System.Windows.Forms.DataGridView.CellFormatting>例に示すようにイベント ハンドラー メソッドを使用して、コントロールのイベントを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
- <span data-ttu-id="4ccd8-114"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4ccd8-115">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="4ccd8-115">Robust Programming</span></span>  
 <span data-ttu-id="4ccd8-116">バインドすると、<xref:System.Windows.Forms.DataGridView>外部データ ソースへの制御または仮想モードを実装して、独自のデータ ソースを提供する、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="4ccd8-117">パフォーマンスの低下を避けるためには、大量のデータを使用する場合、処理、<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>設定ではなく、イベント、<xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>複数のセルのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="4ccd8-118">処理するとき、このイベントはセルの値を取得する<xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>プロパティは、イベントを発生させるしの値を返します、<xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType>プロパティとして指定されたイベントのハンドラー。</span><span class="sxs-lookup"><span data-stu-id="4ccd8-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ccd8-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ccd8-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4ccd8-120">Windows フォーム DataGridView コントロールのセル、行、および列を使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="4ccd8-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
