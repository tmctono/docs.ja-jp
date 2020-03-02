---
title: デザイナーを使用して DataGridView コントロールの既定のセルスタイルとデータ形式を設定する
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: ca602fa15e4648550bfa171a9c3abd057e930eca
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731357"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="2a13e-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの既定のセル スタイルとデータ形式を設定する</span><span class="sxs-lookup"><span data-stu-id="2a13e-102">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="2a13e-103"><xref:System.Windows.Forms.DataGridView> コントロールを使用すると、コントロール全体、特定の列、行ヘッダー、列ヘッダー、および行と列のヘッダーに対して、既定のセルスタイルとセルデータ形式を指定できます。また、行を交互に使用して、元帳効果を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a13e-103">The <xref:System.Windows.Forms.DataGridView> control lets you specify default cell styles and cell data formats for the entire control, for specific columns, for row and column headers, and for alternating rows to create a ledger effect.</span></span> <span data-ttu-id="2a13e-104">コントロール全体に対して設定されている既定のスタイルは、列および交互の行に対して設定された既定のスタイルによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="2a13e-104">Default styles set for the entire control are overridden by default styles set for columns and alternating rows.</span></span> <span data-ttu-id="2a13e-105">また、個々の行およびセルのコードで設定したスタイルは、既定のスタイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="2a13e-105">Additionally, styles that you set in code for individual rows and cells override the default styles.</span></span>

