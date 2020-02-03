---
title: DataGridView コントロールでの選択とクリップボードの使用
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 6993f77e8ce532d8df1bdc7e6b6abc1cc3268e49
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743068"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="2ea0d-102">Windows フォーム DataGridView コントロールでの選択およびクリップボードの使用</span><span class="sxs-lookup"><span data-stu-id="2ea0d-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2ea0d-103">`DataGridView` コントロールには、ユーザーがセル、行、および列を選択する方法を構成するためのさまざまなオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="2ea0d-104">たとえば、ユーザーがセルをクリックしたときに、1つまたは複数の選択を有効にしたり、行または列全体を選択したりすることができます。ユーザーがヘッダーをクリックすると、セルの選択も可能になります。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="2ea0d-105">選択に独自のユーザーインターフェイスを提供する場合は、通常の選択を無効にして、すべての選択をプログラムで処理することができます。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="2ea0d-106">また、ユーザーが選択した値をクリップボードにコピーできるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ea0d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2ea0d-107">In This Section</span></span>  
 [<span data-ttu-id="2ea0d-108">Windows フォーム DataGridView コントロールの選択モード</span><span class="sxs-lookup"><span data-stu-id="2ea0d-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2ea0d-109">コントロールでユーザーとプログラムを選択するためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="2ea0d-110">方法: Windows フォーム DataGridView コントロールの選択モードを設定する</span><span class="sxs-lookup"><span data-stu-id="2ea0d-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2ea0d-111">ユーザーがセルをクリックしたときに、単一行の選択のためにコントロールを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="2ea0d-112">方法: Windows フォーム DataGridView コントロールの選択されたセル、行、および列を取得する</span><span class="sxs-lookup"><span data-stu-id="2ea0d-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="2ea0d-113">選択したセル、行、および列のコレクションを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="2ea0d-114">方法: ユーザーが、Windows フォーム DataGridView コントロールからクリップボードに複数のセルをコピーできるようにする</span><span class="sxs-lookup"><span data-stu-id="2ea0d-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="2ea0d-115">コントロールでクリップボードのサポートを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2ea0d-116">リファレンス</span><span class="sxs-lookup"><span data-stu-id="2ea0d-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2ea0d-117"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="2ea0d-118"><xref:System.Windows.Forms.DataGridView.SelectionMode%2A> プロパティのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="2ea0d-119"><xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> プロパティのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="2ea0d-120"><xref:System.Windows.Forms.DataGridViewSelectedCellCollection> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="2ea0d-121"><xref:System.Windows.Forms.DataGridViewSelectedRowCollection> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="2ea0d-122"><xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> クラスのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ea0d-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea0d-123">参照</span><span class="sxs-lookup"><span data-stu-id="2ea0d-123">See also</span></span>

- [<span data-ttu-id="2ea0d-124">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="2ea0d-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="2ea0d-125">Windows フォーム DataGridView コントロールの既定のキーボード処理とマウス処理</span><span class="sxs-lookup"><span data-stu-id="2ea0d-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
