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
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923416"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="fc815-102">方法: グリッドを使用して標準 UI ダイアログ ボックスをビルドする</span><span class="sxs-lookup"><span data-stu-id="fc815-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="fc815-103">この例では、 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.Controls.Grid>要素を使用して標準のダイアログボックスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fc815-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc815-104">例</span><span class="sxs-lookup"><span data-stu-id="fc815-104">Example</span></span>  
 <span data-ttu-id="fc815-105">次の例では、Windows オペレーティングシステムの **[実行]** ダイアログボックスなどのダイアログボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc815-105">The following example creates a dialog box like the **Run** dialog box in the Windows operating system.</span></span>  
  
 <span data-ttu-id="fc815-106">この例では<xref:System.Windows.Controls.Grid> 、を作成<xref:System.Windows.Controls.ColumnDefinition>し<xref:System.Windows.Controls.RowDefinition> 、クラスとクラスを使用して、5つの列と4つの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="fc815-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="fc815-107">次に、この例では<xref:System.Windows.Controls.Image>、 `RunIcon.png`ダイアログボックスに表示されるイメージを表す、、を追加して配置します。</span><span class="sxs-lookup"><span data-stu-id="fc815-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="fc815-108">イメージは、 <xref:System.Windows.Controls.Grid>の最初の列と行 (左上隅) に配置されます。</span><span class="sxs-lookup"><span data-stu-id="fc815-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="fc815-109">次に、最初の行<xref:System.Windows.Controls.TextBlock>の残りの列にまたがる要素を最初の列に追加します。</span><span class="sxs-lookup"><span data-stu-id="fc815-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="fc815-110">最初の列<xref:System.Windows.Controls.TextBlock>の2行目に、**開い**ているテキストボックスを表す別の要素が追加されます。</span><span class="sxs-lookup"><span data-stu-id="fc815-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="fc815-111">データ入力領域を表すを次に示します。<xref:System.Windows.Controls.TextBlock></span><span class="sxs-lookup"><span data-stu-id="fc815-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="fc815-112">最後に、最後の行<xref:System.Windows.Controls.Button>に3つの要素を追加します。これは**OK**、 **Cancel**、および**Browse**イベントを表します。</span><span class="sxs-lookup"><span data-stu-id="fc815-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fc815-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc815-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="fc815-114">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="fc815-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="fc815-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="fc815-115">How-to Topics</span></span>](grid-how-to-topics.md)
