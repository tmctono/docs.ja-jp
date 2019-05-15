---
title: '方法: ToolStripPanel を MDI で使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], using ToolStripPanels [Windows Forms]
- ToolStripPanel control [Windows Forms], using for MDI
- toolbars [Windows Forms], using for MDI
ms.assetid: d6b884fc-0846-465f-83c3-5dc0fe93b00f
ms.openlocfilehash: 9bc64af92fbff26798d1cffede983cbab7ba13da
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591553"
---
# <a name="how-to-use-toolstrippanels-for-mdi"></a><span data-ttu-id="05733-102">方法: ToolStripPanel を MDI で使用する</span><span class="sxs-lookup"><span data-stu-id="05733-102">How to: Use ToolStripPanels for MDI</span></span>
<span data-ttu-id="05733-103"><xref:System.Windows.Forms.ToolStripPanel> では、<xref:System.Windows.Forms.ToolStripPanel.Join%2A> メソッドを使用することにより、マルチ ドキュメント インターフェイス (MDI) アプリケーションに柔軟に対応できます。</span><span class="sxs-lookup"><span data-stu-id="05733-103">The <xref:System.Windows.Forms.ToolStripPanel> provides flexibility for multiple-document interface (MDI) applications by using the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05733-104">例</span><span class="sxs-lookup"><span data-stu-id="05733-104">Example</span></span>  
 <span data-ttu-id="05733-105">次のコード例は、<xref:System.Windows.Forms.ToolStripPanel> コントロールを MDI で使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="05733-105">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls for MDI.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="05733-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="05733-106">Compiling the Code</span></span>  
 <span data-ttu-id="05733-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="05733-107">This example requires:</span></span>  
  
- <span data-ttu-id="05733-108">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="05733-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05733-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="05733-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripPanel>
- [<span data-ttu-id="05733-110">方法: Toolstrippanel を結合します。</span><span class="sxs-lookup"><span data-stu-id="05733-110">How to: Join ToolStripPanels</span></span>](how-to-join-toolstrippanels.md)
