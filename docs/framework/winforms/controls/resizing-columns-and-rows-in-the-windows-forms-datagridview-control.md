---
title: Windows フォーム DataGridView コントロール内の列と行のサイズ変更
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8eae5dafa314bb293f55a780f6be67d06f376004
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709655"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="bba8c-102">Windows フォーム DataGridView コントロール内の列と行のサイズ変更</span><span class="sxs-lookup"><span data-stu-id="bba8c-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="bba8c-103">`DataGridView`コントロールには、その列と行のサイズ変更動作をカスタマイズするためのさまざまなオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bba8c-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="bba8c-104">通常、`DataGridView`セル サイズを変更しないでその内容を基にします。</span><span class="sxs-lookup"><span data-stu-id="bba8c-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="bba8c-105">代わりに、セルよりも大きい任意の表示値のクリップです。</span><span class="sxs-lookup"><span data-stu-id="bba8c-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="bba8c-106">コンテンツを文字列として表示でき、セルにより、ツールヒントに表示します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="bba8c-107">既定では、ユーザーは、行、列、および詳細情報を表示するには、マウスでのヘッダー区分線をドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="bba8c-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="bba8c-108">ユーザーは、自動的にその内容に基づいて関連付けられている行、列、またはヘッダーのバンドのサイズを変更する区分線をダブルクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bba8c-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="bba8c-109">`DataGridView`プロパティ、メソッド、およびイベントをカスタマイズまたはすべてのユーザー向けのこれらの動作を無効にするためのコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="bba8c-110">さらに、行、列、およびヘッダーをその内容に合わせてサイズ変更できるプログラムでまたは自体の内容が変更されるたびにで自動的にサイズ変更するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="bba8c-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="bba8c-111">指定した比率で、コントロールの使用可能な幅を自動的に分割する列を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bba8c-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bba8c-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bba8c-112">In This Section</span></span>  
 [<span data-ttu-id="bba8c-113">Windows フォーム DataGridView コントロールのサイズ変更オプション</span><span class="sxs-lookup"><span data-stu-id="bba8c-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="bba8c-114">サイズ設定行、列、およびヘッダーのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="bba8c-115">サイズ変更に関連するプロパティとメソッドの詳細を説明し、一般的な使用シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="bba8c-116">Windows フォーム DataGridView コントロールの列フィル モード</span><span class="sxs-lookup"><span data-stu-id="bba8c-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="bba8c-117">列フィル モードとその他のモードを実験に使用できるデモ コードと列フィル モードの詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="bba8c-118">方法: Windows フォーム DataGridView コントロールのサイズ変更モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="bba8c-119">一般的な目的のサイズ変更モードを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="bba8c-120">方法: プログラムで Windows フォームの DataGridView コントロールのコンテンツに合わせてセルのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="bba8c-121">プログラムによるサイズ変更を実験に使用できるデモ コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="bba8c-122">方法: Windows フォームの DataGridView コントロールのコンテンツが変更されたときに、セルを自動的にサイズ変更します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="bba8c-123">自動サイズ変更モードを実験に使用できるデモ コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bba8c-124">参照</span><span class="sxs-lookup"><span data-stu-id="bba8c-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="bba8c-125">
  <xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="bba8c-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bba8c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="bba8c-126">See also</span></span>
- [<span data-ttu-id="bba8c-127">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="bba8c-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
