---
title: '方法: グリッドを使用して標準 UI ダイアログ ボックスをビルドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 0ade908e92e552017acb9ba242ccba2c28c3c995
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051053"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="5d440-102">方法: グリッドを使用して標準 UI ダイアログ ボックスをビルドする</span><span class="sxs-lookup"><span data-stu-id="5d440-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="5d440-103">この例は、標準を作成する方法を示します[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] ダイアログ ボックスを使用して、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="5d440-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d440-104">例</span><span class="sxs-lookup"><span data-stu-id="5d440-104">Example</span></span>  
 <span data-ttu-id="5d440-105">次の例のようなダイアログ ボックスの作成、**実行** ダイアログ ボックスで、[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]オペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="5d440-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="5d440-106">例は、作成、<xref:System.Windows.Controls.Grid>を使用して、<xref:System.Windows.Controls.ColumnDefinition>と<xref:System.Windows.Controls.RowDefinition>5 つの列と 4 つの行を定義するクラス。</span><span class="sxs-lookup"><span data-stu-id="5d440-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="5d440-107">例は、追加し、配置、 <xref:System.Windows.Controls.Image>、 `RunIcon.png`、ダイアログ ボックスにある画像を表します。</span><span class="sxs-lookup"><span data-stu-id="5d440-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="5d440-108">最初の列との行で、イメージが格納される、 <xref:System.Windows.Controls.Grid> (左上隅)。</span><span class="sxs-lookup"><span data-stu-id="5d440-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="5d440-109">次に、例、<xref:System.Windows.Controls.TextBlock>最初の列は、最初の行の残りの列にまたがる要素。</span><span class="sxs-lookup"><span data-stu-id="5d440-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="5d440-110">追加別<xref:System.Windows.Controls.TextBlock>要素を表す、最初の列の 2 つ目の行に、**オープン**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="5d440-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="5d440-111">A<xref:System.Windows.Controls.TextBlock>フォローで、データ エントリの領域を表します。</span><span class="sxs-lookup"><span data-stu-id="5d440-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="5d440-112">最後に、3 つ追加例では、<xref:System.Windows.Controls.Button>を表す要素の最後の行を**OK**、**キャンセル**、および**参照**イベント。</span><span class="sxs-lookup"><span data-stu-id="5d440-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5d440-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d440-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="5d440-114">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="5d440-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="5d440-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="5d440-115">How-to Topics</span></span>](grid-how-to-topics.md)
