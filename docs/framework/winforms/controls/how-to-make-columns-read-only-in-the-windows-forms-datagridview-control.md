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
ms.openlocfilehash: 2a4ca0a718373c56f77e8f3c45a9d6ee6d76a081
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638377"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d83dd-102">方法: Windows フォームの DataGridView コントロールで列を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="d83dd-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d83dd-103">すべてのデータが編集できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d83dd-103">Not all data is meant for editing.</span></span> <span data-ttu-id="d83dd-104"><xref:System.Windows.Forms.DataGridView> コントロールでは、列の <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> プロパティの値はユーザーがその列のセルを編集できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d83dd-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="d83dd-105">完全に読み取り専用コントロールを作成する方法については、次を参照してください。[方法。行の追加を回避し、削除を Windows フォーム DataGridView コントロール](prevent-row-addition-and-deletion-datagridview.md)します。</span><span class="sxs-lookup"><span data-stu-id="d83dd-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="d83dd-106">Visual Studio では、このタスクに対するサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d83dd-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="d83dd-107">参照してください[方法。列を読み取り専用の Windows フォーム DataGridView コントロールのデザイナーを使用して](make-columns-read-only-in-the-datagrid-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="d83dd-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="d83dd-108">プログラムで列を読み取り専用にするには</span><span class="sxs-lookup"><span data-stu-id="d83dd-108">To make a column read-only programmatically</span></span>  
  
- <span data-ttu-id="d83dd-109"><xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d83dd-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d83dd-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d83dd-110">Compiling the Code</span></span>  
 <span data-ttu-id="d83dd-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d83dd-111">This example requires:</span></span>  
  
- <span data-ttu-id="d83dd-112">`CompanyName` という名前の列を持つ `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="d83dd-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
- <span data-ttu-id="d83dd-113"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="d83dd-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d83dd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d83dd-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d83dd-115">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="d83dd-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="d83dd-116">方法: Windows フォームの DataGridView コントロールで行の追加および削除を防ぐ</span><span class="sxs-lookup"><span data-stu-id="d83dd-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)
