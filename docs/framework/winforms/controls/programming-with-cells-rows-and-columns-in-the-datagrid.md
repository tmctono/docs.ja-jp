---
title: DataGridView コントロールのセル、行、および列を使用したプログラミング
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], elements
- columns [Windows Forms], data grids
- cells [Windows Forms], data grids
- DataGridView control [Windows Forms], programming with grid elements
- rows [Windows Forms], data grids
ms.assetid: 0d76f7e4-4149-42c6-9118-bb37d6669dc5
ms.openlocfilehash: e2d5927ecff734b359b860701e094480bbf3188f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741346"
---
# <a name="programming-with-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e4570-102">Windows フォーム DataGridView コントロールのセル、行、および列を使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="e4570-102">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e4570-103">ここでは、セル、行、および列オブジェクトに関連するさまざまなプログラミングタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e4570-103">This section provides topics that demonstrate various programming tasks involving cell, row, and column objects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4570-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e4570-104">In This Section</span></span>  
 [<span data-ttu-id="e4570-105">方法: Windows フォーム DataGridView コントロールの各セルにツールヒントを追加する</span><span class="sxs-lookup"><span data-stu-id="e4570-105">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>](add-tooltips-to-individual-cells-in-a-wf-datagridview-control.md)  
 <span data-ttu-id="e4570-106"><xref:System.Windows.Forms.DataGridView.CellFormatting> イベントを処理して、セルごとに異なるツールヒントを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4570-106">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting> event to provide different ToolTips for individual cells.</span></span>  
  
 [<span data-ttu-id="e4570-107">方法: Windows フォーム DataGridView コントロールのセルの変更に基づいてカスタム動作を実行する</span><span class="sxs-lookup"><span data-stu-id="e4570-107">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>](perform-a-custom-action-based-on-changes-in-a-cell-of-a-datagrid.md)  
 <span data-ttu-id="e4570-108"><xref:System.Windows.Forms.DataGridView.CellValueChanged> イベントと <xref:System.Windows.Forms.DataGridView.CellStateChanged> イベントの処理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4570-108">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
 [<span data-ttu-id="e4570-109">方法: Windows フォームの DataGridView コントロールのバンドを操作する</span><span class="sxs-lookup"><span data-stu-id="e4570-109">How to: Manipulate Bands in the Windows Forms DataGridView Control</span></span>](how-to-manipulate-bands-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e4570-110">行と列の基本型である <xref:System.Windows.Forms.DataGridViewBand>型のオブジェクトを使用してプログラミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4570-110">Describes how to program with objects of type <xref:System.Windows.Forms.DataGridViewBand>, which is the base type for rows and columns.</span></span>  
  
 [<span data-ttu-id="e4570-111">方法: Windows フォームの DataGridView コントロールの行を操作する</span><span class="sxs-lookup"><span data-stu-id="e4570-111">How to: Manipulate Rows in the Windows Forms DataGridView Control</span></span>](how-to-manipulate-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e4570-112">`DataGridViewRow`型のオブジェクトを使用してプログラミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4570-112">Describes how to program with objects of type `DataGridViewRow`.</span></span>  
  
 [<span data-ttu-id="e4570-113">方法: Windows フォーム DataGridView コントロールの列を操作する</span><span class="sxs-lookup"><span data-stu-id="e4570-113">How to: Manipulate Columns in the Windows Forms DataGridView Control</span></span>](how-to-manipulate-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e4570-114">`DataGridViewColumn`型のオブジェクトを使用してプログラミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4570-114">Describes how to program with objects of type `DataGridViewColumn`.</span></span>  
  
 [<span data-ttu-id="e4570-115">方法: Windows フォーム DataGridView コントロールのイメージ列を操作する</span><span class="sxs-lookup"><span data-stu-id="e4570-115">How to: Work with Image Columns in the Windows Forms DataGridView Control</span></span>](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e4570-116">`DataGridViewImageColumn` クラスを使用してプログラミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4570-116">Describes how to program with the `DataGridViewImageColumn` class.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e4570-117">リファレンス</span><span class="sxs-lookup"><span data-stu-id="e4570-117">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="e4570-118"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="e4570-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="e4570-119"><xref:System.Windows.Forms.DataGridViewCell> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="e4570-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="e4570-120"><xref:System.Windows.Forms.DataGridViewRow> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="e4570-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="e4570-121"><xref:System.Windows.Forms.DataGridViewColumn> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="e4570-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e4570-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4570-122">Related Sections</span></span>  
 [<span data-ttu-id="e4570-123">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="e4570-123">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="e4570-124">一般的に使用されるセル、行、および列のプロパティについて説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="e4570-124">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4570-125">参照</span><span class="sxs-lookup"><span data-stu-id="e4570-125">See also</span></span>

- [<span data-ttu-id="e4570-126">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="e4570-126">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="e4570-127">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="e4570-127">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
