---
title: '方法: フォームに ToolStripContainer を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 3d69bc6ed0cf23da8315ae95565300d151069d51
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582578"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="64f44-102">方法: フォームに ToolStripContainer を追加する</span><span class="sxs-lookup"><span data-stu-id="64f44-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="64f44-103">プログラムで Windows フォームに <xref:System.Windows.Forms.ToolStripContainer> を追加し、そこにコントロールを配置できます。</span><span class="sxs-lookup"><span data-stu-id="64f44-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64f44-104">例</span><span class="sxs-lookup"><span data-stu-id="64f44-104">Example</span></span>  
 <span data-ttu-id="64f44-105">次のコード例は、Windows フォームに <xref:System.Windows.Forms.ToolStripContainer> および <xref:System.Windows.Forms.ToolStrip> を追加する方法、<xref:System.Windows.Forms.ToolStrip> に項目を追加する方法、<xref:System.Windows.Forms.ToolStripContainer> の <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> に <xref:System.Windows.Forms.ToolStrip> を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64f44-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="64f44-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="64f44-106">Compiling the Code</span></span>  
 <span data-ttu-id="64f44-107">このコード例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64f44-107">This code example requires:</span></span>  
  
- <span data-ttu-id="64f44-108">System.Drawing、System.Text、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="64f44-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f44-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="64f44-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="64f44-110">ToolStripContainer コントロール</span><span class="sxs-lookup"><span data-stu-id="64f44-110">ToolStripContainer Control</span></span>](toolstripcontainer-control.md)
- [<span data-ttu-id="64f44-111">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="64f44-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
