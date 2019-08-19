---
title: 'チュートリアル: デザイナーを使用した、ListView コントロールと TreeView コントロールを含むエクスプローラー スタイルのインターフェイスの作成'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: 540226dbbada0373854144ac874d2164208ad943
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039923"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="4b2d0-102">チュートリアル: デザイナーを使用した、ListView コントロールと TreeView コントロールを含むエクスプローラー スタイルのインターフェイスの作成</span><span class="sxs-lookup"><span data-stu-id="4b2d0-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="4b2d0-103">Visual Studio の利点の1つは、プロフェッショナルな外観の Windows フォームアプリケーションを短時間で作成できることです。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="4b2d0-104">一般的なシナリオでは、windows オペレーティングシステムの windows エクスプローラー <xref:System.Windows.Forms.ListView>機能<xref:System.Windows.Forms.TreeView>に似たコントロールとコントロールを使用して、ユーザーインターフェイス (UI) を作成します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="4b2d0-105">エクスプローラーには、ユーザーのコンピューター上のファイルとフォルダーの階層構造が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>


### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="4b2d0-106">ListView コントロールと TreeView コントロールを含むフォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="4b2d0-106">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="4b2d0-107">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="4b2d0-108">**[新しいプロジェクト]** ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-108">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="4b2d0-109">[カテゴリ] で、 **[Visual Basic]** または **[ビジュアルC# ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-109">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="4b2d0-110">テンプレートの一覧で、 **[Windows フォームアプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-110">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="4b2d0-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-111">Click **OK**.</span></span> <span data-ttu-id="4b2d0-112">新しい Windows フォームプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-112">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="4b2d0-113">フォームに<xref:System.Windows.Forms.SplitContainer.Dock%2A> <xref:System.Windows.Forms.DockStyle.Fill>コントロールを追加し、そのプロパティをに設定します。 <xref:System.Windows.Forms.SplitContainer></span><span class="sxs-lookup"><span data-stu-id="4b2d0-113">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="4b2d0-114">という名前`imageList1`のをフォームに追加し、プロパティウィンドウを使用して2つのイメージ (フォルダーイメージとドキュメントイメージ) をこの順序で追加します。 <xref:System.Windows.Forms.ImageList></span><span class="sxs-lookup"><span data-stu-id="4b2d0-114">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="4b2d0-115">という<xref:System.Windows.Forms.TreeView>名前`treeview1`のコントロールをフォームに追加し、 <xref:System.Windows.Forms.SplitContainer>コントロールの左側に配置します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-115">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="4b2d0-116">の`treeView1`プロパティウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-116">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="4b2d0-117"><xref:System.Windows.Forms.Control.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill>に設定します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-117">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="4b2d0-118">  <xref:System.Windows.Forms.TreeView.ImageList%2A> プロパティを `imagelist1.` に設定します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-118">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="4b2d0-119">という<xref:System.Windows.Forms.ListView>名前`listView1`のコントロールをフォームに追加し、 <xref:System.Windows.Forms.SplitContainer>コントロールの右側に配置します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-119">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="4b2d0-120">の`listview1`プロパティウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-120">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="4b2d0-121"><xref:System.Windows.Forms.Control.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill>に設定します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-121">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="4b2d0-122"><xref:System.Windows.Forms.ListView.View%2A> プロパティを <xref:System.Windows.Forms.View.Details> に設定します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-122">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="4b2d0-123">[![ ] <xref:System.Windows.Forms.ListView.Columns%2A>プロパティの省略記号 (省略記号ボタン ([...] プロパティウィンドウ](./media/visual-studio-ellipsis-button.png)) をクリックして、columnheader コレクションエディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-123">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="4b2d0-124">3つの列を追加<xref:System.Windows.Forms.ColumnHeader.Text%2A>し、それぞれ`Type`のプロパティ`Last Modified`を、、およびに`Name`それぞれ設定します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-124">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="4b2d0-125">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-125">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="4b2d0-126">  <xref:System.Windows.Forms.ListView.SmallImageList%2A> プロパティを `imageList1.` に設定します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-126">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="4b2d0-127">ノードとサブノードを<xref:System.Windows.Forms.TreeView>に設定するコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-127">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="4b2d0-128">  `Form1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-128">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="4b2d0-129">前のコードでは System.IO 名前空間を使用しているため、フォームの先頭に適切な using ステートメントまたは import ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-129">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="4b2d0-130">フォームのコンストラクターまたは<xref:System.Windows.Forms.Form.Load>イベント処理メソッドで、前の手順の設定メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-130">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="4b2d0-131">このコードをフォームコンストラクターに追加します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-131">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="4b2d0-132"><xref:System.Windows.Forms.TreeView.NodeMouseClick>の `listview1`イベントを処理し、ノードがクリックされたときにノードの内容を設定するコードを実装します。 `treeview1`</span><span class="sxs-lookup"><span data-stu-id="4b2d0-132">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="4b2d0-133">  `Form1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-133">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="4b2d0-134">を使用C#している場合は、イベント処理<xref:System.Windows.Forms.TreeView.NodeMouseClick>メソッドにイベントが関連付けられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-134">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="4b2d0-135">このコードをフォームコンストラクターに追加します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-135">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="4b2d0-136">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="4b2d0-136">Testing the Application</span></span>

<span data-ttu-id="4b2d0-137">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-137">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="4b2d0-138">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="4b2d0-138">To test the form</span></span>

- <span data-ttu-id="4b2d0-139">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-139">Press F5 to run the application.</span></span>

     <span data-ttu-id="4b2d0-140">左側にプロジェクトディレクトリを表示する<xref:System.Windows.Forms.TreeView>コントロール<xref:System.Windows.Forms.ListView>と、右側に3つの列があるコントロールを含む分割フォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-140">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="4b2d0-141">を走査<xref:System.Windows.Forms.TreeView>するには、ディレクトリノードを選択し<xref:System.Windows.Forms.ListView>ます。には、選択したディレクトリの内容が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-141">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4b2d0-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="4b2d0-142">Next Steps</span></span>

<span data-ttu-id="4b2d0-143">このアプリケーションでは、を使用<xref:System.Windows.Forms.TreeView>して制御する方法の例を示して<xref:System.Windows.Forms.ListView>います。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-143">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="4b2d0-144">これらのコントロールの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b2d0-144">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="4b2d0-145">方法: TreeView コントロールまたは ListView コントロールにカスタム情報を追加する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="4b2d0-145">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="4b2d0-146">方法: ListView コントロールに検索機能を追加する</span><span class="sxs-lookup"><span data-stu-id="4b2d0-146">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="4b2d0-147">方法: ショートカットメニューを TreeView ノードにアタッチする</span><span class="sxs-lookup"><span data-stu-id="4b2d0-147">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="4b2d0-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b2d0-148">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="4b2d0-149">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="4b2d0-149">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="4b2d0-150">方法: Windows フォーム TreeView コントロールを使用してノードを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="4b2d0-150">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="4b2d0-151">方法: Windows フォーム ListView コントロールを使用して項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="4b2d0-151">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="4b2d0-152">方法: Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="4b2d0-152">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
