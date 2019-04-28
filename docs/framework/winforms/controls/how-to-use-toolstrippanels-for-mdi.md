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
ms.openlocfilehash: 42d4ed23f477f545c4ff2be53c36d8ea86d3b4f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785763"
---
# <a name="how-to-use-toolstrippanels-for-mdi"></a><span data-ttu-id="02b5b-102">方法: ToolStripPanel を MDI で使用する</span><span class="sxs-lookup"><span data-stu-id="02b5b-102">How to: Use ToolStripPanels for MDI</span></span>
<span data-ttu-id="02b5b-103"><xref:System.Windows.Forms.ToolStripPanel> では、<xref:System.Windows.Forms.ToolStripPanel.Join%2A> メソッドを使用することにより、マルチ ドキュメント インターフェイス (MDI) アプリケーションに柔軟に対応できます。</span><span class="sxs-lookup"><span data-stu-id="02b5b-103">The <xref:System.Windows.Forms.ToolStripPanel> provides flexibility for multiple-document interface (MDI) applications by using the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02b5b-104">例</span><span class="sxs-lookup"><span data-stu-id="02b5b-104">Example</span></span>  
 <span data-ttu-id="02b5b-105">次のコード例は、<xref:System.Windows.Forms.ToolStripPanel> コントロールを MDI で使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="02b5b-105">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls for MDI.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="02b5b-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="02b5b-106">Compiling the Code</span></span>  
 <span data-ttu-id="02b5b-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="02b5b-107">This example requires:</span></span>  
  
- <span data-ttu-id="02b5b-108">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="02b5b-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="02b5b-109">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02b5b-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="02b5b-110">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="02b5b-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b5b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="02b5b-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripPanel>
- [<span data-ttu-id="02b5b-112">方法: Toolstrippanel を結合します。</span><span class="sxs-lookup"><span data-stu-id="02b5b-112">How to: Join ToolStripPanels</span></span>](how-to-join-toolstrippanels.md)
