---
title: '方法: メニューのマージと ToolStrip コントロールを MDI フォームを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 2942d0e92a0f58bef5533d69b27a646d284fef62
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721113"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="24e46-102">方法: メニューのマージと ToolStrip コントロールを MDI フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="24e46-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="24e46-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間は、マルチ ドキュメント インターフェイス (MDI) アプリケーションをサポートし、<xref:System.Windows.Forms.MenuStrip> コントロールはメニューの結合をサポートします。</span><span class="sxs-lookup"><span data-stu-id="24e46-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="24e46-104">MDI フォームは、<xref:System.Windows.Forms.ToolStrip> コントロールもサポートします。</span><span class="sxs-lookup"><span data-stu-id="24e46-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="24e46-105">Visual Studio でこの機能の広範なサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="24e46-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="24e46-106">参照してください[チュートリアル。メニューのマージと ToolStrip コントロールを MDI フォームを作成する](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="24e46-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="24e46-107">例</span><span class="sxs-lookup"><span data-stu-id="24e46-107">Example</span></span>  
 <span data-ttu-id="24e46-108">次のコード例は、<xref:System.Windows.Forms.ToolStripPanel> コントロールを MDI フォームで使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="24e46-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="24e46-109">フォームは、子メニューをマージするメニューもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="24e46-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24e46-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="24e46-110">Compiling the Code</span></span>  
 <span data-ttu-id="24e46-111">このコード例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="24e46-111">This code example requires:</span></span>  
  
-   <span data-ttu-id="24e46-112">System.Drawing アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="24e46-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="24e46-113">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="24e46-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="24e46-114">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="24e46-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e46-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="24e46-115">See also</span></span>
- [<span data-ttu-id="24e46-116">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="24e46-116">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
