---
title: '方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 80ede9b7bc5bf667e03dc0a745fbc0b5f6c2663a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640476"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="39573-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="39573-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="39573-103">Windows フォーム<xref:System.Windows.Forms.DataGridView>コントロールがデータを表示するために列を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="39573-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="39573-104">コントロールを手動で設定する場合は、する必要があります列を追加する、自分でします。</span><span class="sxs-lookup"><span data-stu-id="39573-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="39573-105">または、コントロールを生成し、列に自動的に設定するデータ ソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="39573-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="39573-106">データ ソースに表示するより多くの列が含まれている場合は、不要な列を削除できます。</span><span class="sxs-lookup"><span data-stu-id="39573-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="39573-107">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="39573-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="39573-108">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="39573-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39573-109">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="39573-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="39573-110">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39573-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="39573-111">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39573-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="39573-112">デザイナーを使用して列を追加するには</span><span class="sxs-lookup"><span data-stu-id="39573-112">To add a column using the designer</span></span>  
  
1. <span data-ttu-id="39573-113">スマート タグ グリフをクリックします (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) の右上隅で、 <xref:System.Windows.Forms.DataGridView> 、制御し、**列の追加**します。</span><span class="sxs-lookup"><span data-stu-id="39573-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2. <span data-ttu-id="39573-114">**列の追加** ダイアログ ボックスで、選択、**データ バインド列**オプションし、データ ソースから列を選択するか選択、**非バインド列**オプションを選択し、列の定義該当するフィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="39573-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3. <span data-ttu-id="39573-115">をクリックして、**追加**に既存の列が既にいっぱいになるコントロールの表示領域がある場合に、デザイナーに表示される原因となる列を追加するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="39573-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39573-116">列のプロパティを変更することができます、**列の編集** ダイアログ ボックスで、コントロールのスマート タグからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="39573-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="39573-117">デザイナーを使用して列を削除するには</span><span class="sxs-lookup"><span data-stu-id="39573-117">To remove a column using the designer</span></span>  
  
1. <span data-ttu-id="39573-118">選択**列の編集**コントロールのスマート タグから。</span><span class="sxs-lookup"><span data-stu-id="39573-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2. <span data-ttu-id="39573-119">列を選択、**選択した列**一覧。</span><span class="sxs-lookup"><span data-stu-id="39573-119">Select a column from the **Selected Columns** list.</span></span>  
  
3. <span data-ttu-id="39573-120">をクリックして、**削除**デザイナーから非表示にされ、列を削除するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="39573-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39573-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="39573-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="39573-122">方法: Windows フォーム アプリケーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="39573-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="39573-123">方法: Windows フォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="39573-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
