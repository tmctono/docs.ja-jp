---
title: データバインドされた DataGridView コントロールに非バインド列を追加する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 807bbc121f33c35d70068571e76637c078ecb3da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747062"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="0f2fb-102">方法 : データバインドされた Windows フォーム DataGridView コントロールに非バインド列を追加する</span><span class="sxs-lookup"><span data-stu-id="0f2fb-102">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0f2fb-103"><xref:System.Windows.Forms.DataGridView> コントロールに表示するデータは、通常なんらかのデータ ソースから取得されるデータですが、データ ソース以外からのデータの列を表示する必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-103">The data you display in the <xref:System.Windows.Forms.DataGridView> control will normally come from a data source of some kind, but you might want to display a column of data that does not come from the data source.</span></span> <span data-ttu-id="0f2fb-104">この種類の列は、非バインド列と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-104">This kind of column is called an unbound column.</span></span> <span data-ttu-id="0f2fb-105">非バインド列の形式はさまざまです。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-105">Unbound columns can take many forms.</span></span> <span data-ttu-id="0f2fb-106">しばしば、データ行の詳細へのアクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-106">Frequently, they are used to provide access to the details of a data row.</span></span>  
  
 <span data-ttu-id="0f2fb-107">次のコード例では、マスター/詳細シナリオを実装するときに、親テーブルの特定の行に関連する子テーブルを表示する、 **[詳細]** ボタンのバインドされていない列を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-107">The following code example demonstrates how to create an unbound column of **Details** buttons to display a child table related to a particular row in a parent table when you implement a master/detail scenario.</span></span> <span data-ttu-id="0f2fb-108">ボタンのクリックに応答するには、子テーブルを含むフォームを表示する <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> イベント ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-108">To respond to button clicks, implement a <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> event handler that displays a form containing the child table.</span></span>  
  
 <span data-ttu-id="0f2fb-109">Visual Studio では、このタスクに対するサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="0f2fb-110">「[方法: デザイナーを使用して Windows フォーム DataGridView コントロールで列を追加および削除する](add-and-remove-columns-in-the-datagrid-using-the-designer.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-110">Also see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f2fb-111">例</span><span class="sxs-lookup"><span data-stu-id="0f2fb-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0f2fb-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="0f2fb-112">Compiling the Code</span></span>  
 <span data-ttu-id="0f2fb-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-113">This example requires:</span></span>  
  
- <span data-ttu-id="0f2fb-114"><xref:System.Windows.Forms.DataGridView> という名前の `dataGridView1` コントロール。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-114">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="0f2fb-115"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="0f2fb-115">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2fb-116">参照</span><span class="sxs-lookup"><span data-stu-id="0f2fb-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="0f2fb-117">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="0f2fb-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0f2fb-118">Windows フォーム DataGridView コントロールでのデータ表示モード</span><span class="sxs-lookup"><span data-stu-id="0f2fb-118">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
