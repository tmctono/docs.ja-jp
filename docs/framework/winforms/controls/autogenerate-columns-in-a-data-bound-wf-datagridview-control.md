---
title: データバインドされた DataGridView コントロールの列を自動生成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 860e640e095537358d2f8778c810aa577e9d7ff0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746236"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="d2f2d-102">方法 : データバインドされた Windows フォーム DataGridView コントロールに列を自動生成する</span><span class="sxs-lookup"><span data-stu-id="d2f2d-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d2f2d-103">次のコード例は、<xref:System.Windows.Forms.DataGridView> コントロールでバインドされたデータソースの列を表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d2f2d-104"><xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> プロパティ値が `true` (既定値) の場合、データソーステーブルの各列に対して <xref:System.Windows.Forms.DataGridViewColumn> が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="d2f2d-105"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> プロパティを設定するときに、<xref:System.Windows.Forms.DataGridView> コントロールに既に列がある場合、既存のバインドされた列はデータソース内の列と比較され、一致がある場合は常に保持されます。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="d2f2d-106">非バインド列は常に保持されます。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="d2f2d-107">データソースに一致するものがないバインド列は削除されます。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="d2f2d-108">コントロールに一致するものがないデータソース内の列によって、新しい <xref:System.Windows.Forms.DataGridViewColumn> オブジェクトが生成されます。これは <xref:System.Windows.Forms.DataGridView.Columns%2A> コレクションの末尾に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2f2d-109">使用例</span><span class="sxs-lookup"><span data-stu-id="d2f2d-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d2f2d-110">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="d2f2d-110">Compiling the Code</span></span>  
 <span data-ttu-id="d2f2d-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-111">This example requires:</span></span>  
  
- <span data-ttu-id="d2f2d-112">`customersDataGridView` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
- <span data-ttu-id="d2f2d-113">`Customers`という名前のテーブルを持つ `customersDataSet` という名前の <xref:System.Data.DataSet> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
- <span data-ttu-id="d2f2d-114"><xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、<xref:System.Data?displayProperty=nameWithType>、および <xref:System.Xml?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f2d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2f2d-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d2f2d-116">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="d2f2d-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d2f2d-117">方法: Windows フォーム DataGridView コントロールから自動生成された列を削除する</span><span class="sxs-lookup"><span data-stu-id="d2f2d-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
