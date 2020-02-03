---
title: デザイナーを使用して DataGridView コントロールで列を読み取り専用にする
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 51d9488ef83f7d2c1c01c9ffd756edf8944d738d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744978"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="bb34e-102">方法 : デザイナーを使用して Windows フォームの DataGridView コントロールで列を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="bb34e-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="bb34e-103">既定では、ユーザーは Windows フォーム <xref:System.Windows.Forms.DataGridView> コントロールに表示されるテキストおよび数値データを変更できます。</span><span class="sxs-lookup"><span data-stu-id="bb34e-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bb34e-104">変更を意図していないデータを表示する場合は、データを含む列を読み取り専用にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb34e-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="bb34e-105">コントロールを完全に読み取り専用にする方法については、「[方法: デザイナーを使用して Windows フォーム DataGridView コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb34e-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="bb34e-106">次の手順では、<xref:System.Windows.Forms.DataGridView> コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="bb34e-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bb34e-107">このようなプロジェクトの設定の詳細については、「[方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)する」および「[方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb34e-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="bb34e-108">デザイナーを使用して列を読み取り専用にするには</span><span class="sxs-lookup"><span data-stu-id="bb34e-108">To make a column read-only by using the designer</span></span>

1. <span data-ttu-id="bb34e-109"><xref:System.Windows.Forms.DataGridView> コントロールの右上隅にあるスマートタググリフ (![スマートタググリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) をクリックし、 **[列の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb34e-109">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="bb34e-110">**[選択された列]** ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb34e-110">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="bb34e-111">列の**プロパティ**グリッドで、[<xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>] プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="bb34e-111">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb34e-112">また、 **[列の追加]** ダイアログボックスの **[読み取り専用]** チェックボックスをオンにすると、列を追加するときに読み取り専用にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bb34e-112">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb34e-113">参照</span><span class="sxs-lookup"><span data-stu-id="bb34e-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bb34e-114">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="bb34e-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="bb34e-115">方法: デザイナーを使用して Windows フォーム DataGridView コントロールで行が追加および削除されないようにする</span><span class="sxs-lookup"><span data-stu-id="bb34e-115">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="bb34e-116">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="bb34e-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="bb34e-117">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="bb34e-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
