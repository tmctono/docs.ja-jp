---
title: DataGridView コントロールのセルの変更に基づいてカスタム動作を実行する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: a809134b0a79bc9685c5b84acce58b4c61b5c526
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744286"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="a34fd-102">方法 : Windows フォーム DataGridView コントロールのセルの変更に基づいてカスタム動作を実行する</span><span class="sxs-lookup"><span data-stu-id="a34fd-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a34fd-103"><xref:System.Windows.Forms.DataGridView> コントロールには、<xref:System.Windows.Forms.DataGridView> セルの状態の変化を検出するために使用できる多数のイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="a34fd-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="a34fd-104">最も一般的に使用されるのは、<xref:System.Windows.Forms.DataGridView.CellValueChanged> イベントと <xref:System.Windows.Forms.DataGridView.CellStateChanged> イベントです。</span><span class="sxs-lookup"><span data-stu-id="a34fd-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="a34fd-105">DataGridView セルの値の変更を検出するには</span><span class="sxs-lookup"><span data-stu-id="a34fd-105">To detect changes in the values of DataGridView cells</span></span>  
  
- <span data-ttu-id="a34fd-106"><xref:System.Windows.Forms.DataGridView.CellValueChanged> イベントのハンドラーを記述します。</span><span class="sxs-lookup"><span data-stu-id="a34fd-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="a34fd-107">DataGridView セルの状態の変化を検出するには</span><span class="sxs-lookup"><span data-stu-id="a34fd-107">To detect changes in the states of DataGridView cells</span></span>  
  
- <span data-ttu-id="a34fd-108"><xref:System.Windows.Forms.DataGridView.CellStateChanged> イベントのハンドラーを記述します。</span><span class="sxs-lookup"><span data-stu-id="a34fd-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a34fd-109">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="a34fd-109">Compiling the Code</span></span>  
 <span data-ttu-id="a34fd-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a34fd-110">This example requires:</span></span>  
  
- <span data-ttu-id="a34fd-111">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="a34fd-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="a34fd-112">C#では、イベントハンドラーが対応するイベントに接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a34fd-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
- <span data-ttu-id="a34fd-113"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="a34fd-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a34fd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a34fd-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="a34fd-115">Windows フォーム DataGridView コントロールのセル、行、および列を使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="a34fd-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="a34fd-116">チュートリアル: Windows フォーム DataGridView コントロールのデータの妥当性検査</span><span class="sxs-lookup"><span data-stu-id="a34fd-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
