---
title: '方法: ローカリゼーションに対応した Windows フォーム レイアウトをデザインする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: 131dc688d2a742fa7a0d99ec7858d4e280c9882f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61926516"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="986e0-102">方法: ローカリゼーションに対応した Windows フォーム レイアウトをデザインする</span><span class="sxs-lookup"><span data-stu-id="986e0-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="986e0-103">ローカライズが可能なフォームを作成すると、各国市場向けの開発期間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="986e0-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="986e0-104"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用すると、<xref:System.Windows.Forms.Control.Text%2A> プロパティ値の変更によってコントロールのサイズが変更された際に、これに適切に応答するレイアウトを実装できます</span><span class="sxs-lookup"><span data-stu-id="986e0-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="986e0-105">例</span><span class="sxs-lookup"><span data-stu-id="986e0-105">Example</span></span>  
 <span data-ttu-id="986e0-106">このフォームでは、表示される文字列値を他の言語に翻訳するときに、均等に調整されるレイアウトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="986e0-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="986e0-107">この翻訳プロセスのことを "*ローカリゼーション*" といいます。</span><span class="sxs-lookup"><span data-stu-id="986e0-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="986e0-108">詳細については、「[ローカリゼーション](../../../standard/globalization-localization/localization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="986e0-108">For more information, see [Localization](../../../standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="986e0-109">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="986e0-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="986e0-110">参照してください[チュートリアル。ローカライズの縦横比が調整されるレイアウトの作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))です。</span><span class="sxs-lookup"><span data-stu-id="986e0-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a><span data-ttu-id="986e0-111">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="986e0-111">Additional resources</span></span>
1. [<span data-ttu-id="986e0-112">方法: 配置して、コントロールを TableLayoutPanel コントロールで伸縮</span><span class="sxs-lookup"><span data-stu-id="986e0-112">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="986e0-113">チュートリアル: FlowLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="986e0-113">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [<span data-ttu-id="986e0-114">方法: TableLayoutPanel コントロールの行と列にまたがる</span><span class="sxs-lookup"><span data-stu-id="986e0-114">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="986e0-115">方法: TableLayoutPanel コントロールの列と行を編集します。</span><span class="sxs-lookup"><span data-stu-id="986e0-115">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [<span data-ttu-id="986e0-116">チュートリアル: スマートを使用して一般的なタスクを実行する Windows フォーム コントロールをタグ</span><span class="sxs-lookup"><span data-stu-id="986e0-116">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [<span data-ttu-id="986e0-117">チュートリアル: TableLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="986e0-117">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [<span data-ttu-id="986e0-118">チュートリアル: Windows フォーム コントロール Padding、Margin、および AutoSize プロパティをレイアウト</span><span class="sxs-lookup"><span data-stu-id="986e0-118">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)  
  
8. <span data-ttu-id="986e0-119">[方法: AutoSize と TableLayoutPanel コントロールを使用して Windows フォームのローカリゼーションをサポートします。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="986e0-119">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span></span>  
  
9. <span data-ttu-id="986e0-120">[チュートリアル: データ エントリのサイズ変更可能な Windows フォームを作成します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="986e0-120">[Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="986e0-121">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="986e0-121">Compiling the Code</span></span>  
 <span data-ttu-id="986e0-122">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="986e0-122">This example requires:</span></span>  
  
- <span data-ttu-id="986e0-123">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="986e0-123">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="986e0-124">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="986e0-124">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="986e0-125">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="986e0-125">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="986e0-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="986e0-126">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="986e0-127">ローカリゼーション</span><span class="sxs-lookup"><span data-stu-id="986e0-127">Localization</span></span>](../../../standard/globalization-localization/localization.md)
