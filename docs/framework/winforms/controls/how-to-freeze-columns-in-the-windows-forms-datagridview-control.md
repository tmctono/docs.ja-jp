---
title: '方法: Windows フォーム DataGridView コントロールの列を固定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: a83c5078d67be40fda2ae3382b8124594ee78103
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966659"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="13874-102">方法: Windows フォーム DataGridView コントロールの列を固定する</span><span class="sxs-lookup"><span data-stu-id="13874-102">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="13874-103">ユーザーが Windows フォームの <xref:System.Windows.Forms.DataGridView> コントロールに表示されるデータを確認するときに、1 つの列または列のセットを頻繁に参照しなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="13874-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="13874-104">たとえば、多数の列を含む顧客情報のテーブルを表示するとき、顧客名を常に表示して、その他の列は表示領域外にスクロールするようにできると便利です。</span><span class="sxs-lookup"><span data-stu-id="13874-104">For example, when displaying a table of customer information that contains many columns, it is useful to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="13874-105">この動作を実現するために、コントロールの列を固定することができます。</span><span class="sxs-lookup"><span data-stu-id="13874-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="13874-106">列を固定すると、左側 (右から左へ記述する言語のスクリプトでは右側) のすべての列も同様に固定されます。</span><span class="sxs-lookup"><span data-stu-id="13874-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="13874-107">固定された列は表示されたままになり、その他のすべての列はスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="13874-107">Frozen columns remain in place while all other columns can scroll.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13874-108">列の並べ替えが有効な場合、固定された列は、固定されていない列とは異なるグループとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="13874-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="13874-109">ユーザーは、どちらかのグループに列を再配置できますが、1 つのグループから別のグループに列を移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="13874-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="13874-110">列の <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> プロパティは、列が常にグリッド内で表示されるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="13874-110">The <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property of a column determines whether the column is always visible within the grid.</span></span>  
  
 <span data-ttu-id="13874-111">Visual Studio では、このタスクに対するサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="13874-111">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="13874-112">「 [方法:デザイナー](freeze-columns-in-the-datagrid-using-the-designer.md)を使用して Windows フォーム DataGridView コントロールの列を固定します。</span><span class="sxs-lookup"><span data-stu-id="13874-112">Also see [How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer](freeze-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-freeze-a-column-programmatically"></a><span data-ttu-id="13874-113">プログラムで列を固定するには</span><span class="sxs-lookup"><span data-stu-id="13874-113">To freeze a column programmatically</span></span>  
  
- <span data-ttu-id="13874-114"><xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="13874-114">Set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13874-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="13874-115">Compiling the Code</span></span>  
 <span data-ttu-id="13874-116">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="13874-116">This example requires:</span></span>  
  
- <span data-ttu-id="13874-117">`AddToCartButton` という名前の列を含む `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="13874-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `AddToCartButton`.</span></span>  
  
- <span data-ttu-id="13874-118"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="13874-118">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13874-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="13874-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="13874-120">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="13874-120">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="13874-121">方法: Windows フォーム DataGridView コントロールで列の並べ替えを有効にする</span><span class="sxs-lookup"><span data-stu-id="13874-121">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
