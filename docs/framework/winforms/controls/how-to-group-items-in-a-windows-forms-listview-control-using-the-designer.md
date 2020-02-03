---
title: デザイナーを使用して ListView コントロール内の項目をグループ化する
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 935d8d75517e1028e686ca229f6ada656f58b01e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736685"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="8cf02-102">方法 : デザイナーを使って Windows フォーム ListView コントロールの項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="8cf02-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="8cf02-103"><xref:System.Windows.Forms.ListView> コントロールのグループ化機能を使用すると、関連する項目のセットをグループに表示できます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="8cf02-104">これらのグループは、グループタイトルを含む横方向のグループヘッダーによって画面上で区切られます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="8cf02-105"><xref:System.Windows.Forms.ListView> グループを使用すると、項目をアルファベット順、日付順、または他の論理グループ別にグループ化することで、大きなリストを簡単に移動できます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="8cf02-106">次の図は、グループ化された項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="8cf02-106">The following image shows some grouped items:</span></span>

![奇数と偶数のグループに分割された数値。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="8cf02-108">次の手順では、<xref:System.Windows.Forms.ListView> コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="8cf02-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="8cf02-109">このようなプロジェクトの設定の詳細については、「[方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)する」および「[方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf02-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="8cf02-110">グループ化を有効にするには、最初にデザイナーまたはプログラムを使用して、1つ以上の <xref:System.Windows.Forms.ListViewGroup> オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf02-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="8cf02-111">グループを定義したら、それに項目を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-111">Once a group has been defined, you can assign items to it.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="8cf02-112">デザイナーでグループを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="8cf02-112">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="8cf02-113">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.ListView.Groups%2A>] プロパティの横に**ある省略記号 (省略**記号ボタン ([...]) ボタンをクリックして、[Visual Studio のプロパティウィンドウの](./media/visual-studio-ellipsis-button.png))] ボタンを![ます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-113">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="8cf02-114">**ListViewGroup Collection エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-114">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="8cf02-115">グループを追加するには、 **[追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf02-115">To add a group, click the **Add** button.</span></span> <span data-ttu-id="8cf02-116">その後、新しいグループのプロパティ (<xref:System.Windows.Forms.ListViewGroup.Header%2A> や <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> プロパティなど) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-116">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="8cf02-117">グループを削除するには、グループを選択し、 **[削除]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf02-117">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="8cf02-118">デザイナーで項目をグループに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8cf02-118">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="8cf02-119">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.ListView.Items%2A>] プロパティの横に**ある省略記号 (省略**記号ボタン ([...]) ボタンをクリックして、[Visual Studio のプロパティウィンドウの](./media/visual-studio-ellipsis-button.png))] ボタンを![ます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-119">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="8cf02-120">**ListViewItem Collection エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-120">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="8cf02-121">新しい項目を追加するには、 **[追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cf02-121">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="8cf02-122">その後、<xref:System.Windows.Forms.ListViewItem.Text%2A> や <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> プロパティなど、新しいアイテムのプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8cf02-122">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="8cf02-123">[<xref:System.Windows.Forms.ListViewItem.Group%2A>] プロパティを選択し、ドロップダウンリストからグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf02-123">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cf02-124">参照</span><span class="sxs-lookup"><span data-stu-id="8cf02-124">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="8cf02-125">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="8cf02-125">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="8cf02-126">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="8cf02-126">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="8cf02-127">方法: Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="8cf02-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
