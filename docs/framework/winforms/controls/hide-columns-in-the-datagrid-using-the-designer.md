---
title: '方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を非表示にする'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 35aa1cdeef919d4267cb27da79f183c4c52aefa2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916387"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="b9709-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を非表示にする</span><span class="sxs-lookup"><span data-stu-id="b9709-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="b9709-103">Windows フォームの <xref:System.Windows.Forms.DataGridView> コントロールで使用できる列の一部のみを表示したいときがあります。</span><span class="sxs-lookup"><span data-stu-id="b9709-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b9709-104">たとえば、管理資格情報を持つユーザーに employee salary 列を表示し、他のユーザーには表示しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9709-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="b9709-105">または、いくつかの列を含むデータソースにコントロールをバインドし、その一部のみを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="b9709-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="b9709-106">この場合、通常は、表示されていない列を非表示にするのではなく、削除します。</span><span class="sxs-lookup"><span data-stu-id="b9709-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="b9709-107">詳細については、「[方法 :デザイナー](add-and-remove-columns-in-the-datagrid-using-the-designer.md)を使用して Windows フォーム DataGridView コントロールの列を追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="b9709-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="b9709-108">次の手順では、 <xref:System.Windows.Forms.DataGridView>コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9709-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b9709-109">このようなプロジェクトの設定の詳細につい[ては、「方法:Windows フォームアプリケーションプロジェクト](/visualstudio/ide/step-1-create-a-windows-forms-application-project)を作成し[、次の操作を行います。Windows フォーム](how-to-add-controls-to-windows-forms.md)にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="b9709-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="b9709-110">デザイナーを使用して列を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="b9709-110">To hide a column using the designer</span></span>

1. <span data-ttu-id="b9709-111"><xref:System.Windows.Forms.DataGridView>コントロールの右上隅にあるスマートタググリフ (![スマートタググリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) をクリックし、 **[列の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9709-111">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="b9709-112">**[選択された列]** ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9709-112">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="b9709-113">列の**プロパティ**グリッドで、 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>プロパティをに`false`設定します。</span><span class="sxs-lookup"><span data-stu-id="b9709-113">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9709-114">**[列の追加]** ダイアログボックスの **[表示]** チェックボックスをオフにすることで、列を追加するときに非表示にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b9709-114">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9709-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9709-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b9709-116">方法: デザイナーを使用した Windows フォーム DataGridView コントロールでの列の追加と削除</span><span class="sxs-lookup"><span data-stu-id="b9709-116">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="b9709-117">方法: Windows フォーム アプリケーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="b9709-117">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="b9709-118">方法: コントロールを Windows フォームに追加する</span><span class="sxs-lookup"><span data-stu-id="b9709-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