<span data-ttu-id="2a13e-106">セルスタイルの詳細については、「 [Windows フォーム DataGridView コントロールのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a13e-106">For more information about cell styles, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="2a13e-107">交互の行のスタイルを設定するには、「[方法:デザイナー](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)を使用して、Windows フォーム DataGridView コントロールに交互の行のスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-107">To set styles for alternating rows, see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>

<span data-ttu-id="2a13e-108">また、<xref:System.Windows.Forms.DataGridView.RowTemplate%2A> プロパティを使用してスタイルを設定し、コントロールに追加されるすべての行に影響を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="2a13e-108">You can also set styles using the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property to affect all rows that will be added to the control.</span></span> <span data-ttu-id="2a13e-109">行テンプレートの詳細については、「[方法:行テンプレートを使用して、Windows フォーム DataGridView コントロール](use-the-row-template-to-customize-rows-in-the-datagrid.md)の行をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="2a13e-109">For more information about the row template, see [How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control](use-the-row-template-to-customize-rows-in-the-datagrid.md).</span></span>

<span data-ttu-id="2a13e-110">次の手順では、<xref:System.Windows.Forms.DataGridView> コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="2a13e-110">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2a13e-111">このようなプロジェクトの設定の詳細については、「[方法:Windows フォームアプリケーションプロジェクトを作成し、次の操作方法を ](/visualstudio/ide/step-1-create-a-windows-forms-application-project) [ます。Windows フォーム](how-to-add-controls-to-windows-forms.md)にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a><span data-ttu-id="2a13e-112">コントロール内のすべてのセルに既定のスタイルを設定するには</span><span class="sxs-lookup"><span data-stu-id="2a13e-112">To set default styles for all cells in the control</span></span>

1. <span data-ttu-id="2a13e-113">デザイナーで <xref:System.Windows.Forms.DataGridView> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-113">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="2a13e-114">**[プロパティ]** ウィンドウで、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>、または <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> プロパティの横にある省略記号ボタン ([.. プロパティウィンドウ.]) をクリックし、[、、または] プロパティの横にある [...] を![します](./media/visual-studio-ellipsis-button.png)。</span><span class="sxs-lookup"><span data-stu-id="2a13e-114">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property.</span></span> <span data-ttu-id="2a13e-115">**[CellStyle ビルダー]** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a13e-115">The **CellStyle Builder** dialog box appears.</span></span>

3. <span data-ttu-id="2a13e-116">**プレビュー**ウィンドウを使用して選択内容を確認し、プロパティを設定してスタイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-116">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

> [!NOTE]
> <span data-ttu-id="2a13e-117">視覚スタイルが有効になっている場合、行と列のヘッダー (<xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>を除く) は、現在のテーマによって自動的にスタイル設定され、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> と <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> のプロパティ値をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2a13e-117">If visual styles are enabled, the row and column headers (except for the <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) are automatically styled by the current theme, overriding the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property values.</span></span>
>
> <span data-ttu-id="2a13e-118">デザイナーを使用して、選択した複数の <xref:System.Windows.Forms.DataGridView> コントロールのセルスタイルを設定できますが、変更するセルスタイルプロパティに同じ値が設定されている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="2a13e-118">You can set cell styles for multiple selected <xref:System.Windows.Forms.DataGridView> controls using the designer, but only if they have identical values for the cell style property you want to modify.</span></span> <span data-ttu-id="2a13e-119">そのプロパティのセルスタイルが異なる場合、 **[CellStyle ビルダー]** ダイアログボックスの **[プロパティ]** ウィンドウは空白になります。</span><span class="sxs-lookup"><span data-stu-id="2a13e-119">If any cell styles differ for that property, the **Properties** windows of the **CellStyle Builder** dialog box will be blank.</span></span>

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a><span data-ttu-id="2a13e-120">個々の列のセルに既定のスタイルを設定するには</span><span class="sxs-lookup"><span data-stu-id="2a13e-120">To set default styles for cells in individual columns</span></span>

1. <span data-ttu-id="2a13e-121">デザイナーで <xref:System.Windows.Forms.DataGridView> コントロールを右クリックし、 **[列の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-121">Right-click the <xref:System.Windows.Forms.DataGridView> control in the designer and choose **Edit Columns**.</span></span>

2. <span data-ttu-id="2a13e-122">**[選択された列]** ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-122">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="2a13e-123">**[列のプロパティ]** グリッドで、<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> プロパティの横にある省略記号ボタン ([...]) をクリックします (![Visual Studio のプロパティウィンドウの [...] ](./media/visual-studio-ellipsis-button.png)を)。</span><span class="sxs-lookup"><span data-stu-id="2a13e-123">In the **Column Properties** grid, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="2a13e-124">**[CellStyle ビルダー]** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a13e-124">The **CellStyle Builder** dialog box appears.</span></span>

4. <span data-ttu-id="2a13e-125">**プレビュー**ウィンドウを使用して選択内容を確認し、プロパティを設定してスタイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-125">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

### <a name="to-format-data-in-cells"></a><span data-ttu-id="2a13e-126">セルのデータの書式を設定するには</span><span class="sxs-lookup"><span data-stu-id="2a13e-126">To format data in cells</span></span>

1. <span data-ttu-id="2a13e-127">前の手順のいずれかを使用して、既定のセルスタイルプロパティに関連する **[CellStyle ビルダー]** ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-127">Use one of the preceding procedures to display a **CellStyle Builder** dialog box related to a default cell style property.</span></span>

2. <span data-ttu-id="2a13e-128">**[CellStyle ビルダー]** ダイアログボックスで、<xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> プロパティの横にある省略記号ボタン (![参照ボタン ([...]) をクリックします (Visual Studio のプロパティウィンドウの](./media/visual-studio-ellipsis-button.png))。</span><span class="sxs-lookup"><span data-stu-id="2a13e-128">In the **CellStyle Builder** dialog box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property.</span></span> <span data-ttu-id="2a13e-129">**[書式文字列]** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a13e-129">The **Format String** dialog box appears.</span></span>

3. <span data-ttu-id="2a13e-130">書式の種類を選択してから、 **[サンプル]** ボックスを使用して選択内容を確認し、種類の詳細 (表示する小数点以下の桁数など) を変更します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-130">Select a format type, then modify the details of the type (such as the number of decimal places to display), using the **Sample** box to confirm your choices.</span></span>

4. <span data-ttu-id="2a13e-131">Null 値が含まれる可能性のあるデータソースに <xref:System.Windows.Forms.DataGridView> コントロールをバインドする場合は、 **[Null 値]** ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="2a13e-131">If you are binding the <xref:System.Windows.Forms.DataGridView> control to a data source that is likely to contain null values, fill in the **Null Value** text box.</span></span> <span data-ttu-id="2a13e-132">この値は、セルの値が null 参照 (Visual Basic では`Nothing`) または <xref:System.DBNull.Value?displayProperty=nameWithType>の場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a13e-132">This value is displayed when the cell value is equal to a null reference (`Nothing` in Visual Basic) or <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a13e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a13e-133">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2a13e-134">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="2a13e-134">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2a13e-135">方法: デザイナーを使用して、Windows フォーム DataGridView コントロールに交互の行のスタイルを設定し</span><span class="sxs-lookup"><span data-stu-id="2a13e-135">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="2a13e-136">方法: Windows フォーム アプリケーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="2a13e-136">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- <span data-ttu-id="2a13e-137">[方法: Windows フォーム](how-to-add-controls-to-windows-forms.md) にコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="2a13e-137">[How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md)</span></span>
