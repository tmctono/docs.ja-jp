---
title: '方法: TableLayoutPanel コントロールの列と行を編集する'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 99ff3286592da0a097835b8f35d687475ca54fb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040297"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="65447-102">方法: TableLayoutPanel コントロールの列と行を編集する</span><span class="sxs-lookup"><span data-stu-id="65447-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>

<span data-ttu-id="65447-103">**[列と行のスタイル]** ダイアログ<xref:System.Windows.Forms.TableLayoutPanel>ボックスと呼ばれるコントロールのコレクションエディターを使用して、コントロールの行と列を編集できます。</span><span class="sxs-lookup"><span data-stu-id="65447-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>

> [!NOTE]
> <span data-ttu-id="65447-104">コントロールが複数の行または列にまたがるようにするに`RowSpan`は`ColumnSpan` 、コントロールのプロパティとプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="65447-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="65447-105">詳細については、「[チュートリアル:TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)を使用して Windows フォームのコントロールを配置する。</span><span class="sxs-lookup"><span data-stu-id="65447-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>
>
> <span data-ttu-id="65447-106">セル内にコントロールを配置する場合、またはコントロールをセル内に引き伸ばす場合は、コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="65447-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="65447-107">詳細については、「[チュートリアル:TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)を使用して Windows フォームのコントロールを配置する。</span><span class="sxs-lookup"><span data-stu-id="65447-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>

## <a name="to-edit-rows-and-columns"></a><span data-ttu-id="65447-108">行と列を編集するには</span><span class="sxs-lookup"><span data-stu-id="65447-108">To edit rows and columns</span></span>

1. <span data-ttu-id="65447-109"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="65447-109">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="65447-110">![](./media/vs-winformsmttagglyph.gif "")コントロールのスマートタググリフ (スマートタググリフ VS_WinFormSmtTagGlyph) をクリックし、[行と列の編集] を選択して [列と行のスタイル] ダイアログボックスを開きます。 <xref:System.Windows.Forms.TableLayoutPanel></span><span class="sxs-lookup"><span data-stu-id="65447-110">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="65447-111">また、 <xref:System.Windows.Forms.TableLayoutPanel>コントロールを右クリックし、ショートカットメニューの **[行と列の編集]** をクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="65447-111">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>

3. <span data-ttu-id="65447-112">列を追加または削除するには、 **[メンバーの種類]** ボックスの一覧から**列**を選択します。</span><span class="sxs-lookup"><span data-stu-id="65447-112">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>

4. <span data-ttu-id="65447-113">行を追加または削除するには、 **[メンバーの種類]** ボックスの一覧から **[行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="65447-113">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>

5. <span data-ttu-id="65447-114">**メンバー**リストの末尾に行または列を追加するには、 **[追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="65447-114">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>

6. <span data-ttu-id="65447-115">一覧で現在選択されている項目の前に行または列を追加するには、 **[挿入]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="65447-115">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>

7. <span data-ttu-id="65447-116">行または列を追加する場合は、新しい行または列の**サイズの種類**を選択します。</span><span class="sxs-lookup"><span data-stu-id="65447-116">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="65447-117">詳細については、「 <xref:System.Windows.Forms.SizeType> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65447-117">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>

8. <span data-ttu-id="65447-118">行または列を削除するには、 **[削除]** ボタンをクリックして、**メンバー**リストで現在選択されているアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="65447-118">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>

## <a name="see-also"></a><span data-ttu-id="65447-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="65447-119">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="65447-120">TableLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="65447-120">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
