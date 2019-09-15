---
title: '方法: Windows フォーム BindingNavigator コントロールに [Load]、[Save]、[Cancel] の各ボタンを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 2d4867c0bc4feb7b43e15614fc56a3c709cef9e7
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991736"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="b6f78-102">方法: Windows フォーム BindingNavigator コントロールに [Load]、[Save]、[Cancel] の各ボタンを追加する</span><span class="sxs-lookup"><span data-stu-id="b6f78-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="b6f78-103">コントロールは、データにバインドさ<xref:System.Windows.Forms.ToolStrip>れているフォーム上のコントロールを移動および操作するための特殊な用途のコントロールです。 <xref:System.Windows.Forms.BindingNavigator></span><span class="sxs-lookup"><span data-stu-id="b6f78-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="b6f78-104">コントロールであるため、コンポーネントを簡単に変更して、ユーザーの追加または別のコマンドを含めることができます。<xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.BindingNavigator></span><span class="sxs-lookup"><span data-stu-id="b6f78-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="b6f78-105">次の手順<xref:System.Windows.Forms.TextBox>では、コントロールがデータ<xref:System.Windows.Forms.ToolStrip>にバインドされ、フォームに追加されたコントロールが、[読み込み]、[保存]、および [キャンセル] の各ボタンを含むように変更されます。</span><span class="sxs-lookup"><span data-stu-id="b6f78-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="b6f78-106">[Load]、[save]、[cancel] の各ボタンを BindingNavigator コンポーネントに追加します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-106">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="b6f78-107">Visual Studio で、フォームに<xref:System.Windows.Forms.TextBox>コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-107">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="b6f78-108">データソースにバインド<xref:System.Windows.Forms.BindingSource>されているにバインドします。</span><span class="sxs-lookup"><span data-stu-id="b6f78-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="b6f78-109">この例<xref:System.Windows.Forms.BindingSource>では、がデータベースにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="b6f78-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="b6f78-110">データセットとテーブルアダプターが生成されたら、 <xref:System.Windows.Forms.BindingNavigator>コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b6f78-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="b6f78-111">コントロールの<xref:System.Windows.Forms.BindingNavigator.BindingSource%2A>プロパティを、 <xref:System.Windows.Forms.BindingSource>コントロールにバインドされているフォーム上のに設定します。 <xref:System.Windows.Forms.BindingNavigator></span><span class="sxs-lookup"><span data-stu-id="b6f78-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="b6f78-112"><xref:System.Windows.Forms.BindingNavigator> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="b6f78-113">**[BindingNavigator タスク]** ダイアログボックスが表示されるように、スマートタググリフ (![スマートタググリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) をクリックし、 **[アイテムの編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="b6f78-114">**項目コレクションエディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6f78-114">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="b6f78-115">**Items コレクションエディター**で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-115">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="b6f78-116">適切な<xref:System.Windows.Forms.ToolStripSeparator>種類の<xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolStripItem>を選択し、 **[追加]** ボタンをクリックして、3つの項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="b6f78-117">ボタンのプロパティを loadbutton、savebutton、および cancelbutton にそれぞれ設定します。 <xref:System.Windows.Forms.ToolStripItem.Name%2A></span><span class="sxs-lookup"><span data-stu-id="b6f78-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="b6f78-118">読み込み、**保存**、 **キャンセル**の各ボタンのプロパティを設定します。<xref:System.Windows.Forms.ToolStripItem.Text%2A></span><span class="sxs-lookup"><span data-stu-id="b6f78-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="b6f78-119">各ボタン<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>のプロパティを **[テキスト]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="b6f78-120">または、このプロパティを**image**または**imageandtext**に設定し、 <xref:System.Windows.Forms.ToolStripItem.Image%2A>プロパティに表示されるようにイメージを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6f78-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="b6f78-121">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b6f78-121">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="b6f78-122">ボタンがに<xref:System.Windows.Forms.ToolStrip>追加されます。</span><span class="sxs-lookup"><span data-stu-id="b6f78-122">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="b6f78-123">フォームを右クリックし、 **[コードの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-123">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="b6f78-124">コードエディターで、テーブルアダプターにデータを読み込むコード行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="b6f78-124">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="b6f78-125">このコードは、手順 2. でデータバインディングを設定したときに生成されました。</span><span class="sxs-lookup"><span data-stu-id="b6f78-125">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="b6f78-126">コードは次`TableAdapterName.Fill(DataSetName.TableName)`のようになります。</span><span class="sxs-lookup"><span data-stu-id="b6f78-126">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="b6f78-127">通常、フォームの<xref:System.Windows.Forms.Form.Load>イベントに含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6f78-127">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="b6f78-128">前に作成した<xref:System.Windows.Forms.ToolStripItem.Click> **読み込み** <xref:System.Windows.Forms.ToolStripButton>のイベントのイベントハンドラーを作成し、このデータ読み込みコードをそのイベントに移動します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-128">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="b6f78-129">これで、コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b6f78-129">Your code should now look similar to the following:</span></span>

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

11. <span data-ttu-id="b6f78-130">前の手順で作成し<xref:System.Windows.Forms.ToolStripItem.Click>た**保存**<xref:System.Windows.Forms.ToolStripButton>のイベントのイベントハンドラーを作成し、コントロールがバインドされているテーブル内のデータを更新するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-130">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

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
    > <span data-ttu-id="b6f78-131">場合<xref:System.Windows.Forms.BindingNavigator>によっては、コンポーネントに **[保存]** ボタンが既に存在していても、Windows フォームデザイナーによってコードが生成されていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="b6f78-131">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="b6f78-132">この場合は、 <xref:System.Windows.Forms.ToolStripItem.Click> <xref:System.Windows.Forms.ToolStrip>上にまったく新しいボタンを作成するのではなく、そのボタンのイベントハンドラーに上記のコードを配置できます。</span><span class="sxs-lookup"><span data-stu-id="b6f78-132">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="b6f78-133">ただし、ボタンは既定で無効になっているので、 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A>ボタンのプロパティをに`true`設定して、ボタンが正しく機能するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6f78-133">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="b6f78-134">前に作成した<xref:System.Windows.Forms.ToolStripItem.Click> **キャンセル** <xref:System.Windows.Forms.ToolStripButton>のイベントのイベントハンドラーを作成し、表示されるデータレコードに対する変更を取り消すコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-134">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

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
    > <span data-ttu-id="b6f78-135">メソッド<xref:System.Windows.Forms.BindingSource.CancelEdit%2A>のスコープは、データの行です。</span><span class="sxs-lookup"><span data-stu-id="b6f78-135">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="b6f78-136">次のレコードに移動する前に、個々のレコードを表示しているときに行ったすべての変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="b6f78-136">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6f78-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6f78-137">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="b6f78-138">BindingNavigator コントロール</span><span class="sxs-lookup"><span data-stu-id="b6f78-138">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="b6f78-139">BindingSource コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="b6f78-139">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
