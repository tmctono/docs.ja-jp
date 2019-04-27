---
title: '方法: デザイナーを使用して Windows フォーム DataGridView コントロールで行が追加および削除されないようにする'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: 9f78068597edb616017876c9c72b01d44111f6f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902825"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="0d24d-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールで行が追加および削除されないようにする</span><span class="sxs-lookup"><span data-stu-id="0d24d-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="0d24d-103">場合によっては、ユーザーが <xref:System.Windows.Forms.DataGridView> コントロールに新しいデータ行を入力したり、既存の行を削除したりできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d24d-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0d24d-104">コントロールの下部に新しいレコードの特別な行では新しい行を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d24d-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="0d24d-105">行の追加を無効にすると、新しいレコードの行は表示されません。</span><span class="sxs-lookup"><span data-stu-id="0d24d-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="0d24d-106">行うことができますし、コントロール全体は読み取り専用行の削除とセルの編集を無効にするとします。</span><span class="sxs-lookup"><span data-stu-id="0d24d-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>  
  
 <span data-ttu-id="0d24d-107">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0d24d-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0d24d-108">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="0d24d-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d24d-109">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d24d-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0d24d-110">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d24d-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0d24d-111">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d24d-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="0d24d-112">行の追加と削除を防止するには</span><span class="sxs-lookup"><span data-stu-id="0d24d-112">To prevent row addition and deletion</span></span>  
  
-   <span data-ttu-id="0d24d-113">スマート タグ グリフをクリックします (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) の右上隅で、 <xref:System.Windows.Forms.DataGridView> 、制御し、オフ、 **追加を有効にする** **削除を有効にする** チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="0d24d-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d24d-114">コントロールを完全に読み取り専用にするには、オフ、**編集を有効にする** チェック ボックスもします。</span><span class="sxs-lookup"><span data-stu-id="0d24d-114">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d24d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d24d-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0d24d-116">方法: Windows フォーム アプリケーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="0d24d-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="0d24d-117">方法: Windows フォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="0d24d-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
