---
title: '方法: Windows フォームの DataGridView コントロールで列を読み取り専用にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: c865db5caf33b34f12c7acf8078995b12db3c970
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649281"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4f50b-102">方法: Windows フォームの DataGridView コントロールで列を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="4f50b-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4f50b-103">すべてのデータが編集できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="4f50b-103">Not all data is meant for editing.</span></span> <span data-ttu-id="4f50b-104"><xref:System.Windows.Forms.DataGridView> コントロールでは、列の <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> プロパティの値はユーザーがその列のセルを編集できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4f50b-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="4f50b-105">完全に読み取り専用コントロールを作成する方法については、次を参照してください。[方法。行の追加を回避し、削除を Windows フォーム DataGridView コントロール](prevent-row-addition-and-deletion-datagridview.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f50b-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="4f50b-106">Visual Studio では、このタスクに対するサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f50b-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="4f50b-107">参照してください[方法。列を読み取り専用の Windows フォーム DataGridView コントロールのデザイナーを使用して](make-columns-read-only-in-the-datagrid-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f50b-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="4f50b-108">プログラムで列を読み取り専用にするには</span><span class="sxs-lookup"><span data-stu-id="4f50b-108">To make a column read-only programmatically</span></span>  
  
- <span data-ttu-id="4f50b-109"><xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="4f50b-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f50b-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4f50b-110">Compiling the Code</span></span>  
 <span data-ttu-id="4f50b-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f50b-111">This example requires:</span></span>  
  
- <span data-ttu-id="4f50b-112">`CompanyName` という名前の列を持つ `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="4f50b-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
- <span data-ttu-id="4f50b-113"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="4f50b-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f50b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f50b-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4f50b-115">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="4f50b-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="4f50b-116">方法: Windows フォームの DataGridView コントロールで行の追加および削除を防ぐ</span><span class="sxs-lookup"><span data-stu-id="4f50b-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)
