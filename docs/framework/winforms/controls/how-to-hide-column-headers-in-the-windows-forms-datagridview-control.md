---
title: '方法: Windows フォーム DataGridView コントロールの列ヘッダーを非表示にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: 888ff59d42f44db652d3188e016b9e10a9590139
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651669"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8da62-102">方法: Windows フォーム DataGridView コントロールの列ヘッダーを非表示にする</span><span class="sxs-lookup"><span data-stu-id="8da62-102">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8da62-103">表示することもありますが、<xref:System.Windows.Forms.DataGridView>列ヘッダーのないです。</span><span class="sxs-lookup"><span data-stu-id="8da62-103">Sometimes you will want to display a <xref:System.Windows.Forms.DataGridView> without column headers.</span></span> <span data-ttu-id="8da62-104"><xref:System.Windows.Forms.DataGridView>コントロール、<xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A>プロパティの値が列ヘッダーを表示するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="8da62-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> property value determines whether the column headers are displayed.</span></span>  
  
### <a name="to-hide-the-column-headers"></a><span data-ttu-id="8da62-105">列ヘッダーを非表示にするには</span><span class="sxs-lookup"><span data-stu-id="8da62-105">To hide the column headers</span></span>  
  
- <span data-ttu-id="8da62-106"><xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="8da62-106">Set the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8da62-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8da62-107">Compiling the Code</span></span>  
 <span data-ttu-id="8da62-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8da62-108">This example requires:</span></span>  
  
- <span data-ttu-id="8da62-109">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="8da62-109">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="8da62-110"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="8da62-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8da62-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8da62-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8da62-112">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="8da62-112">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
