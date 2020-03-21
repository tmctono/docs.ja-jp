---
title: データ グリッド コントロールの書式設定
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182148"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="91f76-102">方法 : Windows フォーム DataGrid コントロールの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="91f76-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="91f76-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="91f76-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="91f76-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91f76-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="91f76-105">コントロールのさまざまな部分に異なる色を<xref:System.Windows.Forms.DataGrid>適用すると、その中の情報を読みやすく、解釈しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="91f76-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="91f76-106">行と列に色を適用できます。</span><span class="sxs-lookup"><span data-stu-id="91f76-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="91f76-107">行と列は、ユーザーの裁量で非表示にしたり、表示したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="91f76-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="91f76-108">コントロールの書式設定には、3 つの<xref:System.Windows.Forms.DataGrid>基本的な側面があります。</span><span class="sxs-lookup"><span data-stu-id="91f76-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="91f76-109">プロパティを設定して、データが表示される既定のスタイルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="91f76-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="91f76-110">そのベースから、実行時に特定のテーブルを表示する方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="91f76-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="91f76-111">最後に、データ グリッドに表示する列、および表示される色やその他の書式設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="91f76-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="91f76-112">データ グリッドの書式設定の最初の手順として、それ自体のプロパティを<xref:System.Windows.Forms.DataGrid>設定できます。</span><span class="sxs-lookup"><span data-stu-id="91f76-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="91f76-113">これらの色と書式の選択肢は、表示されるデータ テーブルと列に応じて変更を加えることができるベースを形成します。</span><span class="sxs-lookup"><span data-stu-id="91f76-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="91f76-114">コントロールの既定のスタイルを設定するには</span><span class="sxs-lookup"><span data-stu-id="91f76-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="91f76-115">必要に応じて、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="91f76-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="91f76-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="91f76-116">Property</span></span>|<span data-ttu-id="91f76-117">説明</span><span class="sxs-lookup"><span data-stu-id="91f76-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="91f76-118">この<xref:System.Windows.Forms.DataGrid.BackColor%2A>プロパティは、グリッドの偶数行の色を定義します。</span><span class="sxs-lookup"><span data-stu-id="91f76-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="91f76-119">プロパティを<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>異なる色に設定すると、他のすべての行がこの新しい色 (行 1、3、5 など) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="91f76-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="91f76-120">グリッドの偶数行の背景色 (行 0、2、4、6 など)。</span><span class="sxs-lookup"><span data-stu-id="91f76-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="91f76-121">プロパティと<xref:System.Windows.Forms.DataGrid.BackColor%2A><xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>プロパティによってグリッド内の行の色が決まります<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>が、グリッドが下にスクロールされたとき、またはグリッドに含まれている行が数行しかない場合にのみ表示される非行領域の色がプロパティによって決まります。</span><span class="sxs-lookup"><span data-stu-id="91f76-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="91f76-122">グリッドの境界線スタイル (列挙値の<xref:System.Windows.Forms.BorderStyle>1 つ)。</span><span class="sxs-lookup"><span data-stu-id="91f76-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="91f76-123">グリッドのすぐ上に表示される、グリッドのウィンドウ キャプションの背景色。</span><span class="sxs-lookup"><span data-stu-id="91f76-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="91f76-124">グリッドの上部にあるキャプションのフォント。</span><span class="sxs-lookup"><span data-stu-id="91f76-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="91f76-125">グリッドのウィンドウ キャプションの背景色。</span><span class="sxs-lookup"><span data-stu-id="91f76-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="91f76-126">グリッド内のテキストを表示するために使用するフォント。</span><span class="sxs-lookup"><span data-stu-id="91f76-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="91f76-127">データ グリッドの行のデータによって表示されるフォントの色。</span><span class="sxs-lookup"><span data-stu-id="91f76-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="91f76-128">データ グリッドのグリッド線の色。</span><span class="sxs-lookup"><span data-stu-id="91f76-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="91f76-129">グリッドのセルを区切る線のスタイル(<xref:System.Windows.Forms.DataGridLineStyle>列挙値の 1 つ)。</span><span class="sxs-lookup"><span data-stu-id="91f76-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="91f76-130">行ヘッダーと列ヘッダーの背景色。</span><span class="sxs-lookup"><span data-stu-id="91f76-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="91f76-131">列ヘッダーに使用されるフォント。</span><span class="sxs-lookup"><span data-stu-id="91f76-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="91f76-132">列ヘッダーテキストとプラス/マイナスグリフ (複数の関連テーブルが表示されている場合に行を展開する) を含む、グリッドの列ヘッダーの前景色。</span><span class="sxs-lookup"><span data-stu-id="91f76-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="91f76-133">子テーブルへのリンク、リレーション名など、データ グリッド内のすべてのリンクのテキストの色。</span><span class="sxs-lookup"><span data-stu-id="91f76-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="91f76-134">子テーブルでは、親行の背景色です。</span><span class="sxs-lookup"><span data-stu-id="91f76-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="91f76-135">子テーブルでは、親行の前景色です。</span><span class="sxs-lookup"><span data-stu-id="91f76-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="91f76-136">列挙体を使用して、テーブル名と列名を親の行に表示するかどうかを<xref:System.Windows.Forms.DataGridParentRowsLabelStyle>決定します。</span><span class="sxs-lookup"><span data-stu-id="91f76-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="91f76-137">グリッドの列の既定の幅 (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="91f76-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="91f76-138">プロパティを<xref:System.Windows.Forms.DataGrid.DataSource%2A><xref:System.Windows.Forms.DataGrid.DataMember%2A>リセットする前にこのプロパティを設定するか (個別に、<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>またはメソッドを使用して)、プロパティは無効になります。</span><span class="sxs-lookup"><span data-stu-id="91f76-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="91f76-139">このプロパティは 0 未満の値に設定できません。</span><span class="sxs-lookup"><span data-stu-id="91f76-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="91f76-140">グリッド内の行の行の高さ (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="91f76-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="91f76-141">プロパティを<xref:System.Windows.Forms.DataGrid.DataSource%2A><xref:System.Windows.Forms.DataGrid.DataMember%2A>リセットする前にこのプロパティを設定するか (個別に、<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>またはメソッドを使用して)、プロパティは無効になります。</span><span class="sxs-lookup"><span data-stu-id="91f76-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="91f76-142">このプロパティは 0 未満の値に設定できません。</span><span class="sxs-lookup"><span data-stu-id="91f76-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="91f76-143">グリッドの行ヘッダーの幅。</span><span class="sxs-lookup"><span data-stu-id="91f76-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="91f76-144">行またはセルが選択されている場合、背景色になります。</span><span class="sxs-lookup"><span data-stu-id="91f76-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="91f76-145">行またはセルが選択されている場合、これは前景色です。</span><span class="sxs-lookup"><span data-stu-id="91f76-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="91f76-146">コントロールの色をカスタマイズする場合は、色の選択が不十分なため(赤や緑など)、コントロールにアクセスできなくなることを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="91f76-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="91f76-147">この問題を回避するには、[**システム カラー** ] パレットで使用できる色を使用します。</span><span class="sxs-lookup"><span data-stu-id="91f76-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="91f76-148">次の手順では、フォームにデータ<xref:System.Windows.Forms.DataGrid>テーブルにバインドされたコントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="91f76-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="91f76-149">詳細については、「 [Windows フォーム のデータ グリッド コントロールをデータ ソースにバインドする](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91f76-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="91f76-150">データ テーブルのテーブルスタイルと列スタイルをプログラムで設定するには</span><span class="sxs-lookup"><span data-stu-id="91f76-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="91f76-151">新しい表スタイルを作成し、そのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="91f76-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="91f76-152">列スタイルを作成し、そのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="91f76-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="91f76-153">表スタイルの列スタイルコレクションに列スタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="91f76-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="91f76-154">データ グリッドのテーブル スタイル コレクションにテーブル スタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="91f76-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="91f76-155">次の例では、新しい<xref:System.Windows.Forms.DataGridTableStyle>インスタンスを作成し、そのプロパティ<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>を設定します。</span><span class="sxs-lookup"><span data-stu-id="91f76-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="91f76-156">**GridColumnStyle**の新しいインスタンスを作成し、その**マッピング名**(およびその他のレイアウトと表示プロパティ) を設定します。</span><span class="sxs-lookup"><span data-stu-id="91f76-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="91f76-157">作成する列スタイルごとに、手順 2 から 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="91f76-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="91f76-158">次の例は、 の<xref:System.Windows.Forms.DataGridTextBoxColumn>列に名前が表示されるため、a が作成される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="91f76-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="91f76-159">さらに、列スタイルをテーブル スタイルの<xref:System.Windows.Forms.GridColumnStylesCollection>に追加し、データ グリッドの に<xref:System.Windows.Forms.GridTableStylesCollection>テーブル スタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="91f76-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName
       ' to the name of a DataColumn in the DataTable.
       ' Set the HeaderText and Width properties.
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to
       ' the GridTableStylesCollection.
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName
       // to the name of a DataColumn in the DataTable.
       // Set the HeaderText and Width properties.
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to
       // the GridTableStylesCollection.
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName
          // to the name of a DataColumn in the DataTable.
          // Set the HeaderText and Width properties.
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to
          // the GridTableStylesCollection.
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="91f76-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="91f76-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="91f76-161">方法 : Windows フォーム DataGrid コントロールの列を削除するまたは非表示にする</span><span class="sxs-lookup"><span data-stu-id="91f76-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="91f76-162">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="91f76-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
