---
title: Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: 5e967c1bbe54095cc11e48b014600158da7fe6a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189895"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="27c3f-102">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="27c3f-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="27c3f-103">`DataGridView`コントロールにより、簡単に基本セルの外観およびセルの値の表示書式を定義できます。</span><span class="sxs-lookup"><span data-stu-id="27c3f-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="27c3f-104">外観を定義して、個々 のセル、特定の列と行のセルまたはコントロール内のすべてのセルのスタイル設定の書式設定のプロパティを設定して、`DataGridViewCellStyle`オブジェクトを通じてさまざまなアクセス`DataGridView`プロパティを制御します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="27c3f-105">さらに、処理することによって、セルの値などの要因に基づいて動的にこれらのスタイルを変更することができます、`CellFormatting`イベント。</span><span class="sxs-lookup"><span data-stu-id="27c3f-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27c3f-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="27c3f-106">In This Section</span></span>  
 [<span data-ttu-id="27c3f-107">方法: 罫線と、Windows フォーム DataGridView コントロールでグリッド線のスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="27c3f-108">設定する方法について説明します`DataGridView`コントロールの境界線とセル間の境界線の外観を定義するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="27c3f-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="27c3f-109">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="27c3f-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27c3f-110">について説明します、`DataGridViewCellStyle`クラスとコントロールのセルを表示する方法を定義する型のプロパティの相互作用します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="27c3f-111">方法: Windows フォームの DataGridView コントロールの既定のセル スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27c3f-112">使用する方法について説明します`DataGridViewCellStyle`特定の行と列では、コントロール全体では、セルの既定の外観を定義するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="27c3f-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="27c3f-113">方法: 書式設定データの Windows フォーム DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="27c3f-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27c3f-114">セルの表示値を使用して書式設定する方法について説明します`DataGridViewCellStyle`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="27c3f-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="27c3f-115">方法: Windows フォームの DataGridView コントロールのフォントと色のスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27c3f-116">使用する方法について説明します、`DefaultCellStyle`基本的な設定するプロパティは、すべてのセルの特性をコントロールに表示します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="27c3f-117">方法: Windows フォームの DataGridView コントロールの交互の行のスタイル設定します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27c3f-118">表示方法が異なる交互の行を使用して、コントロールで帳簿のような効果を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="27c3f-119">方法: 行テンプレートを使用して Windows フォームの DataGridView コントロール内の行をカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="27c3f-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="27c3f-120">使用する方法について説明します、`RowTemplate`コントロールのすべての行に使用される行のプロパティを設定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="27c3f-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="27c3f-121">参照</span><span class="sxs-lookup"><span data-stu-id="27c3f-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="27c3f-122"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="27c3f-123">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridViewCellStyle>クラス。</span><span class="sxs-lookup"><span data-stu-id="27c3f-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="27c3f-124">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.CellFormatting>イベント。</span><span class="sxs-lookup"><span data-stu-id="27c3f-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="27c3f-125">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="27c3f-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="27c3f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="27c3f-126">Related Sections</span></span>  
 [<span data-ttu-id="27c3f-127">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="27c3f-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27c3f-128"><xref:System.Windows.Forms.DataGridView> のセルおよび行のカスタム描画と、セル、列、および行の派生型の作成について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="27c3f-129">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="27c3f-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="27c3f-130">よくを説明するトピックに使用されるセル、行、および列のプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="27c3f-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c3f-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="27c3f-131">See also</span></span>

- [<span data-ttu-id="27c3f-132">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="27c3f-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
