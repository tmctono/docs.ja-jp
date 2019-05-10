---
title: '方法: 実行時に ToolStrip レンダラーを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
ms.openlocfilehash: 7d52aa1b6049007928c4045ad52c982b16cd7a00
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630456"
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="fe503-102">方法: 実行時に ToolStrip レンダラーを設定する</span><span class="sxs-lookup"><span data-stu-id="fe503-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="fe503-103">カスタムの `ProfessionalColorTable` クラスを作成することで、<xref:System.Windows.Forms.ToolStrip> コントロールの外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="fe503-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe503-104">例</span><span class="sxs-lookup"><span data-stu-id="fe503-104">Example</span></span>  
 <span data-ttu-id="fe503-105">次のコード例は、カスタムの `ProfessionalColorTable` クラスを作成する方法を示しています</span><span class="sxs-lookup"><span data-stu-id="fe503-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="fe503-106">このクラスは、<xref:System.Windows.Forms.MenuStrip> コントロールと <xref:System.Windows.Forms.ToolStrip> コントロールのグラデーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe503-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="fe503-107">このコード例を使用するには、アプリケーションをコンパイルして実行し、**[色を変更]** をクリックして、カスタムの `ProfessionalColorTable` クラスで定義されているグラデーションを適用します。</span><span class="sxs-lookup"><span data-stu-id="fe503-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="fe503-108">カスタム ProfessionalColorTable クラスを定義する</span><span class="sxs-lookup"><span data-stu-id="fe503-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="fe503-109">カスタムのグラデーションは、`CustomProfessionalColors` クラスでで定義されます。</span><span class="sxs-lookup"><span data-stu-id="fe503-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="fe503-110">カスタム レンダラーの割り当て</span><span class="sxs-lookup"><span data-stu-id="fe503-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="fe503-111">`CustomProfessionalColors` クラスを使用して `ToolStripProfessionalRenderer` を新規作成し、<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> プロパティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fe503-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fe503-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="fe503-112">Compiling the Code</span></span>  
 <span data-ttu-id="fe503-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe503-113">This example requires:</span></span>  
  
- <span data-ttu-id="fe503-114">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="fe503-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fe503-115">コマンドラインからこの例を Visual Basic または Visual C# の構築方法の詳細については、[、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe503-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fe503-116">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe503-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe503-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe503-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="fe503-118">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="fe503-118">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
