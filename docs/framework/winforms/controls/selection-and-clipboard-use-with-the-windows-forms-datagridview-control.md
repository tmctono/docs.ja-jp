---
title: Windows フォーム DataGridView コントロールでの選択およびクリップボードの使用
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 61f3eee6f4690e9bd9141f2eeb6de330bac87550
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715374"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="c92dd-102">Windows フォーム DataGridView コントロールでの選択およびクリップボードの使用</span><span class="sxs-lookup"><span data-stu-id="c92dd-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c92dd-103">`DataGridView`コントロールでは、さまざまなユーザーがセル、行、および列を選択する方法を構成するためのオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c92dd-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="c92dd-104">たとえば、有効にできます 1 つまたは複数選択、行全体またはユーザーがセルをクリックすると、列の選択または選択範囲全体の行または列のユーザー ヘッダーをクリックする場合にのみがセルの選択もできます。</span><span class="sxs-lookup"><span data-stu-id="c92dd-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="c92dd-105">選択範囲の独自のユーザー インターフェイスを提供する場合は、通常の選択を無効にし、すべての選択をプログラムで処理できます。</span><span class="sxs-lookup"><span data-stu-id="c92dd-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="c92dd-106">さらに、選択された値をクリップボードにコピーするユーザーを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c92dd-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c92dd-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c92dd-107">In This Section</span></span>  
 [<span data-ttu-id="c92dd-108">Windows フォーム DataGridView コントロールの選択モード</span><span class="sxs-lookup"><span data-stu-id="c92dd-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c92dd-109">ユーザーと、コントロールのプログラムの選択項目のオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c92dd-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="c92dd-110">方法: Windows フォーム DataGridView コントロールの選択モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="c92dd-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c92dd-111">ユーザーがセルをクリックすると、単一行の選択のコントロールを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c92dd-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="c92dd-112">方法: Windows フォーム DataGridView コントロールで選択したセル、行、および列を取得します。</span><span class="sxs-lookup"><span data-stu-id="c92dd-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="c92dd-113">選択したセル、行、および列のコレクションを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c92dd-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="c92dd-114">方法: Windows フォームの DataGridView コントロールから複数のセルをクリップボードにコピーするユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c92dd-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="c92dd-115">コントロールでのクリップボードのサポートを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c92dd-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c92dd-116">参照</span><span class="sxs-lookup"><span data-stu-id="c92dd-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="c92dd-117">
  <xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c92dd-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="c92dd-118">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c92dd-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="c92dd-119">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c92dd-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="c92dd-120">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridViewSelectedCellCollection>クラス。</span><span class="sxs-lookup"><span data-stu-id="c92dd-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="c92dd-121">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridViewSelectedRowCollection>クラス。</span><span class="sxs-lookup"><span data-stu-id="c92dd-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="c92dd-122">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>クラス。</span><span class="sxs-lookup"><span data-stu-id="c92dd-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c92dd-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c92dd-123">See also</span></span>
- [<span data-ttu-id="c92dd-124">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="c92dd-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="c92dd-125">Windows フォーム DataGridView コントロールの既定のキーボード処理とマウス処理</span><span class="sxs-lookup"><span data-stu-id="c92dd-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
