---
title: デザイナーを使用して DataGridView 列の型を変更する
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 470f350a4791a3db39d08ab7992d86eb7b2e270a
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628619"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="a5100-102">方法 : デザイナーを使用して Windows フォーム DataGridView 列の種類を変更する</span><span class="sxs-lookup"><span data-stu-id="a5100-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="a5100-103">Windows フォーム <xref:System.Windows.Forms.DataGridView> コントロールに既に追加されている列の型を変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5100-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a5100-104">たとえば、データソースにコントロールをバインドするときに自動的に生成されるいくつかの列の型を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a5100-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="a5100-105">これは、表示するテーブルに、関連テーブル内の行に対する外部キーを含む列がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a5100-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="a5100-106">この場合は、これらの外部キーを表示するテキストボックスの列を、関連するテーブルの意味のある値を表示するコンボボックスの列に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="a5100-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>

 <span data-ttu-id="a5100-107">次の手順では、<xref:System.Windows.Forms.DataGridView> コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="a5100-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a5100-108">このようなプロジェクトの設定の詳細については、「[方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)する」および「[方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5100-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="a5100-109">デザイナーを使用して列の型を変更するには</span><span class="sxs-lookup"><span data-stu-id="a5100-109">To change the type of a column using the designer</span></span>

1. <span data-ttu-id="a5100-110"><xref:System.Windows.Forms.DataGridView> コントロールの右上隅にある [デザイナーアクション] グリフ (![小さい黒い矢印](./media/designer-actions-glyph.gif)) をクリックし、[列の**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5100-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="a5100-111">**[選択された列]** ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5100-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="a5100-112">列の**プロパティ**グリッドで、[`ColumnType`] プロパティを新しい列の種類に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5100-112">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a5100-113">`ColumnType` プロパティは、列の型を表すクラスを示すデザイン時専用のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a5100-113">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="a5100-114">これは、列クラスで定義された実際のプロパティではありません。</span><span class="sxs-lookup"><span data-stu-id="a5100-114">It is not an actual property defined in a column class.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5100-115">参照</span><span class="sxs-lookup"><span data-stu-id="a5100-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="a5100-116">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a5100-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="a5100-117">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="a5100-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
