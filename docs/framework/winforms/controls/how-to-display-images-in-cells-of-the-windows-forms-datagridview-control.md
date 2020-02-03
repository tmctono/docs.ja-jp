---
title: DataGridView コントロールのセルに画像を表示する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740276"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="fb862-102">方法 : Windows フォーム DataGridView コントロールのセルにイメージを表示する</span><span class="sxs-lookup"><span data-stu-id="fb862-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fb862-103">画像またはグラフィックは、データ行に表示できる値の1つです。</span><span class="sxs-lookup"><span data-stu-id="fb862-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="fb862-104">多くの場合、これらのグラフィックは従業員の写真または会社のロゴの形になります。</span><span class="sxs-lookup"><span data-stu-id="fb862-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="fb862-105"><xref:System.Windows.Forms.DataGridView> コントロール内にデータを表示する場合、画像の組み込みは簡単です。</span><span class="sxs-lookup"><span data-stu-id="fb862-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="fb862-106"><xref:System.Windows.Forms.DataGridView> コントロールは、一部のデータベースで使用される OLE 画像形式だけでなく、<xref:System.Drawing.Image> クラスでサポートされているイメージ形式をネイティブで処理します。</span><span class="sxs-lookup"><span data-stu-id="fb862-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="fb862-107"><xref:System.Windows.Forms.DataGridView> コントロールのデータソースに画像の列がある場合は、<xref:System.Windows.Forms.DataGridView> コントロールによって自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb862-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="fb862-108">次のコード例では、埋め込みリソースからアイコンを抽出し、イメージ列のすべてのセルに表示するビットマップに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fb862-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="fb862-109">テキストのセル値を対応する画像に置き換える別の例については、「[方法: Windows フォーム DataGridView コントロールでデータの書式をカスタマイズ](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb862-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb862-110">例</span><span class="sxs-lookup"><span data-stu-id="fb862-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fb862-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="fb862-111">Compiling the Code</span></span>  
 <span data-ttu-id="fb862-112">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fb862-112">This example requires:</span></span>  
  
- <span data-ttu-id="fb862-113"><xref:System.Windows.Forms.DataGridView> という名前の `dataGridView1` コントロール。</span><span class="sxs-lookup"><span data-stu-id="fb862-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="fb862-114">`tree.ico`という名前の埋め込みアイコンリソース。</span><span class="sxs-lookup"><span data-stu-id="fb862-114">An embedded icon resource named `tree.ico`.</span></span>  
  
- <span data-ttu-id="fb862-115"><xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、および <xref:System.Drawing?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="fb862-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb862-116">参照</span><span class="sxs-lookup"><span data-stu-id="fb862-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="fb862-117">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="fb862-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="fb862-118">方法: Windows フォーム DataGridView コントロールのデータの書式設定をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="fb862-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
