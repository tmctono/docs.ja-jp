---
title: '方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を固定する'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: 7ebdf7a1598ac3cd61005ae607e5bfbe7cb49059
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933713"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="ee174-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を固定する</span><span class="sxs-lookup"><span data-stu-id="ee174-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="ee174-103">ユーザーが Windows フォームの <xref:System.Windows.Forms.DataGridView> コントロールに表示されるデータを確認するときに、1 つの列または列のセットを頻繁に参照しなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="ee174-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="ee174-104">たとえば、多数の列が含まれている顧客情報のテーブルを表示する場合、他の列を表示可能な領域の外側にスクロールできるようにしながら、常に顧客名を表示すると便利です。</span><span class="sxs-lookup"><span data-stu-id="ee174-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>

 <span data-ttu-id="ee174-105">この動作を実現するために、コントロールの列を固定することができます。</span><span class="sxs-lookup"><span data-stu-id="ee174-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="ee174-106">列を固定すると、左側 (右から左へ記述する言語のスクリプトでは右側) のすべての列も同様に固定されます。</span><span class="sxs-lookup"><span data-stu-id="ee174-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="ee174-107">固定された列は表示されたままになり、その他のすべての列はスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="ee174-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="ee174-108">列の並べ替えが有効な場合、固定された列は、固定されていない列とは異なるグループとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="ee174-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="ee174-109">ユーザーは、どちらかのグループに列を再配置できますが、1 つのグループから別のグループに列を移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="ee174-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>

 <span data-ttu-id="ee174-110">次の手順では、 <xref:System.Windows.Forms.DataGridView>コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="ee174-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ee174-111">このようなプロジェクトの設定の詳細につい[ては、「方法:Windows フォームアプリケーションプロジェクト](/visualstudio/ide/step-1-create-a-windows-forms-application-project)を作成し[、次の操作を行います。Windows フォーム](how-to-add-controls-to-windows-forms.md)にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="ee174-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="ee174-112">デザイナーを使用して列を固定するには</span><span class="sxs-lookup"><span data-stu-id="ee174-112">To freeze a column using the designer</span></span>

1. <span data-ttu-id="ee174-113"><xref:System.Windows.Forms.DataGridView>コントロールの右上隅にあるスマートタググリフ (![スマートタググリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) をクリックし、 **[列の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee174-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="ee174-114">**[選択された列]** ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee174-114">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="ee174-115">列の**プロパティ**グリッドで、 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A>プロパティをに`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="ee174-115">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee174-116">**[列の追加]** ダイアログボックスで**固定**されたボックスを選択して、列を追加するときに固定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee174-116">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee174-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee174-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ee174-118">方法: デザイナーを使用した Windows フォーム DataGridView コントロールでの列の追加と削除</span><span class="sxs-lookup"><span data-stu-id="ee174-118">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="ee174-119">方法: デザイナーを使用して Windows フォーム DataGridView コントロールで列の並べ替えを有効にする</span><span class="sxs-lookup"><span data-stu-id="ee174-119">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="ee174-120">[方法: グローバリゼーション用に Windows フォームに右から左に記述するテキストを表示する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ee174-120">[How to: Display Right-to-Left Text in Windows Forms for Globalization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span></span>
- [<span data-ttu-id="ee174-121">方法: Windows フォーム アプリケーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="ee174-121">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="ee174-122">方法: コントロールを Windows フォームに追加する</span><span class="sxs-lookup"><span data-stu-id="ee174-122">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
