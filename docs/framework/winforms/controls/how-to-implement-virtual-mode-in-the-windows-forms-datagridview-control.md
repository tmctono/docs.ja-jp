---
title: DataGridView コントロールでの仮想モードの実装
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: f8612a808ac5c9facee55d820529945f481a2cea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736509"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="959c5-102">方法 : Windows フォーム DataGridView コントロールで仮想モードを実装する</span><span class="sxs-lookup"><span data-stu-id="959c5-102">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="959c5-103">次のコード例は、<xref:System.Windows.Forms.DataGridView.VirtualMode%2A> プロパティを `true` に設定した <xref:System.Windows.Forms.DataGridView> コントロールを使用して、大規模なデータ セットを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="959c5-103">The following code example demonstrates how to manage large sets of data using a <xref:System.Windows.Forms.DataGridView> control with its <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property set to `true`.</span></span>  
  
 <span data-ttu-id="959c5-104">このコード例の詳細な説明については、「[チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="959c5-104">For a complete explanation of this code example, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="959c5-105">使用例</span><span class="sxs-lookup"><span data-stu-id="959c5-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="959c5-106">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="959c5-106">Compiling the Code</span></span>  
 <span data-ttu-id="959c5-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="959c5-107">This example requires:</span></span>  
  
- <span data-ttu-id="959c5-108">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="959c5-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="959c5-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="959c5-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="959c5-110">チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装</span><span class="sxs-lookup"><span data-stu-id="959c5-110">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)
- [<span data-ttu-id="959c5-111">Windows フォーム DataGridView コントロールでのパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="959c5-111">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="959c5-112">Windows フォーム DataGridView コントロールでの仮想モード</span><span class="sxs-lookup"><span data-stu-id="959c5-112">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)
