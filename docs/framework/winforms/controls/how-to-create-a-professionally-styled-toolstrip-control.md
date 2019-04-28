---
title: '方法: プロフェッショナル スタイルの ToolStrip コントロールを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 6da6e113867efed79dfcd02f3b89ee1f9ae13c4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746668"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="159e9-102">方法: プロフェッショナル スタイルの ToolStrip コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="159e9-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="159e9-103"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> 型から派生する独自のクラスを記述することで、アプリケーションの <xref:System.Windows.Forms.ToolStrip> コントロールにプロフェッショナルな外観と動作 (操作性) を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="159e9-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="159e9-104">Visual Studio でこの機能の広範なサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="159e9-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="159e9-105">「[チュートリアル:プロフェッショナル スタイルの ToolStrip コントロールの作成](walkthrough-creating-a-professionally-styled-toolstrip-control.md)です。</span><span class="sxs-lookup"><span data-stu-id="159e9-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="159e9-106">例</span><span class="sxs-lookup"><span data-stu-id="159e9-106">Example</span></span>  
 <span data-ttu-id="159e9-107">次のコード例は、使用する方法を示します<xref:System.Windows.Forms.ToolStrip>似た複合コントロールを作成するコントロール、**ナビゲーション ウィンドウ**Microsoft® Outlook® で提供されます。</span><span class="sxs-lookup"><span data-stu-id="159e9-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="159e9-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="159e9-108">Compiling the Code</span></span>  
 <span data-ttu-id="159e9-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="159e9-109">This example requires:</span></span>  
  
- <span data-ttu-id="159e9-110">System.Drawing アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="159e9-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="159e9-111">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="159e9-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="159e9-112">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="159e9-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="159e9-113">参照してください[チュートリアル。プロフェッショナル スタイルの ToolStrip コントロールの作成](walkthrough-creating-a-professionally-styled-toolstrip-control.md)です。</span><span class="sxs-lookup"><span data-stu-id="159e9-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159e9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="159e9-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="159e9-115">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="159e9-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="159e9-116">方法: フォームに標準メニュー項目を提供します。</span><span class="sxs-lookup"><span data-stu-id="159e9-116">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
