---
title: '方法: デザイナーを使用して Windows フォーム DataGridView コントロールの既定のセル スタイルとデータ形式を設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 54ed74c7738b6b7eb2844dfb1e2c865dbed7208e
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959444"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="f0a00-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの既定のセル スタイルとデータ形式を設定する</span><span class="sxs-lookup"><span data-stu-id="f0a00-102">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="f0a00-103"><xref:System.Windows.Forms.DataGridView>コントロールを使用する既定のセル スタイルを指定し、コントロール全体の特定の列、行および列のヘッダーおおよび台帳効果を作成する行を交互のデータ形式します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-103">The <xref:System.Windows.Forms.DataGridView> control lets you specify default cell styles and cell data formats for the entire control, for specific columns, for row and column headers, and for alternating rows to create a ledger effect.</span></span> <span data-ttu-id="f0a00-104">既定のスタイルのコントロール全体の設定は、既定の列と交互の行のスタイル設定によって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f0a00-104">Default styles set for the entire control are overridden by default styles set for columns and alternating rows.</span></span> <span data-ttu-id="f0a00-105">さらに、個々 の行とセルのコードに設定するスタイルは、既定のスタイルをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f0a00-105">Additionally, styles that you set in code for individual rows and cells override the default styles.</span></span>

<span data-ttu-id="f0a00-106">セルのスタイルの詳細については、次を参照してください。 [Windows フォームの DataGridView コントロールのセル スタイル](cell-styles-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-106">For more information about cell styles, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="f0a00-107">交互の行のスタイルを設定するを参照してください。[方法。Windows フォーム DataGridView コントロールのデザイナーを使用しての交互の行のスタイル設定](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-107">To set styles for alternating rows, see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>

<span data-ttu-id="f0a00-108">使用してスタイルを設定することも、<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>プロパティをコントロールに追加されるすべての行に影響します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-108">You can also set styles using the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property to affect all rows that will be added to the control.</span></span> <span data-ttu-id="f0a00-109">行のテンプレートの詳細については、次を参照してください。[方法。行テンプレートを使用して Windows フォームの DataGridView コントロール内の行をカスタマイズする](use-the-row-template-to-customize-rows-in-the-datagrid.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-109">For more information about the row template, see [How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control](use-the-row-template-to-customize-rows-in-the-datagrid.md).</span></span>

<span data-ttu-id="f0a00-110">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="f0a00-110">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f0a00-111">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f0a00-112">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f0a00-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f0a00-113">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0a00-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f0a00-114">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0a00-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a><span data-ttu-id="f0a00-115">コントロール内のすべてのセルの既定のスタイルを設定するには</span><span class="sxs-lookup"><span data-stu-id="f0a00-115">To set default styles for all cells in the control</span></span>

1. <span data-ttu-id="f0a00-116">選択、<xref:System.Windows.Forms.DataGridView>デザイナーでコントロールできます。</span><span class="sxs-lookup"><span data-stu-id="f0a00-116">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="f0a00-117">**プロパティ**ウィンドウで、省略記号ボタンをクリックします (![. Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png)) 横に、 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>、 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>、または<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f0a00-117">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property.</span></span> <span data-ttu-id="f0a00-118">**[CellStyle ビルダー** ] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a00-118">The **CellStyle Builder** dialog box appears.</span></span>

3. <span data-ttu-id="f0a00-119">使用して、プロパティを設定してスタイルを定義、**プレビュー**ウィンドウで選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-119">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a00-120">Visual スタイルが有効な場合行および列ヘッダー (を除き、 <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) は、現在のテーマによって自動的にスタイルが設定をオーバーライドする、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>と<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="f0a00-120">If visual styles are enabled, the row and column headers (except for the <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) are automatically styled by the current theme, overriding the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property values.</span></span>
>
> <span data-ttu-id="f0a00-121">選択された複数のセル スタイルを設定する<xref:System.Windows.Forms.DataGridView>セル スタイル プロパティを変更するのと同じ値がある場合にのみ、デザイナーの使用を制御します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-121">You can set cell styles for multiple selected <xref:System.Windows.Forms.DataGridView> controls using the designer, but only if they have identical values for the cell style property you want to modify.</span></span> <span data-ttu-id="f0a00-122">そのプロパティの任意のセルのスタイルが異なる場合、**プロパティ**の windows、 **[CellStyle ビルダー** ] ダイアログ ボックスは空白になります。</span><span class="sxs-lookup"><span data-stu-id="f0a00-122">If any cell styles differ for that property, the **Properties** windows of the **CellStyle Builder** dialog box will be blank.</span></span>

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a><span data-ttu-id="f0a00-123">個々 の列のセルの既定のスタイルを設定するには</span><span class="sxs-lookup"><span data-stu-id="f0a00-123">To set default styles for cells in individual columns</span></span>

1. <span data-ttu-id="f0a00-124">右クリックし、<xref:System.Windows.Forms.DataGridView>デザイナーで制御および選択**列の編集**します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-124">Right-click the <xref:System.Windows.Forms.DataGridView> control in the designer and choose **Edit Columns**.</span></span>

2. <span data-ttu-id="f0a00-125">列を選択、**選択した列**一覧。</span><span class="sxs-lookup"><span data-stu-id="f0a00-125">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="f0a00-126">**列プロパティ**グリッドで、省略記号ボタンをクリックします (![. Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png)) 横に、<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f0a00-126">In the **Column Properties** grid, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="f0a00-127">**[CellStyle ビルダー** ] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a00-127">The **CellStyle Builder** dialog box appears.</span></span>

4. <span data-ttu-id="f0a00-128">使用して、プロパティを設定してスタイルを定義、**プレビュー**ウィンドウで選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-128">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

### <a name="to-format-data-in-cells"></a><span data-ttu-id="f0a00-129">データ セルを書式設定するには</span><span class="sxs-lookup"><span data-stu-id="f0a00-129">To format data in cells</span></span>

1. <span data-ttu-id="f0a00-130">表示する前の手順のいずれかを使用して、 **[CellStyle ビルダー** ] ダイアログ ボックスに関連する既定のセル スタイル プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f0a00-130">Use one of the preceding procedures to display a **CellStyle Builder** dialog box related to a default cell style property.</span></span>

2. <span data-ttu-id="f0a00-131">**[CellStyle ビルダー** ] ダイアログ ボックスで、省略記号ボタンをクリックします (![. Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png)) 横に、<xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f0a00-131">In the **CellStyle Builder** dialog box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property.</span></span> <span data-ttu-id="f0a00-132">**書式指定文字列** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0a00-132">The **Format String** dialog box appears.</span></span>

3. <span data-ttu-id="f0a00-133">形式の種類を選択し、表示する小数点以下桁数の数) などの型の詳細の変更を使用して、**サンプル**ボックス選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-133">Select a format type, then modify the details of the type (such as the number of decimal places to display), using the **Sample** box to confirm your choices.</span></span>

4. <span data-ttu-id="f0a00-134">バインドしている場合、 <xref:System.Windows.Forms.DataGridView> null 値を含む、入力する可能性があるデータ ソースにコントロール、 **Null 値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="f0a00-134">If you are binding the <xref:System.Windows.Forms.DataGridView> control to a data source that is likely to contain null values, fill in the **Null Value** text box.</span></span> <span data-ttu-id="f0a00-135">セルの値が null 参照に等しい場合に、この値が表示されます (`Nothing` Visual basic) または<xref:System.DBNull.Value?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-135">This value is displayed when the cell value is equal to a null reference (`Nothing` in Visual Basic) or <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0a00-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0a00-136">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f0a00-137">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="f0a00-137">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f0a00-138">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの交互の行のスタイル設定します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-138">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="f0a00-139">方法: Windows フォーム アプリケーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="f0a00-139">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="f0a00-140">方法: Windows フォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="f0a00-140">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
