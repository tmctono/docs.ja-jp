---
title: '方法: デザイナーで Windows フォーム ListView コントロールを使って項目を追加および削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 62665746ea9fcd1553717b02b1f1349dc6415ab2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040084"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="91264-102">方法: デザイナーで Windows フォーム ListView コントロールを使って項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="91264-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="91264-103">項目を Windows フォーム<xref:System.Windows.Forms.ListView>コントロールに追加するプロセスは、主に項目を指定し、その項目にプロパティを割り当てることによって構成されます。</span><span class="sxs-lookup"><span data-stu-id="91264-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="91264-104">リスト項目の追加または削除は、いつでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="91264-104">Adding or removing list items can be done at any time.</span></span>

<span data-ttu-id="91264-105">次の手順では、 <xref:System.Windows.Forms.ListView>コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="91264-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="91264-106">このようなプロジェクトの設定の詳細につい[ては、「方法:Windows フォームアプリケーションプロジェクト](/visualstudio/ide/step-1-create-a-windows-forms-application-project)を作成し[、次の操作を行います。Windows フォーム](how-to-add-controls-to-windows-forms.md)にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="91264-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="91264-107">デザイナーを使用して項目を追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="91264-107">To add or remove items using the designer</span></span>

1. <span data-ttu-id="91264-108"><xref:System.Windows.Forms.ListView> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="91264-108">Select the <xref:System.Windows.Forms.ListView> control.</span></span>

2. <span data-ttu-id="91264-109">**[プロパティ]** ウィンドウで、プロパティの横![にある省略記号 (省略記号ボタン ([...])](./media/visual-studio-ellipsis-button.png)をクリックして、 <xref:System.Windows.Forms.ListView.Items%2A>プロパティの横にある [プロパティウィンドウ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="91264-109">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="91264-110">**ListViewItem Collection エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="91264-110">The **ListViewItem Collection Editor** appears.</span></span>

3. <span data-ttu-id="91264-111">項目を追加するには、 **[追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="91264-111">To add an item, click the **Add** button.</span></span> <span data-ttu-id="91264-112">その後、プロパティ<xref:System.Windows.Forms.ListView.Text%2A>や<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>プロパティなど、新しい項目のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="91264-112">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

4. <span data-ttu-id="91264-113">項目を削除するには、項目を選択し、 **[削除]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="91264-113">To remove an item, select it and click the **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="91264-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="91264-114">See also</span></span>

- [<span data-ttu-id="91264-115">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="91264-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="91264-116">方法: Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="91264-116">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="91264-117">方法: Windows フォーム ListView コントロールを使用して列にサブ項目を表示する</span><span class="sxs-lookup"><span data-stu-id="91264-117">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="91264-118">方法: Windows フォーム ListView コントロールのアイコンを表示する</span><span class="sxs-lookup"><span data-stu-id="91264-118">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="91264-119">方法: TreeView コントロールまたは ListView コントロールにカスタム情報を追加する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="91264-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="91264-120">方法: Windows フォーム ListView コントロールの項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="91264-120">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
