---
title: DataGridView コントロールの既定の機能
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746133"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e5b95-102">Windows フォーム DataGridView コントロールの既定の機能</span><span class="sxs-lookup"><span data-stu-id="e5b95-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e5b95-103">Windows フォーム <xref:System.Windows.Forms.DataGridView> コントロールにより、ユーザーは大量の既定機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="e5b95-104">既定の機能</span><span class="sxs-lookup"><span data-stu-id="e5b95-104">Default Functionality</span></span>  
 <span data-ttu-id="e5b95-105">既定では、<xref:System.Windows.Forms.DataGridView> コントロールです。</span><span class="sxs-lookup"><span data-stu-id="e5b95-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <span data-ttu-id="e5b95-106">テーブルを垂直方向にスクロールしても列ヘッダーおよび行ヘッダーが見える状態のまま自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="e5b95-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
- <span data-ttu-id="e5b95-107">現在の行を示す選択を含む行ヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="e5b95-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
- <span data-ttu-id="e5b95-108">最初のセルに選択を示す四角形があります。</span><span class="sxs-lookup"><span data-stu-id="e5b95-108">Has a selection rectangle in the first cell.</span></span>  
  
- <span data-ttu-id="e5b95-109">ユーザーが列の区切り線をダブルクリックすると、自動的にサイズを変更できる列があります。</span><span class="sxs-lookup"><span data-stu-id="e5b95-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
- <span data-ttu-id="e5b95-110">では、アプリケーションの `Main` メソッドから <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> メソッドが呼び出されたときに、Windows XP と Windows Server 2003 ファミリの visual スタイルが自動的にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="e5b95-111">また、既定では、<xref:System.Windows.Forms.DataGridView> コントロールの内容を編集できます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
- <span data-ttu-id="e5b95-112">ユーザーがダブルクリックするか、セル中で F2 キーを押した場合、コントロールは自動的にセルを編集モードにし、ユーザーが入力したセルの内容を更新します。</span><span class="sxs-lookup"><span data-stu-id="e5b95-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
- <span data-ttu-id="e5b95-113">ユーザーがグリッドの最後までスクロールすると、新しいレコードを追加するための行が存在することがわかります。</span><span class="sxs-lookup"><span data-stu-id="e5b95-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="e5b95-114">ユーザーがこの行をクリックすると、<xref:System.Windows.Forms.DataGridView> コントロールに新しい行が追加され、既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="e5b95-115">ユーザーが ESC キーを押すと、この新しい行は消えます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-115">When the user presses ESC, this new row disappears.</span></span>  
  
- <span data-ttu-id="e5b95-116">ユーザーが行ヘッダーをクリックすると、行全体が選択されます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="e5b95-117"><xref:System.Windows.Forms.DataGridView.DataSource%2A> プロパティを設定して、<xref:System.Windows.Forms.DataGridView> コントロールをデータソースにバインドする場合、コントロールは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e5b95-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
- <span data-ttu-id="e5b95-118">では、データソースの列の名前が列ヘッダーのテキストとして自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
- <span data-ttu-id="e5b95-119">には、データソースの内容が設定されます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="e5b95-120"><xref:System.Windows.Forms.DataGridView> 列は、データソースの各列に対して自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
- <span data-ttu-id="e5b95-121">テーブル内の表示されている各行に対して行を作成します。</span><span class="sxs-lookup"><span data-stu-id="e5b95-121">Creates a row for each visible row in the table.</span></span>  
  
- <span data-ttu-id="e5b95-122">は、ユーザーが列ヘッダーをクリックしたときに、基になるデータに基づいて行を自動的に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="e5b95-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b95-123">参照</span><span class="sxs-lookup"><span data-stu-id="e5b95-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="e5b95-124">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="e5b95-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
