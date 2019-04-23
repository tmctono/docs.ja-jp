---
title: '方法: ToolStrip の項目を動的に追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
ms.openlocfilehash: d84b62005554479d227778f513e72594322791a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124931"
---
# <a name="how-to-add-toolstrip-items-dynamically"></a><span data-ttu-id="2b4bf-102">方法: ToolStrip の項目を動的に追加する</span><span class="sxs-lookup"><span data-stu-id="2b4bf-102">How to: Add ToolStrip Items Dynamically</span></span>
<span data-ttu-id="2b4bf-103">メニューが開くときに <xref:System.Windows.Forms.ToolStrip> コントロールのメニュー項目コレクションを動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="2b4bf-103">You can dynamically populate the menu item collection of a <xref:System.Windows.Forms.ToolStrip> control when the menu opens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b4bf-104">例</span><span class="sxs-lookup"><span data-stu-id="2b4bf-104">Example</span></span>  
 <span data-ttu-id="2b4bf-105">次のコード例は、<xref:System.Windows.Forms.ContextMenuStrip> コントロールに項目を動的に追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b4bf-105">The following code example demonstrates how to dynamically add items to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="2b4bf-106">この例は、フォーム上の 3 つの異なるコントロールに同じ <xref:System.Windows.Forms.ContextMenuStrip> を再利用する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="2b4bf-106">The example also shows how to reuse the same <xref:System.Windows.Forms.ContextMenuStrip> for three different controls on the form.</span></span>  
  
 <span data-ttu-id="2b4bf-107">この例では、<xref:System.Windows.Forms.ToolStripDropDown.Opening> イベント ハンドラーがメニュー項目コレクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b4bf-107">In the example, an <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler populates the menu item collection.</span></span> <span data-ttu-id="2b4bf-108"><xref:System.Windows.Forms.ToolStripDropDown.Opening> イベント ハンドラーは、<xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> プロパティと <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> プロパティを調べて、ソース管理を示す <xref:System.Windows.Forms.ToolStripItem> を追加します。</span><span class="sxs-lookup"><span data-stu-id="2b4bf-108">The <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler examines the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> properties and adds a <xref:System.Windows.Forms.ToolStripItem> describing the source control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b4bf-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="2b4bf-109">Compiling the Code</span></span>  
 <span data-ttu-id="2b4bf-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2b4bf-110">This example requires:</span></span>  
  
-   <span data-ttu-id="2b4bf-111">System.Drawing アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="2b4bf-111">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="2b4bf-112">この例をコマンドラインから Visual Basic または Visual C# にビルドする方法の詳細については、[コマンドラインからのビルド](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[csc.exe を使用したコマンド ラインからのビルド](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b4bf-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2b4bf-113">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b4bf-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4bf-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b4bf-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- [<span data-ttu-id="2b4bf-115">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="2b4bf-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
