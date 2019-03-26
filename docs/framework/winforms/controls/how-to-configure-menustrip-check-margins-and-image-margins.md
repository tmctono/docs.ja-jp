---
title: '方法: MenuStrip のチェックの余白とイメージの余白'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: f75cce1a9c155174178a55213d6a21ad5ba99772
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707847"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="49c1d-102">方法: MenuStrip のチェックの余白とイメージの余白</span><span class="sxs-lookup"><span data-stu-id="49c1d-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="49c1d-103"><xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> プロパティと <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> プロパティをさまざまな組み合わせで設定することにより、<xref:System.Windows.Forms.MenuStrip> をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="49c1d-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49c1d-104">例</span><span class="sxs-lookup"><span data-stu-id="49c1d-104">Example</span></span>  
 <span data-ttu-id="49c1d-105">次のコード例では、<xref:System.Windows.Forms.ContextMenuStrip> のチェックの余白とイメージの余白をカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49c1d-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="49c1d-106">手順は <xref:System.Windows.Forms.ContextMenuStrip> または <xref:System.Windows.Forms.MenuStrip> と同じです。</span><span class="sxs-lookup"><span data-stu-id="49c1d-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49c1d-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="49c1d-107">Compiling the Code</span></span>  
 <span data-ttu-id="49c1d-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49c1d-108">This example requires:</span></span>  
  
-   <span data-ttu-id="49c1d-109">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="49c1d-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="49c1d-110">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="49c1d-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="49c1d-111">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="49c1d-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c1d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="49c1d-112">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="49c1d-113">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="49c1d-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="49c1d-114">方法: ContextMenuStrip コントロールでチェックの余白とイメージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="49c1d-114">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
