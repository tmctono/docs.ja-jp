---
title: '方法: Windows フォーム DataGridView コントロールのセルの変更に基づいてカスタム動作を実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: 0573199e9afb7e52c7542d36a2f3e39730dacdc4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012673"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="59d43-102">方法: Windows フォーム DataGridView コントロールのセルの変更に基づいてカスタム動作を実行する</span><span class="sxs-lookup"><span data-stu-id="59d43-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="59d43-103"><xref:System.Windows.Forms.DataGridView>コントロールが状態の変更を検出するために使用できるイベントの数が<xref:System.Windows.Forms.DataGridView>セル。</span><span class="sxs-lookup"><span data-stu-id="59d43-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="59d43-104">2 つの最も一般的に使用される、<xref:System.Windows.Forms.DataGridView.CellValueChanged>と<xref:System.Windows.Forms.DataGridView.CellStateChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="59d43-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="59d43-105">DataGridView セルの値に変更を検出するには</span><span class="sxs-lookup"><span data-stu-id="59d43-105">To detect changes in the values of DataGridView cells</span></span>  
  
- <span data-ttu-id="59d43-106">ハンドラーを記述、<xref:System.Windows.Forms.DataGridView.CellValueChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="59d43-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="59d43-107">DataGridView セルの状態の変更を検出するには</span><span class="sxs-lookup"><span data-stu-id="59d43-107">To detect changes in the states of DataGridView cells</span></span>  
  
- <span data-ttu-id="59d43-108">ハンドラーを記述、<xref:System.Windows.Forms.DataGridView.CellStateChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="59d43-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="59d43-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="59d43-109">Compiling the Code</span></span>  
 <span data-ttu-id="59d43-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="59d43-110">This example requires:</span></span>  
  
- <span data-ttu-id="59d43-111">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="59d43-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="59d43-112">C#、対応するイベントにイベント ハンドラーを接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59d43-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
- <span data-ttu-id="59d43-113"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="59d43-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59d43-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="59d43-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="59d43-115">Windows フォーム DataGridView コントロールのセル、行、および列を使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="59d43-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="59d43-116">チュートリアル: Windows フォームの DataGridView コントロールのデータの検証</span><span class="sxs-lookup"><span data-stu-id="59d43-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
