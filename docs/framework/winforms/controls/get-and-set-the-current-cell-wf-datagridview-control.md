---
title: DataGridView コントロールの現在のセルを取得および設定します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 0fb01d5392e02b53e0e5bf905c872dbeeb22fad9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745662"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5b443-102">方法 : Windows フォーム DataGridView コントロールの現在のセルを取得および設定する</span><span class="sxs-lookup"><span data-stu-id="5b443-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5b443-103">多くの場合、<xref:System.Windows.Forms.DataGridView> とのやり取りでは、どのセルが現在アクティブであるかをプログラムで検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b443-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="5b443-104">また、現在のセルの変更が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5b443-104">You may also need to change the current cell.</span></span> <span data-ttu-id="5b443-105">これらのタスクは、<xref:System.Windows.Forms.DataGridView.CurrentCell%2A> プロパティを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="5b443-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b443-106"><xref:System.Windows.Forms.DataGridViewBand.Visible%2A> プロパティが `false`に設定されている行または列の現在のセルを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5b443-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="5b443-107"><xref:System.Windows.Forms.DataGridView> コントロールの選択モードによっては、現在のセルを変更すると選択内容を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5b443-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="5b443-108">詳細については、「 [Windows フォーム DataGridView コントロールの選択モード](selection-modes-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b443-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="5b443-109">現在のセルをプログラムで取得するには</span><span class="sxs-lookup"><span data-stu-id="5b443-109">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="5b443-110"><xref:System.Windows.Forms.DataGridView> コントロールの <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b443-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="5b443-111">現在のセルをプログラムによって設定するには</span><span class="sxs-lookup"><span data-stu-id="5b443-111">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="5b443-112"><xref:System.Windows.Forms.DataGridView> コントロールの <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5b443-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5b443-113">次のコード例では、現在のセルは行0、列1に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5b443-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b443-114">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="5b443-114">Compiling the Code</span></span>  
 <span data-ttu-id="5b443-115">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5b443-115">This example requires:</span></span>  
  
- <span data-ttu-id="5b443-116">`getCurrentCellButton` と `setCurrentCellButton`という名前のコントロールを <xref:System.Windows.Forms.Button> します。</span><span class="sxs-lookup"><span data-stu-id="5b443-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="5b443-117">ビジュアルC#では、各ボタンの <xref:System.Windows.Forms.Control.Click> イベントを、コード例の関連付けられたイベントハンドラーにアタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b443-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="5b443-118">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="5b443-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="5b443-119"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="5b443-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b443-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b443-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5b443-121">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="5b443-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="5b443-122">Windows フォーム DataGridView コントロールの選択モード</span><span class="sxs-lookup"><span data-stu-id="5b443-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
