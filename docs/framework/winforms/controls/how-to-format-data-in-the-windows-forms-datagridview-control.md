---
title: '方法: Windows フォーム DataGridView コントロールのデータの書式を設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: 62701edfdb3cf2729cb401ad12a12ee4f524287b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221301"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fc7ae-102">方法: Windows フォーム DataGridView コントロールのデータの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="fc7ae-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fc7ae-103">次の手順の説明を使用してセル値の基本的な書式設定、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>のプロパティを<xref:System.Windows.Forms.DataGridView>コントロールとコントロールの特定の列。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="fc7ae-104">高度なデータの書式設定方法の詳細については、次を参照してください。[方法。Windows フォーム DataGridView コントロールでデータの書式設定をカスタマイズ](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="fc7ae-105">通貨の書式設定および日付値を</span><span class="sxs-lookup"><span data-stu-id="fc7ae-105">To format currency and date values</span></span>  
  
-   <span data-ttu-id="fc7ae-106"><xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="fc7ae-107">次のコード例を使用して特定の列の形式を設定する、<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>列のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="fc7ae-108">値、`UnitPrice`列が負の値をかっこで囲まれた現在のカルチャに固有の通貨形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="fc7ae-109">値、`ShipDate`列が現在のカルチャに固有の短い日付形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="fc7ae-110">詳細については<xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>値を参照してください[型の書式設定](../../../standard/base-types/formatting-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="fc7ae-111">データベースの null 値の表示をカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="fc7ae-111">To customize the display of null database values</span></span>  
  
-   <span data-ttu-id="fc7ae-112"><xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="fc7ae-113">次のコード例では、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>プロパティと同じ値を格納しているすべてのセルに「エントリ」を表示する<xref:System.DBNull.Value?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="fc7ae-114">セルのテキスト ベースのワード ラップを有効にするには</span><span class="sxs-lookup"><span data-stu-id="fc7ae-114">To enable wordwrap in text-based cells</span></span>  
  
-   <span data-ttu-id="fc7ae-115">設定、<xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>のプロパティを<xref:System.Windows.Forms.DataGridViewCellStyle>のいずれかに、<xref:System.Windows.Forms.DataGridViewTriState>列挙値。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="fc7ae-116">次のコード例では、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>コントロール全体のラップ モードを設定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="fc7ae-117">DataGridView セルのテキストの配置を指定するには</span><span class="sxs-lookup"><span data-stu-id="fc7ae-117">To specify the text alignment of DataGridView cells</span></span>  
  
-   <span data-ttu-id="fc7ae-118">設定、<xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>のプロパティを<xref:System.Windows.Forms.DataGridViewCellStyle>のいずれかに、<xref:System.Windows.Forms.DataGridViewContentAlignment>列挙値。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="fc7ae-119">次のコード例を使用して、特定の列の配置の設定、<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>列のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="fc7ae-120">例</span><span class="sxs-lookup"><span data-stu-id="fc7ae-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fc7ae-121">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="fc7ae-121">Compiling the Code</span></span>  
 <span data-ttu-id="fc7ae-122">これらの例には次の項目が必要です。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-122">These examples require:</span></span>  
  
-   <span data-ttu-id="fc7ae-123">A<xref:System.Windows.Forms.DataGridView>という名前のコントロール`dataGridView1`という名前の列を格納している`UnitPrice`、という名前の列`ShipDate`、という名前の列と`CustomerName`します。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
-   <span data-ttu-id="fc7ae-124"><xref:System?displayProperty=nameWithType>、<xref:System.Drawing?displayProperty=nameWithType>、および <xref:System.Windows.Forms?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fc7ae-125">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="fc7ae-125">Robust Programming</span></span>  
 <span data-ttu-id="fc7ae-126">スケーラビリティを最大にするには、共有する必要があります<xref:System.Windows.Forms.DataGridViewCellStyle>全体で複数の行、列、または個別に各要素のスタイル プロパティを設定するのではなく、同じスタイルを使用するセルのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="fc7ae-127">詳細については、次を参照してください。 [Windows フォーム DataGridView コントロールを拡張するためのベスト プラクティス](best-practices-for-scaling-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc7ae-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc7ae-128">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="fc7ae-129">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="fc7ae-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fc7ae-130">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="fc7ae-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fc7ae-131">Windows フォーム DataGridView コントロールでのデータの書式設定</span><span class="sxs-lookup"><span data-stu-id="fc7ae-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fc7ae-132">方法: Windows フォーム DataGridView コントロールでデータの書式設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="fc7ae-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fc7ae-133">型の書式設定</span><span class="sxs-lookup"><span data-stu-id="fc7ae-133">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
