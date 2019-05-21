---
title: '方法: デザイナーを使って Windows フォーム ListView コントロールの項目をグループ化する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 9249eef281237f61d103a7c865042aafe537dea5
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960219"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="a509e-102">方法: デザイナーを使って Windows フォーム ListView コントロールの項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="a509e-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="a509e-103">グループ化機能、<xref:System.Windows.Forms.ListView>コントロールでは、グループ内のアイテムの関連する設定を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="a509e-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="a509e-104">これらのグループは、画面に含まれるグループのタイトルは水平方向のグループ ヘッダーで区切られます。</span><span class="sxs-lookup"><span data-stu-id="a509e-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="a509e-105">使用することができます<xref:System.Windows.Forms.ListView>グループ日付、または他の論理グループで、アルファベット順に項目をグループ化して簡単に大きい一覧を移動します。</span><span class="sxs-lookup"><span data-stu-id="a509e-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="a509e-106">次の図は、いくつかのグループ化された項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="a509e-106">The following image shows some grouped items:</span></span>

![数値が奇数/偶数のグループに区切られます。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="a509e-108">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a509e-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="a509e-109">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="a509e-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="a509e-110">グループ化を有効にする必要があります最初に作成する 1 つまたは複数<xref:System.Windows.Forms.ListViewGroup>オブジェクトがデザイナーで、またはプログラムを使用します。</span><span class="sxs-lookup"><span data-stu-id="a509e-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="a509e-111">グループを定義した後に項目を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a509e-111">Once a group has been defined, you can assign items to it.</span></span>

> [!NOTE]
> <span data-ttu-id="a509e-112"><xref:System.Windows.Forms.ListView> のみ使用可能なグループ[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]、アプリケーションを呼び出すと、<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="a509e-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a509e-113">以前のオペレーティング システムでは、グループに関するすべてのコードが影響を与えません、グループは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a509e-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="a509e-114">詳細については、「 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a509e-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>
>
> <span data-ttu-id="a509e-115">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a509e-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a509e-116">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a509e-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a509e-117">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a509e-117">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="a509e-118">追加またはデザイナーでグループを削除するには</span><span class="sxs-lookup"><span data-stu-id="a509e-118">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="a509e-119">**プロパティ**ウィンドウで、をクリックして、**省略記号**(![. Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png)) ボタンの横に、<xref:System.Windows.Forms.ListView.Groups%2A>プロパティ.</span><span class="sxs-lookup"><span data-stu-id="a509e-119">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="a509e-120">**ListViewGroup コレクション エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a509e-120">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="a509e-121">グループを追加する をクリックして、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a509e-121">To add a group, click the **Add** button.</span></span> <span data-ttu-id="a509e-122">など、新しいグループのプロパティを設定することができますし、<xref:System.Windows.Forms.ListViewGroup.Header%2A>と<xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a509e-122">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="a509e-123">グループを削除するを選択し、クリックして、**削除**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a509e-123">To remove a group, select it and click the **Remove** button.</span></span>

### <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="a509e-124">デザイナーでのグループに項目を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a509e-124">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="a509e-125">**プロパティ**ウィンドウで、をクリックして、**省略記号**(![. Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png)) ボタンの横に、<xref:System.Windows.Forms.ListView.Items%2A>プロパティ.</span><span class="sxs-lookup"><span data-stu-id="a509e-125">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="a509e-126">**ListViewItem コレクション エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a509e-126">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="a509e-127">新しいアイテムを追加する をクリックして、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a509e-127">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="a509e-128">など、新しい項目のプロパティを設定することができますし、<xref:System.Windows.Forms.ListViewItem.Text%2A>と<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a509e-128">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="a509e-129">選択、<xref:System.Windows.Forms.ListViewItem.Group%2A>プロパティ ドロップダウン リストからグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a509e-129">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="a509e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="a509e-130">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="a509e-131">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="a509e-131">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="a509e-132">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a509e-132">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="a509e-133">方法: Windows フォーム ListView コントロールで項目追加および削除</span><span class="sxs-lookup"><span data-stu-id="a509e-133">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
