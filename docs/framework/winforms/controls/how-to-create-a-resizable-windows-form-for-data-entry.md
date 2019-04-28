---
title: '方法: データ入力用のサイズ変更可能な Windows フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: ebccad248927d8a201bd5758e5ddf2d5414455f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746642"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="a6f3c-102">方法: データ入力用のサイズ変更可能な Windows フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="a6f3c-102">How to: Create a Resizable Windows Form for Data Entry</span></span>
<span data-ttu-id="a6f3c-103">レイアウトが優れていると、その親フォームの寸法の変更に柔軟に対応できます。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="a6f3c-104"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用すると、フォームの寸法の変更に応じて一貫した方法でコントロールの位置とサイズが変更されるように、フォームのレイアウトを調整できます。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="a6f3c-105"><xref:System.Windows.Forms.TableLayoutPanel> コントロールは、コントロールの内容の変更によってレイアウトの変更が生じる場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="a6f3c-106">この手順で説明するプロセスは、Visual Studio 環境内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="a6f3c-107">参照してください[チュートリアル。データ エントリのサイズ変更可能な Windows フォームを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6f3c-108">例</span><span class="sxs-lookup"><span data-stu-id="a6f3c-108">Example</span></span>  
 <span data-ttu-id="a6f3c-109">ユーザーによるフォームのサイズ変更に適切に対応するレイアウトを <xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用して作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="a6f3c-110">また、ローカリゼーションに適切に対応するレイアウトも示します。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a6f3c-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a6f3c-111">Compiling the Code</span></span>  
 <span data-ttu-id="a6f3c-112">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-112">This example requires:</span></span>  
  
- <span data-ttu-id="a6f3c-113">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="a6f3c-114">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a6f3c-115">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f3c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6f3c-116">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="a6f3c-117">方法: 固定およびドッキング TableLayoutPanel コントロールで子コントロール</span><span class="sxs-lookup"><span data-stu-id="a6f3c-117">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="a6f3c-118">方法: ローカリゼーションに対応する Windows フォーム レイアウトをデザインします。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-118">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="a6f3c-119">Microsoft Windows ユーザー エクスペリエンス、Official Guidelines for ユーザー インターフェイス開発者および設計者です。Redmond、WA:Microsoft Press、1999 年。(USBN:0-7356-0566-1)</span><span class="sxs-lookup"><span data-stu-id="a6f3c-119">Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span></span>](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
