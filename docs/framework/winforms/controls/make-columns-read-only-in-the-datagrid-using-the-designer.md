---
title: '方法: デザイナーを使用して Windows フォームの DataGridView コントロールで列を読み取り専用にする'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 8639c1e6f4382c1f91ed2c777b1b0ff29c5a60a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113517"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="ef496-102">方法: デザイナーを使用して Windows フォームの DataGridView コントロールで列を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="ef496-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="ef496-103">ユーザーが既定では、テキストと Windows フォームに表示される数値のデータ変更できる<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="ef496-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ef496-104">変更できないデータを表示する場合は、読み取り専用データを含む列を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef496-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="ef496-105">完全に読み取り専用コントロールを作成する方法については、次を参照してください。[方法。行の追加を回避し、削除を Windows フォーム DataGridView コントロールのデザイナーを使用して](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="ef496-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="ef496-106">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="ef496-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ef496-107">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="ef496-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef496-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef496-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ef496-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef496-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ef496-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef496-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="ef496-111">デザイナーを使用して、列を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="ef496-111">To make a column read-only by using the designer</span></span>  
  
1.  <span data-ttu-id="ef496-112">スマート タグ グリフをクリックします (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) の右上隅で、 <xref:System.Windows.Forms.DataGridView> 、制御し、**列の編集**します。</span><span class="sxs-lookup"><span data-stu-id="ef496-112">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="ef496-113">列を選択、**選択した列**一覧。</span><span class="sxs-lookup"><span data-stu-id="ef496-113">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="ef496-114">**列プロパティ**グリッドで、設定、<xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="ef496-114">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef496-115">行うことができますも列を読み取り専用を選択して追加すると、**読み取り専用** チェック ボックス、**列の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ef496-115">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef496-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef496-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ef496-117">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="ef496-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="ef496-118">方法: デザイナーを使用して Windows フォーム DataGridView コントロールで行が追加および削除されないようにする</span><span class="sxs-lookup"><span data-stu-id="ef496-118">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="ef496-119">方法: Windows フォーム アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ef496-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="ef496-120">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="ef496-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
