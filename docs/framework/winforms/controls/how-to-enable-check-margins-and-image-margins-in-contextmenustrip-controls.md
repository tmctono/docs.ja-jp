---
title: '方法: ContextMenuStrip コントロールでチェックの余白とイメージの余白を有効にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ShowCheckMargin property [Windows Forms]
- ShowImageMargin property [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: eb584e71-59da-4012-aaca-dbe1c7c7a156
ms.openlocfilehash: 80a6b5a7e3ce354abdfbe330a378566d47c011ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170899"
---
# <a name="how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls"></a><span data-ttu-id="8ad45-102">方法: ContextMenuStrip コントロールでチェックの余白とイメージの余白を有効にする</span><span class="sxs-lookup"><span data-stu-id="8ad45-102">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>
<span data-ttu-id="8ad45-103"><xref:System.Windows.Forms.ToolStripMenuItem> コントロールの <xref:System.Windows.Forms.MenuStrip> オブジェクトを、チェック マークやカスタム イメージを付けてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="8ad45-103">You can customize the <xref:System.Windows.Forms.ToolStripMenuItem> objects in your <xref:System.Windows.Forms.MenuStrip> control with check marks and custom images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ad45-104">例</span><span class="sxs-lookup"><span data-stu-id="8ad45-104">Example</span></span>  
 <span data-ttu-id="8ad45-105">次のコード例は、チェック マークとカスタム イメージを持つメニュー項目を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8ad45-105">The following code example demonstrates how to create menu items that have check marks and custom images.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
 <span data-ttu-id="8ad45-106"><xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> プロパティと <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> プロパティを設定して、チェック マークとカスタム イメージがメニュー項目に表示されるタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ad45-106">Set the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> properties to specify when check marks and custom images appear in your menu items.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ad45-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8ad45-107">Compiling the Code</span></span>  
 <span data-ttu-id="8ad45-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ad45-108">This example requires:</span></span>  
  
-   <span data-ttu-id="8ad45-109">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="8ad45-109">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8ad45-110">この例をコマンドラインから Visual Basic または Visual C# にビルドする方法の詳細については、[コマンドラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ad45-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8ad45-111">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ad45-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad45-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ad45-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="8ad45-113">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="8ad45-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
