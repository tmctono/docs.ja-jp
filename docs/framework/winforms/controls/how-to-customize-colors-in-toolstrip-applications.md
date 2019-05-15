---
title: '方法: ToolStrip アプリケーションの色をカスタマイズする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 6719156d0ab6d1e53cd0bd8f16f306577589fb40
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592844"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="00e5b-102">方法: ToolStrip アプリケーションの色をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="00e5b-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="00e5b-103"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> クラスを使用して、カスタマイズした色を使用すると、<xref:System.Windows.Forms.ToolStrip> の外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="00e5b-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00e5b-104">例</span><span class="sxs-lookup"><span data-stu-id="00e5b-104">Example</span></span>  
 <span data-ttu-id="00e5b-105">次のコード例は、<xref:System.Windows.Forms.ToolStripProfessionalRenderer> を使用してカスタム カラーを実行時に定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="00e5b-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00e5b-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="00e5b-106">Compiling the Code</span></span>  
 <span data-ttu-id="00e5b-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00e5b-107">This example requires:</span></span>  
  
- <span data-ttu-id="00e5b-108">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="00e5b-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e5b-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="00e5b-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
