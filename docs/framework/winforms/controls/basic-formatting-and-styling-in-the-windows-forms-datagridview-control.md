---
title: DataGridView コントロールの基本的な書式設定とスタイル設定
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731996"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="316c4-102">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="316c4-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="316c4-103">`DataGridView` コントロールを使用すると、セルの基本的な外観と、セル値の表示形式を簡単に定義できます。</span><span class="sxs-lookup"><span data-stu-id="316c4-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="316c4-104">さまざまな `DataGridView` コントロールのプロパティを使用してアクセスする `DataGridViewCellStyle` オブジェクトのプロパティを設定することによって、個々のセル、特定の列や行のセル、またはコントロール内のすべてのセルの外観と書式設定スタイルを定義できます。</span><span class="sxs-lookup"><span data-stu-id="316c4-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="316c4-105">また、`CellFormatting` イベントを処理することによって、セルの値などの要因に基づいて、これらのスタイルを動的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="316c4-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="316c4-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="316c4-106">In This Section</span></span>  
 [<span data-ttu-id="316c4-107">方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する</span><span class="sxs-lookup"><span data-stu-id="316c4-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="316c4-108">コントロールの境界線とセル間の境界線の外観を定義する `DataGridView` プロパティを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="316c4-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="316c4-109">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="316c4-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="316c4-110">`DataGridViewCellStyle` クラスと、その型のプロパティがコントロールでのセルの表示方法を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="316c4-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="316c4-111">方法: Windows フォーム DataGridView コントロールの既定のセル スタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="316c4-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="316c4-112">`DataGridViewCellStyle` のプロパティを使用して、特定の行と列、およびコントロール全体のセルの既定の外観を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="316c4-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="316c4-113">方法: Windows フォーム DataGridView コントロールのデータの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="316c4-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="316c4-114">`DataGridViewCellStyle` のプロパティを使用して、セルの表示値の書式を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="316c4-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="316c4-115">方法: Windows フォーム DataGridView コントロールのフォントと色のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="316c4-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="316c4-116">`DefaultCellStyle` プロパティを使用して、コントロールのすべてのセルの基本的な表示特性を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="316c4-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="316c4-117">方法: Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="316c4-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="316c4-118">別の行で表示される行を交互に使用して、コントロールに元帳に似た効果を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="316c4-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="316c4-119">方法: 行テンプレートを使用して Windows フォーム DataGridView コントロールの行をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="316c4-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="316c4-120">`RowTemplate` プロパティを使用して、コントロールのすべての行に使用される行のプロパティを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="316c4-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="316c4-121">参照先</span><span class="sxs-lookup"><span data-stu-id="316c4-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="316c4-122"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="316c4-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="316c4-123"><xref:System.Windows.Forms.DataGridViewCellStyle> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="316c4-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="316c4-124"><xref:System.Windows.Forms.DataGridView.CellFormatting> イベントのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="316c4-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="316c4-125"><xref:System.Windows.Forms.DataGridView.RowTemplate%2A> プロパティのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="316c4-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="316c4-126">関連セクション</span><span class="sxs-lookup"><span data-stu-id="316c4-126">Related Sections</span></span>  
 [<span data-ttu-id="316c4-127">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="316c4-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="316c4-128"><xref:System.Windows.Forms.DataGridView> のセルおよび行のカスタム描画と、セル、列、および行の派生型の作成について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="316c4-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="316c4-129">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="316c4-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="316c4-130">一般的に使用されるセル、行、および列のプロパティについて説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="316c4-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="316c4-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="316c4-131">See also</span></span>

- [<span data-ttu-id="316c4-132">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="316c4-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
