---
title: DataGridView コントロールのカスタマイズ
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744028"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="1d657-102">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="1d657-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1d657-103">`DataGridView` コントロールには、セル、行、および列の外観と基本動作 (ルックアンドフィール) を調整するために使用できるいくつかのプロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1d657-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="1d657-104">ただし、<xref:System.Windows.Forms.DataGridViewCellStyle> クラスの機能を超える特別なニーズがある場合は、コントロールのオーナー描画を実装したり、カスタムセル、列、および行を作成してその機能を拡張したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1d657-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="1d657-105">セルと行を自分で描画するには、さまざまな `DataGridView` の描画イベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="1d657-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="1d657-106">既存の機能を変更したり、新しい機能を提供したりするには、既存の `DataGridViewCell`、`DataGridViewColumn`、および `DataGridViewRow` 型から派生した独自の型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1d657-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="1d657-107">また、セルが編集モードのときに選択したコントロールを表示する派生型を作成することによって、新しい編集機能を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="1d657-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d657-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1d657-108">In This Section</span></span>  
 [<span data-ttu-id="1d657-109">方法 : Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1d657-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="1d657-110">セルを手動で描画するために <xref:System.Windows.Forms.DataGridView.CellPainting> イベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d657-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="1d657-111">方法: Windows フォームの DataGridView コントロールの行の外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1d657-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="1d657-112">カスタム、グラデーションの背景、および複数の列にまたがるコンテンツを使用して行を描画するために、<xref:System.Windows.Forms.DataGridView.RowPrePaint> イベントと <xref:System.Windows.Forms.DataGridView.RowPostPaint> イベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d657-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="1d657-113">方法: Windows フォーム DataGridView コントロールのセルと列を、それぞれの動作と外観を拡張してカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1d657-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="1d657-114">マウスポインターがセル上にあるときにセルを強調表示するために `DataGridViewCell` および `DataGridViewColumn` から派生したカスタム型を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d657-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="1d657-115">方法: Windows フォーム DataGridView コントロールのボタン列にあるボタンを無効にする</span><span class="sxs-lookup"><span data-stu-id="1d657-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="1d657-116">ボタン列に無効なボタンを表示するために <xref:System.Windows.Forms.DataGridViewButtonCell> および <xref:System.Windows.Forms.DataGridViewButtonColumn> から派生したカスタム型を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d657-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="1d657-117">方法: Windows フォーム DataGridView Cells でコントロールをホストする</span><span class="sxs-lookup"><span data-stu-id="1d657-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="1d657-118">セルが編集モードのときに <xref:System.Windows.Forms.DateTimePicker> コントロールを表示するために、`IDataGridViewEditingControl` インターフェイスを実装し、`DataGridViewCell` および `DataGridViewColumn` から派生したカスタム型を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d657-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1d657-119">リファレンス</span><span class="sxs-lookup"><span data-stu-id="1d657-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="1d657-120"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d657-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="1d657-121"><xref:System.Windows.Forms.DataGridViewCell> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d657-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="1d657-122"><xref:System.Windows.Forms.DataGridViewRow> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d657-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="1d657-123"><xref:System.Windows.Forms.DataGridViewColumn> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d657-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="1d657-124"><xref:System.Windows.Forms.IDataGridViewEditingControl> インターフェイスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d657-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1d657-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d657-125">Related Sections</span></span>  
 [<span data-ttu-id="1d657-126">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="1d657-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1d657-127">コントロールの基本の外観およびセル データの書式設定を変更する方法を説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="1d657-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d657-128">参照</span><span class="sxs-lookup"><span data-stu-id="1d657-128">See also</span></span>

- [<span data-ttu-id="1d657-129">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="1d657-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="1d657-130">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="1d657-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
