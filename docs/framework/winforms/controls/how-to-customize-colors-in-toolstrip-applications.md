---
title: '方法: ToolStrip アプリケーションの色をカスタマイズします。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: db64ee353cc71cf39516e5ee0a08cf4b9627548c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709641"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="71267-102">方法: ToolStrip アプリケーションの色をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="71267-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="71267-103">
  <xref:System.Windows.Forms.ToolStripProfessionalRenderer> クラスを使用して、カスタマイズした色を使用すると、<xref:System.Windows.Forms.ToolStrip> の外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="71267-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71267-104">例</span><span class="sxs-lookup"><span data-stu-id="71267-104">Example</span></span>  
 <span data-ttu-id="71267-105">次のコード例は、<xref:System.Windows.Forms.ToolStripProfessionalRenderer> を使用してカスタム カラーを実行時に定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="71267-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71267-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="71267-106">Compiling the Code</span></span>  
 <span data-ttu-id="71267-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71267-107">This example requires:</span></span>  
  
-   <span data-ttu-id="71267-108">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="71267-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="71267-109">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="71267-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="71267-110">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="71267-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71267-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="71267-111">See also</span></span>
- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
