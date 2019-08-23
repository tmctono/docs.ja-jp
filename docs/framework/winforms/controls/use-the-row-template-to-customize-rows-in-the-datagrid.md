---
title: '方法: 行テンプレートを使用して Windows フォーム DataGridView コントロールの行をカスタマイズする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 0dba318e6aa35761f4e9471fdb13b65644747b57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966504"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="bf5a7-102">方法: 行テンプレートを使用して Windows フォーム DataGridView コントロールの行をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="bf5a7-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="bf5a7-103">コントロール<xref:System.Windows.Forms.DataGridView>は、データバインディングを使用してコントロールに追加するすべての行の基礎として、または使用する既存<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType>の行を指定せずにメソッドを呼び出すと、行テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="bf5a7-104">行テンプレートを使用すると、 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>プロパティよりも行の外観と動作をより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="bf5a7-105">行テンプレートを使用して、など<xref:System.Windows.Forms.DataGridViewRow> <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="bf5a7-106">場合によっては、行テンプレートを使用して特定の効果を実現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="bf5a7-107">たとえば、行の高さ情報をに格納<xref:System.Windows.Forms.DataGridViewCellStyle>することはできません。そのため、行テンプレートを使用して、すべての行で使用される既定の高さを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="bf5a7-108">行テンプレートは、から<xref:System.Windows.Forms.DataGridViewRow>派生した独自のクラスを作成し、新しい行がコントロールに追加されたときにカスタム型を使用する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf5a7-109">行テンプレートは、行が追加された場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="bf5a7-110">行テンプレートを変更して既存の行を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="bf5a7-111">行テンプレートを使用するには</span><span class="sxs-lookup"><span data-stu-id="bf5a7-111">To use the row template</span></span>  
  
- <span data-ttu-id="bf5a7-112"><xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>プロパティから取得したオブジェクトのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bf5a7-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="bf5a7-113">Compiling the Code</span></span>  
 <span data-ttu-id="bf5a7-114">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-114">This example requires:</span></span>  
  
- <span data-ttu-id="bf5a7-115">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="bf5a7-116"><xref:System?displayProperty=nameWithType>、<xref:System.Drawing?displayProperty=nameWithType>、および <xref:System.Windows.Forms?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="bf5a7-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5a7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf5a7-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bf5a7-118">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="bf5a7-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="bf5a7-119">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="bf5a7-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
