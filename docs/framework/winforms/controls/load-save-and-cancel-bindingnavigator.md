---
title: BindingNavigator コントロールに [Load]、[Save]、[Cancel] の各ボタンを追加する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: ac862d163f1bd8b66f29160d836bc459e4bf4081
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745128"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="84df2-102">方法 : Windows フォーム BindingNavigator コントロールに [Load]、[Save]、[Cancel] の各ボタンを追加する</span><span class="sxs-lookup"><span data-stu-id="84df2-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="84df2-103"><xref:System.Windows.Forms.BindingNavigator> コントロールは、データにバインドされているフォーム上のコントロールの移動や操作を目的とした特殊な用途の <xref:System.Windows.Forms.ToolStrip> コントロールです。</span><span class="sxs-lookup"><span data-stu-id="84df2-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="84df2-104">これは <xref:System.Windows.Forms.ToolStrip> コントロールであるため、<xref:System.Windows.Forms.BindingNavigator> コンポーネントを簡単に変更して、ユーザーの追加または代替コマンドを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="84df2-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="84df2-105">次の手順では、<xref:System.Windows.Forms.TextBox> コントロールがデータにバインドされ、フォームに追加された <xref:System.Windows.Forms.ToolStrip> コントロールが、[読み込み]、[保存]、および [キャンセル] の各ボタンを含むように変更されます。</span><span class="sxs-lookup"><span data-stu-id="84df2-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="84df2-106">[Load]、[save]、[cancel] の各ボタンを BindingNavigator コンポーネントに追加します。</span><span class="sxs-lookup"><span data-stu-id="84df2-106">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="84df2-107">Visual Studio で、フォームに <xref:System.Windows.Forms.TextBox> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="84df2-107">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="84df2-108">データソースにバインドされている <xref:System.Windows.Forms.BindingSource>にバインドします。</span><span class="sxs-lookup"><span data-stu-id="84df2-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="84df2-109">この例では、<xref:System.Windows.Forms.BindingSource> はデータベースにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="84df2-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="84df2-110">データセットとテーブルアダプターが生成されたら、<xref:System.Windows.Forms.BindingNavigator> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="84df2-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="84df2-111">コントロールにバインドされているフォームの <xref:System.Windows.Forms.BindingSource> に <xref:System.Windows.Forms.BindingNavigator> コントロールの <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="84df2-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="84df2-112"><xref:System.Windows.Forms.BindingNavigator> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="84df2-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="84df2-113">**[BindingNavigator タスク]** ダイアログボックスが表示されるように、スマートタググリフ (![スマートタググリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) をクリックし、 **[アイテムの編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84df2-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="84df2-114">**項目コレクションエディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="84df2-114">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="84df2-115">**Items コレクションエディター**で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="84df2-115">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="84df2-116">適切な種類の <xref:System.Windows.Forms.ToolStripItem> を選択し、 **[追加]** ボタンをクリックして、<xref:System.Windows.Forms.ToolStripSeparator> と3つの <xref:System.Windows.Forms.ToolStripButton> 項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="84df2-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="84df2-117">ボタンの <xref:System.Windows.Forms.ToolStripItem.Name%2A> プロパティを**Loadbutton**、 **savebutton**、および**cancelbutton**にそれぞれ設定します。</span><span class="sxs-lookup"><span data-stu-id="84df2-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="84df2-118">**[読み込み]** 、 **[保存]** 、 **[キャンセル]** の各ボタンの <xref:System.Windows.Forms.ToolStripItem.Text%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="84df2-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="84df2-119">各ボタンの [<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>] プロパティを **[テキスト]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="84df2-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="84df2-120">または、このプロパティを**image**または**imageandtext**に設定し、<xref:System.Windows.Forms.ToolStripItem.Image%2A> プロパティに表示されるようにイメージを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="84df2-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="84df2-121">[OK ] をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="84df2-121">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="84df2-122">ボタンが <xref:System.Windows.Forms.ToolStrip>に追加されます。</span><span class="sxs-lookup"><span data-stu-id="84df2-122">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="84df2-123">フォームを右クリックし、 **[コードの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84df2-123">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="84df2-124">コードエディターで、テーブルアダプターにデータを読み込むコード行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="84df2-124">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="84df2-125">このコードは、手順 2. でデータバインディングを設定したときに生成されました。</span><span class="sxs-lookup"><span data-stu-id="84df2-125">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="84df2-126">コードは次のようになります。 `TableAdapterName.Fill(DataSetName.TableName)`。</span><span class="sxs-lookup"><span data-stu-id="84df2-126">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="84df2-127">通常、フォームの <xref:System.Windows.Forms.Form.Load> イベントに含まれます。</span><span class="sxs-lookup"><span data-stu-id="84df2-127">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="84df2-128">前に作成した**読み込み**<xref:System.Windows.Forms.ToolStripButton> の <xref:System.Windows.Forms.ToolStripItem.Click> イベントのイベントハンドラーを作成し、このデータ読み込みコードをそこに移動します。</span><span class="sxs-lookup"><span data-stu-id="84df2-128">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="84df2-129">これで、コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84df2-129">Your code should now look similar to the following:</span></span>

    ```vb
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click
        TableAdapterName.Fill(DataSetName.TableName)
    End Sub
    ```

    ```csharp
    private void LoadButton_Click(System.Object sender,
        System.EventArgs e)
    {
        TableAdapterName.Fill(DataSetName.TableName);
    }
    ```

11. <span data-ttu-id="84df2-130">前に作成した**保存**<xref:System.Windows.Forms.ToolStripButton> の <xref:System.Windows.Forms.ToolStripItem.Click> イベントのイベントハンドラーを作成し、コントロールがバインドされているテーブル内のデータを更新するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="84df2-130">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

    ```vb
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click
        TableAdapterName.Update(DataSetName.TableName)
    End Sub
    ```

    ```csharp
    private void SaveButton_Click(System.Object sender,
        System.EventArgs e)
    {
        TableAdapterName.Update(DataSetName.TableName);
    }
    ```

    > [!NOTE]
    > <span data-ttu-id="84df2-131"><xref:System.Windows.Forms.BindingNavigator> コンポーネントには既に **[保存]** ボタンがありますが、Windows フォームデザイナーによってコードが生成されていない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="84df2-131">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="84df2-132">この場合、<xref:System.Windows.Forms.ToolStrip>にまったく新しいボタンを作成するのではなく、そのボタンの <xref:System.Windows.Forms.ToolStripItem.Click> イベントハンドラーに上記のコードを配置できます。</span><span class="sxs-lookup"><span data-stu-id="84df2-132">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="84df2-133">ただし、ボタンは既定では無効になっているため、ボタンが正しく機能するようにするには、ボタンの <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> プロパティを `true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84df2-133">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="84df2-134">前に作成した**cancel** <xref:System.Windows.Forms.ToolStripButton> の <xref:System.Windows.Forms.ToolStripItem.Click> イベントのイベントハンドラーを作成し、表示されるデータレコードへの変更を取り消すコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="84df2-134">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

    ```vb
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click
        BindingSourceName.CancelEdit()
    End Sub
    ```

    ```csharp
    private void CancelButton_Click(System.Object sender, System.EventArgs e)
    {
        BindingSourceName.CancelEdit();
    }
    ```

    > [!NOTE]
    > <span data-ttu-id="84df2-135"><xref:System.Windows.Forms.BindingSource.CancelEdit%2A> メソッドは、データの行にスコープが設定されています。</span><span class="sxs-lookup"><span data-stu-id="84df2-135">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="84df2-136">次のレコードに移動する前に、個々のレコードを表示しているときに行ったすべての変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="84df2-136">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="84df2-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="84df2-137">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="84df2-138">BindingNavigator コントロール</span><span class="sxs-lookup"><span data-stu-id="84df2-138">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="84df2-139">BindingSource コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="84df2-139">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
