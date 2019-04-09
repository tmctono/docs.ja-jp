---
title: Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 4c755d5f0c2e134b83beb27ebbd06080bad620b6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115233"
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="957d2-102">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="957d2-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="957d2-103">多くの基本的な動作の`DataGridView`セル、行、および列を 1 つのプロパティを設定して変更できます。</span><span class="sxs-lookup"><span data-stu-id="957d2-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="957d2-104">このセクションのトピックでは、最もよく使用されるこれらの機能のいくつかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="957d2-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="957d2-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="957d2-105">In This Section</span></span>  
 [<span data-ttu-id="957d2-106">方法: Windows フォームの DataGridView コントロールの列を非表示にする</span><span class="sxs-lookup"><span data-stu-id="957d2-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="957d2-107">特定の列がコントロールに表示されないようにする方法をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="957d2-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="957d2-108">方法: Windows フォーム DataGridView コントロールの列ヘッダーを非表示にする</span><span class="sxs-lookup"><span data-stu-id="957d2-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="957d2-109">列ヘッダーが、コントロールに表示されないようにする方法をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="957d2-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="957d2-110">方法: Windows フォーム DataGridView コントロールの列の並べ替えを有効にする</span><span class="sxs-lookup"><span data-stu-id="957d2-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="957d2-111">ユーザーがコントロール内の列を再配置を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="957d2-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="957d2-112">方法: Windows フォーム DataGridView コントロールの列を固定する</span><span class="sxs-lookup"><span data-stu-id="957d2-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="957d2-113">説明 1 つ以上の隣接する列をスクロールしないようにする方法。</span><span class="sxs-lookup"><span data-stu-id="957d2-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="957d2-114">方法: Windows フォームの DataGridView コントロールで列を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="957d2-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="957d2-115">ユーザーがコントロール内の特定の列を編集できないようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="957d2-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="957d2-116">方法: Windows フォーム DataGridView コントロールで行が追加および削除されないようにする</span><span class="sxs-lookup"><span data-stu-id="957d2-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="957d2-117">新しいレコードをユーザーが行を追加するを防ぐために、コントロールの下部にある行を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="957d2-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="957d2-118">ユーザーが行を削除することを防止する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="957d2-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="957d2-119">方法: Windows フォーム DataGridView コントロールの現在のセルを取得および設定する</span><span class="sxs-lookup"><span data-stu-id="957d2-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="957d2-120">現在コントロールにフォーカスがあるセルにアクセスする方法をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="957d2-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="957d2-121">方法: Windows フォーム DataGridView コントロールのセルにイメージを表示する</span><span class="sxs-lookup"><span data-stu-id="957d2-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="957d2-122">すべてのセルにアイコンを表示するイメージ列を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="957d2-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="957d2-123">参照</span><span class="sxs-lookup"><span data-stu-id="957d2-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="957d2-124">コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="957d2-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="957d2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="957d2-125">Related Sections</span></span>  
 [<span data-ttu-id="957d2-126">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="957d2-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="957d2-127">コントロールの基本の外観およびセル データの書式設定を変更する方法を説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="957d2-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="957d2-128">Windows フォーム DataGridView コントロールのセル、行、および列を使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="957d2-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="957d2-129">セル、行、および列オブジェクトを使用したプログラミング方法を説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="957d2-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957d2-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="957d2-130">See also</span></span>

- [<span data-ttu-id="957d2-131">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="957d2-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="957d2-132">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="957d2-132">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
