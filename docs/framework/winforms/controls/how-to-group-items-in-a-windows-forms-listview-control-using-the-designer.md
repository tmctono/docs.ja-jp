---
title: '方法: デザイナーを使って Windows フォーム ListView コントロールの項目をグループ化する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: b63bcd9e5e357db350cc2987e09af84eb58bdcff
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "69039399"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="9cca5-102">方法: デザイナーを使って Windows フォーム ListView コントロールの項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="9cca5-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="9cca5-103"><xref:System.Windows.Forms.ListView>コントロールのグループ化機能を使用すると、関連する項目のセットをグループに表示できます。</span><span class="sxs-lookup"><span data-stu-id="9cca5-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="9cca5-104">これらのグループは、グループタイトルを含む横方向のグループヘッダーによって画面上で区切られます。</span><span class="sxs-lookup"><span data-stu-id="9cca5-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="9cca5-105">グループを使用<xref:System.Windows.Forms.ListView>すると、項目をアルファベット順、日付形式、またはその他の論理グループ別にグループ化することで、大きなリストを簡単に移動できます。</span><span class="sxs-lookup"><span data-stu-id="9cca5-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="9cca5-106">次の図は、グループ化された項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="9cca5-106">The following image shows some grouped items:</span></span>

![奇数と偶数のグループに分割された数値。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="9cca5-108">次の手順では、 <xref:System.Windows.Forms.ListView>コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="9cca5-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="9cca5-109">このようなプロジェクトの設定の詳細につい[ては、「方法:Windows フォームアプリケーションプロジェクト](/visualstudio/ide/step-1-create-a-windows-forms-application-project)を作成し[、次の操作を行います。Windows フォーム](how-to-add-controls-to-windows-forms.md)にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cca5-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="9cca5-110">グループ化を有効にするには、最初に<xref:System.Windows.Forms.ListViewGroup>デザイナーまたはプログラムを使用して、1つ以上のオブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cca5-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="9cca5-111">グループを定義したら、それに項目を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9cca5-111">Once a group has been defined, you can assign items to it.</span></span>

> [!NOTE]
> <span data-ttu-id="9cca5-112"><xref:System.Windows.Forms.ListView>グループは、アプリケーションが[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]メソッドを<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>呼び出したときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9cca5-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9cca5-113">以前のオペレーティングシステムでは、グループに関連するすべてのコードは効果がなく、グループは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9cca5-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="9cca5-114">詳細については、「 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cca5-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="9cca5-115">デザイナーでグループを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="9cca5-115">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="9cca5-116">**[プロパティ]** ウィンドウで、プロパティの横![に**ある省略記号 (省略**記号ボタン ([...])](./media/visual-studio-ellipsis-button.png)をクリックして、 <xref:System.Windows.Forms.ListView.Groups%2A>プロパティの横にある [プロパティウィンドウ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cca5-116">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="9cca5-117">**ListViewGroup Collection エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cca5-117">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="9cca5-118">グループを追加するには、 **[追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cca5-118">To add a group, click the **Add** button.</span></span> <span data-ttu-id="9cca5-119">その後、プロパティ<xref:System.Windows.Forms.ListViewGroup.Header%2A>や<xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>プロパティなど、新しいグループのプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="9cca5-119">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="9cca5-120">グループを削除するには、グループを選択し、 **[削除]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cca5-120">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="9cca5-121">デザイナーで項目をグループに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="9cca5-121">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="9cca5-122">**[プロパティ]** ウィンドウで、プロパティの横![に**ある省略記号 (省略**記号ボタン ([...])](./media/visual-studio-ellipsis-button.png)をクリックして、 <xref:System.Windows.Forms.ListView.Items%2A>プロパティの横にある [プロパティウィンドウ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cca5-122">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="9cca5-123">**ListViewItem Collection エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cca5-123">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="9cca5-124">新しい項目を追加するには、 **[追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cca5-124">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="9cca5-125">その後、プロパティ<xref:System.Windows.Forms.ListViewItem.Text%2A>や<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>プロパティなど、新しい項目のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="9cca5-125">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="9cca5-126"><xref:System.Windows.Forms.ListViewItem.Group%2A>プロパティを選択し、ドロップダウンリストからグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="9cca5-126">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cca5-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cca5-127">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="9cca5-128">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="9cca5-128">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="9cca5-129">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="9cca5-129">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="9cca5-130">方法: Windows フォーム ListView コントロールを使用して項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="9cca5-130">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
