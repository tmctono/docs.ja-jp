---
title: '方法: デザイナーを使用して Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: fb338a3616bc20542ec940db5977c4ffdab9654c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012426"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="d82bd-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="d82bd-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="d82bd-103">表形式のデータは多くの場合、別の背景色の交互の行のある帳簿のような形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="d82bd-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="d82bd-104">この形式を使用すると、多数の列がある幅の広いテーブルで、ユーザーが各行にあるセルを簡単に識別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d82bd-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="d82bd-105"><xref:System.Windows.Forms.DataGridView> コントロールを使用すると、1 行おきの完全なスタイル情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d82bd-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="d82bd-106">交互の行を区別するために、前景色と背景の色に加えて、フォントなどのスタイル特性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d82bd-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="d82bd-107">詳細については、次を参照してください。 [Windows フォームの DataGridView コントロールのセル スタイル](cell-styles-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="d82bd-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="d82bd-108">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d82bd-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d82bd-109">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="d82bd-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d82bd-110">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d82bd-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d82bd-111">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d82bd-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d82bd-112">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d82bd-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="d82bd-113">交互の行のスタイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="d82bd-113">Define styles for alternating rows</span></span>  
  
1. <span data-ttu-id="d82bd-114">選択、<xref:System.Windows.Forms.DataGridView>デザイナーでコントロールできます。</span><span class="sxs-lookup"><span data-stu-id="d82bd-114">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>  
  
2. <span data-ttu-id="d82bd-115">**プロパティ**ウィンドウで、省略記号ボタンをクリックします (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) 横に、<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d82bd-115">In the **Properties** window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>  
  
3. <span data-ttu-id="d82bd-116">**CellStyle ビルダー**ダイアログ ボックスで、プロパティを設定してスタイルを定義して、**プレビュー**ウィンドウで選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="d82bd-116">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="d82bd-117">以降、2 つ目では、コントロールに表示されるその他のすべての行では、指定したスタイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d82bd-117">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>  
  
4. <span data-ttu-id="d82bd-118">残りの行のスタイルを定義するには、手順 2 および 3 を使用して、<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d82bd-118">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d82bd-119">セルは、複数のプロパティから継承されたスタイルを使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="d82bd-119">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="d82bd-120">スタイルの継承の詳細については、次を参照してください。 [Windows フォームの DataGridView コントロールのセル スタイル](cell-styles-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="d82bd-120">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d82bd-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d82bd-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="d82bd-122">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="d82bd-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d82bd-123">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="d82bd-123">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d82bd-124">Windows フォーム DataGridView コントロールでのデザイナーの使用</span><span class="sxs-lookup"><span data-stu-id="d82bd-124">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d82bd-125">方法: Windows フォーム アプリケーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d82bd-125">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="d82bd-126">方法: Windows フォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="d82bd-126">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
