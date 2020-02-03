---
title: デザイナーを使用して DataGridView コントロールの列を追加および削除する
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 717a0074f0750352a23b90a9b6e5eab1dc6c925a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732352"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="76cc7-102">方法 : デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="76cc7-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="76cc7-103">データを表示するには、Windows フォーム <xref:System.Windows.Forms.DataGridView> コントロールに列が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76cc7-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="76cc7-104">コントロールを手動で設定する場合は、自分で列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76cc7-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="76cc7-105">または、データソースにコントロールをバインドして、列を自動的に生成して設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="76cc7-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="76cc7-106">表示する列数よりも多くの列がデータソースに含まれている場合は、不要な列を削除できます。</span><span class="sxs-lookup"><span data-stu-id="76cc7-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>

 <span data-ttu-id="76cc7-107">次の手順では、<xref:System.Windows.Forms.DataGridView> コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="76cc7-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="76cc7-108">このようなプロジェクトの設定の詳細については、「[方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)する」および「[方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76cc7-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="76cc7-109">デザイナーを使用して列を追加するには</span><span class="sxs-lookup"><span data-stu-id="76cc7-109">To add a column using the designer</span></span>

1. <span data-ttu-id="76cc7-110"><xref:System.Windows.Forms.DataGridView> コントロールの右上隅にあるスマートタググリフ (![スマートタググリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) をクリックし、 **[列の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="76cc7-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>

2. <span data-ttu-id="76cc7-111">**[列の追加]** ダイアログボックスで、データ **[バインド列]** オプションを選択し、データソースから列を選択するか、 **[非バインド列]** オプションを選択して、提供されたフィールドを使用して列を定義します。</span><span class="sxs-lookup"><span data-stu-id="76cc7-111">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>

3. <span data-ttu-id="76cc7-112">**[追加]** ボタンをクリックして列を追加すると、既存の列がコントロールの表示領域にまだ表示されていない場合に、その列がデザイナーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="76cc7-112">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76cc7-113">**[列の編集]** ダイアログボックスでは、コントロールのスマートタグからアクセスできる列のプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="76cc7-113">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>

## <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="76cc7-114">デザイナーを使用して列を削除するには</span><span class="sxs-lookup"><span data-stu-id="76cc7-114">To remove a column using the designer</span></span>

1. <span data-ttu-id="76cc7-115">コントロールのスマートタグから **[列の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="76cc7-115">Choose **Edit Columns** from the control's smart tag.</span></span>

2. <span data-ttu-id="76cc7-116">**[選択された列]** ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="76cc7-116">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="76cc7-117">列を削除するには、 **[削除]** ボタンをクリックします。これにより、デザイナーに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="76cc7-117">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="76cc7-118">参照</span><span class="sxs-lookup"><span data-stu-id="76cc7-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="76cc7-119">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="76cc7-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="76cc7-120">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="76cc7-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
