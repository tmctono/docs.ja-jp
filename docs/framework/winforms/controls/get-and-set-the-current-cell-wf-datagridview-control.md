---
title: DataGridView コントロールの現在のセルを取得および設定します。
description: Windows フォーム DataGridView コントロールで現在のセルを取得および設定することによって、現在アクティブなセルをプログラムで検出する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 1651ca9c8fa0329f9435a70ce777bce68f15ff63
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622212"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c0847-103">方法: Windows フォーム DataGridView コントロールの現在のセルを取得および設定する</span><span class="sxs-lookup"><span data-stu-id="c0847-103">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c0847-104">との対話で <xref:System.Windows.Forms.DataGridView> は、現在アクティブなセルをプログラムによって検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0847-104">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="c0847-105">また、現在のセルの変更が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c0847-105">You may also need to change the current cell.</span></span> <span data-ttu-id="c0847-106">これらのタスクは、プロパティを使用して実行でき <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="c0847-106">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0847-107">プロパティがに設定されている行または列の現在のセルを設定することはできません <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> `false` 。</span><span class="sxs-lookup"><span data-stu-id="c0847-107">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="c0847-108">コントロールの選択モードによっては、現在のセルを変更すると <xref:System.Windows.Forms.DataGridView> 選択範囲が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0847-108">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="c0847-109">詳細については、「 [Windows フォーム DataGridView コントロールの選択モード](selection-modes-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0847-109">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="c0847-110">現在のセルをプログラムで取得するには</span><span class="sxs-lookup"><span data-stu-id="c0847-110">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="c0847-111"><xref:System.Windows.Forms.DataGridView>コントロールのプロパティを使用し <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="c0847-111">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="c0847-112">現在のセルをプログラムによって設定するには</span><span class="sxs-lookup"><span data-stu-id="c0847-112">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="c0847-113"><xref:System.Windows.Forms.DataGridView.CurrentCell%2A>コントロールのプロパティを設定 <xref:System.Windows.Forms.DataGridView> します。</span><span class="sxs-lookup"><span data-stu-id="c0847-113">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c0847-114">次のコード例では、現在のセルは行0、列1に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c0847-114">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c0847-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c0847-115">Compiling the Code</span></span>  
 <span data-ttu-id="c0847-116">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0847-116">This example requires:</span></span>  
  
- <span data-ttu-id="c0847-117"><xref:System.Windows.Forms.Button>およびという名前のコントロール `getCurrentCellButton` `setCurrentCellButton` 。</span><span class="sxs-lookup"><span data-stu-id="c0847-117"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="c0847-118">Visual C# では、 <xref:System.Windows.Forms.Control.Click> 各ボタンのイベントを、コード例の関連付けられたイベントハンドラーにアタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0847-118">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="c0847-119">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="c0847-119">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="c0847-120"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="c0847-120">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0847-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0847-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c0847-122">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="c0847-122">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="c0847-123">Windows フォーム DataGridView コントロールの選択モード</span><span class="sxs-lookup"><span data-stu-id="c0847-123">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
