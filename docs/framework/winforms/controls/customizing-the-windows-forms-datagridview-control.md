---
title: Windows フォーム DataGridView コントロールのカスタマイズ
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: ab8d1f07c608aca4f14f5e73860f8c3e263a4610
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011424"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="6b2ee-102">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6b2ee-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6b2ee-103">`DataGridView`コントロールのセル、行、列の基本的な動作 (ルック アンド フィール) と外観を調整するために使用できるいくつかのプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="6b2ee-104">機能を上回る特別なニーズがあるかどうか、<xref:System.Windows.Forms.DataGridViewCellStyle>クラス、ただしも所有者コントロールの描画を実装したり、カスタムのセル、列、および行を作成してその機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="6b2ee-105">描画するセルと行自分で、さまざまな処理できる`DataGridView`描画イベント。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="6b2ee-106">既存から派生した独自の型を作成するには、既存の機能を変更したり、新しい機能を提供、 `DataGridViewCell`、 `DataGridViewColumn`、および`DataGridViewRow`型。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="6b2ee-107">独自のセルが編集モードのときのコントロールを表示する派生型を作成、新しい編集機能を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b2ee-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6b2ee-108">In This Section</span></span>  
 [<span data-ttu-id="6b2ee-109">方法: Windows フォームの DataGridView コントロール内のセルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="6b2ee-110">処理する方法について説明します、<xref:System.Windows.Forms.DataGridView.CellPainting>セルを手動で描画するためにイベント。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="6b2ee-111">方法: Windows フォームの DataGridView コントロール内の行の外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="6b2ee-112">処理する方法について説明します、<xref:System.Windows.Forms.DataGridView.RowPrePaint>と<xref:System.Windows.Forms.DataGridView.RowPostPaint>にまたがる複数の列のカスタムのグラデーションの背景を持つ行を描画してコンテンツをするためにイベント。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="6b2ee-113">方法: それぞれの動作と外観を拡張することによって、セルと、Windows フォーム DataGridView コントロール内の列をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="6b2ee-114">派生したカスタムの型を作成する方法について説明します`DataGridViewCell`と`DataGridViewColumn`にマウス ポインターを合わせると、セルを強調表示するためにします。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="6b2ee-115">方法: Windows フォーム DataGridView コントロールのボタン列のボタンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="6b2ee-116">派生したカスタムの型を作成する方法について説明します<xref:System.Windows.Forms.DataGridViewButtonCell>と<xref:System.Windows.Forms.DataGridViewButtonColumn>ボタン列に無効になっているボタンを表示するためにします。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="6b2ee-117">方法: Windows フォーム DataGridView Cells でコントロールをホスト</span><span class="sxs-lookup"><span data-stu-id="6b2ee-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="6b2ee-118">実装する方法について説明します、`IDataGridViewEditingControl`インターフェイスし、から派生したカスタムの型を作成`DataGridViewCell`と`DataGridViewColumn`表示するために、<xref:System.Windows.Forms.DateTimePicker>セルが編集モードのときを制御します。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6b2ee-119">参照</span><span class="sxs-lookup"><span data-stu-id="6b2ee-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="6b2ee-120"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="6b2ee-121">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridViewCell>クラス。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="6b2ee-122">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridViewRow>クラス。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="6b2ee-123">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridViewColumn>クラス。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="6b2ee-124">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.IDataGridViewEditingControl>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6b2ee-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b2ee-125">Related Sections</span></span>  
 [<span data-ttu-id="6b2ee-126">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="6b2ee-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6b2ee-127">コントロールの基本の外観およびセル データの書式設定を変更する方法を説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="6b2ee-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b2ee-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b2ee-128">See also</span></span>

- [<span data-ttu-id="6b2ee-129">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="6b2ee-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="6b2ee-130">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="6b2ee-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
