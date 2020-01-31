---
title: デザイナーを使用して DataGridView コントロールの列の順序を変更する
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: be4f67ca6530b74fc90cb50a10463b2378edb933
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743156"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="a3d72-102">方法 : デザイナーを使用して Windows フォーム DataGridView コントロールの列の順序を変更する</span><span class="sxs-lookup"><span data-stu-id="a3d72-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="a3d72-103">Windows フォーム <xref:System.Windows.Forms.DataGridView> コントロールをデータソースにバインドすると、自動的に生成された列の表示順序はデータソースによって決まります。</span><span class="sxs-lookup"><span data-stu-id="a3d72-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="a3d72-104">この順序が希望どおりでない場合は、デザイナーを使用して列の順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a3d72-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="a3d72-105">コントロールに非バインド列を追加して、表示順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3d72-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="a3d72-106">プログラムによって列の順序を変更する方法の詳細については、「[方法: Windows フォーム DataGridView コントロールの列の順序を変更](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3d72-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="a3d72-107">次の手順では、<xref:System.Windows.Forms.DataGridView> コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="a3d72-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a3d72-108">このようなプロジェクトの設定の詳細については、「[方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)する」および「[方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3d72-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="a3d72-109">デザイナーを使用して列の順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="a3d72-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="a3d72-110"><xref:System.Windows.Forms.DataGridView> コントロールの右上隅にあるスマートタググリフ (![スマートタググリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) をクリックし、 **[列の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3d72-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="a3d72-111">**[選択された列]** ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3d72-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="a3d72-112">[**選択さ**れた列] の一覧の右側にある上矢印または下矢印をクリックすると、選択した列が目的の位置に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3d72-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3d72-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3d72-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="a3d72-114">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="a3d72-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="a3d72-115">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a3d72-115">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="a3d72-116">方法 : Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="a3d72-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
