---
title: DataGridView コントロールでの列と行のサイズ変更
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8f8394a837ccc11c469f9ad4feeb60464d0014fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742411"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="afc12-102">Windows フォーム DataGridView コントロール内の列と行のサイズ変更</span><span class="sxs-lookup"><span data-stu-id="afc12-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="afc12-103">`DataGridView` コントロールには、列と行のサイズ変更動作をカスタマイズするためのさまざまなオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="afc12-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="afc12-104">通常、`DataGridView` のセルは、その内容に基づいてサイズが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="afc12-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="afc12-105">代わりに、セルよりも大きい表示値をクリップします。</span><span class="sxs-lookup"><span data-stu-id="afc12-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="afc12-106">コンテンツを文字列として表示できる場合、セルはツールヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="afc12-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="afc12-107">既定では、ユーザーは、行、列、およびヘッダーの区切り線をマウスでドラッグして、より多くの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="afc12-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="afc12-108">ユーザーは、区分線をダブルクリックして、関連付けられている行、列、またはヘッダーのバンドのサイズをその内容に基づいて自動的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="afc12-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="afc12-109">`DataGridView` コントロールには、これらのすべてのユーザー向け動作をカスタマイズまたは無効にするためのプロパティ、メソッド、およびイベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="afc12-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="afc12-110">また、行、列、ヘッダーの内容に合わせてプログラムによってサイズを変更することもできます。また、コンテンツが変更されるたびに自動的にサイズが変更されるように構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="afc12-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="afc12-111">また、使用可能なコントロールの幅を指定した比率で自動的に分割するように列を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="afc12-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="afc12-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="afc12-112">In This Section</span></span>  
 [<span data-ttu-id="afc12-113">Windows フォーム DataGridView コントロールのサイズ変更オプション</span><span class="sxs-lookup"><span data-stu-id="afc12-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="afc12-114">行、列、およびヘッダーのサイズを変更するためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="afc12-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="afc12-115">また、サイズに関連するプロパティとメソッドの詳細について説明し、一般的な使用シナリオについても説明します。</span><span class="sxs-lookup"><span data-stu-id="afc12-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="afc12-116">Windows フォーム DataGridView コントロールの列フィル モード</span><span class="sxs-lookup"><span data-stu-id="afc12-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="afc12-117">列の塗りつぶしモードの詳細について説明し、列の塗りつぶしモードとその他のモードを試すために使用できるデモコードを示します。</span><span class="sxs-lookup"><span data-stu-id="afc12-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="afc12-118">方法: Windows フォーム DataGridView コントロールのサイズ変更モードを設定する</span><span class="sxs-lookup"><span data-stu-id="afc12-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="afc12-119">一般的な目的でサイズ変更モードを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="afc12-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="afc12-120">方法: Windows フォームの DataGridView コントロールの内容に合わせてセルのサイズをプログラムで変更する</span><span class="sxs-lookup"><span data-stu-id="afc12-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="afc12-121">プログラムによるサイズ変更のテストに使用できるデモコードを示します。</span><span class="sxs-lookup"><span data-stu-id="afc12-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="afc12-122">方法: Windows フォームの DataGridView コントロールの内容変更時にセルのサイズを自動的に変更する</span><span class="sxs-lookup"><span data-stu-id="afc12-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="afc12-123">自動サイズ調整モードを試すために使用できるデモコードを示します。</span><span class="sxs-lookup"><span data-stu-id="afc12-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="afc12-124">リファレンス</span><span class="sxs-lookup"><span data-stu-id="afc12-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="afc12-125"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="afc12-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc12-126">参照</span><span class="sxs-lookup"><span data-stu-id="afc12-126">See also</span></span>

- [<span data-ttu-id="afc12-127">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="afc12-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
