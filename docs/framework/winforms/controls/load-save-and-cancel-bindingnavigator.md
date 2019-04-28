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
ms.openlocfilehash: 4d5cc91ca8bf71b2d5893f591652d777041e1a4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757376"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="b44f6-102">方法: Windows フォーム BindingNavigator コントロールに [Load]、[Save]、[Cancel] の各ボタンを追加する</span><span class="sxs-lookup"><span data-stu-id="b44f6-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="b44f6-103"><xref:System.Windows.Forms.BindingNavigator>コントロールが特別な用途<xref:System.Windows.Forms.ToolStrip>移動し、フォーム上のデータにバインドされているコントロールを操作することが想定されているコントロール。</span><span class="sxs-lookup"><span data-stu-id="b44f6-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="b44f6-104">ある、<xref:System.Windows.Forms.ToolStrip>コントロール、<xref:System.Windows.Forms.BindingNavigator>コンポーネントは、ユーザーの追加のまたは別のコマンドを含めるに簡単に変更できます。</span><span class="sxs-lookup"><span data-stu-id="b44f6-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="b44f6-105">次の手順で、<xref:System.Windows.Forms.TextBox>コントロールがデータにバインドされていると、<xref:System.Windows.Forms.ToolStrip>をフォームに追加するコントロールは、保存、読み込みを含めるし、キャンセル ボタンに変更されます。</span><span class="sxs-lookup"><span data-stu-id="b44f6-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="b44f6-106">負荷を追加するには、保存、およびキャンセル ボタンに BindingNavigator コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b44f6-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1. <span data-ttu-id="b44f6-107">フォームに <xref:System.Windows.Forms.TextBox> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2. <span data-ttu-id="b44f6-108">バインドする<xref:System.Windows.Forms.BindingSource>、データ ソースにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="b44f6-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="b44f6-109">この例で、<xref:System.Windows.Forms.BindingSource>データベースにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="b44f6-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3. <span data-ttu-id="b44f6-110">データセットとテーブルのアダプターが生成されると、ドラッグ、<xref:System.Windows.Forms.BindingNavigator>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="b44f6-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4. <span data-ttu-id="b44f6-111">設定、<xref:System.Windows.Forms.BindingNavigator>コントロールの<xref:System.Windows.Forms.BindingNavigator.BindingSource%2A>プロパティを<xref:System.Windows.Forms.BindingSource>コントロールにバインドされている形式にします。</span><span class="sxs-lookup"><span data-stu-id="b44f6-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5. <span data-ttu-id="b44f6-112"><xref:System.Windows.Forms.BindingNavigator> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6. <span data-ttu-id="b44f6-113">スマート タグ グリフをクリックします (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) ため、 **BindingNavigator タスク**ダイアログが表示され選択**アイテムの編集**.</span><span class="sxs-lookup"><span data-stu-id="b44f6-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="b44f6-114">**Items コレクション エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b44f6-114">The **Items Collection Editor** appears.</span></span>  
  
7. <span data-ttu-id="b44f6-115">**Items コレクション エディター**を次の手順します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1. <span data-ttu-id="b44f6-116">追加、<xref:System.Windows.Forms.ToolStripSeparator>と 3 つ<xref:System.Windows.Forms.ToolStripButton>を適切な種類の選択項目<xref:System.Windows.Forms.ToolStripItem>クリックして、**追加**ボタン。</span><span class="sxs-lookup"><span data-stu-id="b44f6-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2. <span data-ttu-id="b44f6-117">設定、<xref:System.Windows.Forms.ToolStripItem.Name%2A>プロパティをボタンの**LoadButton**、 **SaveButton**、および**CancelButton**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="b44f6-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>  
  
    3. <span data-ttu-id="b44f6-118">設定、<xref:System.Windows.Forms.ToolStripItem.Text%2A>プロパティをボタンの**ロード**、**保存**と**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>  
  
    4. <span data-ttu-id="b44f6-119">設定、<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>ボタンの各プロパティ**テキスト**します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="b44f6-120">このプロパティを設定する代わりに、**イメージ**または**ImageAndText**に表示されるイメージを設定し、<xref:System.Windows.Forms.ToolStripItem.Image%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b44f6-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5. <span data-ttu-id="b44f6-121">クリックして**OK**ダイアログ ボックスを閉じます。ボタンに追加されて、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8. <span data-ttu-id="b44f6-122">フォームを右クリックし **コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="b44f6-123">コード エディターでは、テーブル アダプターにデータを読み込むコードの行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="b44f6-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="b44f6-124">このコードは、手順 2 でのデータ バインディングを設定するときに生成されました。</span><span class="sxs-lookup"><span data-stu-id="b44f6-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="b44f6-125">コードは、次のようになります:`TableAdapterName.Fill(DataSetName.TableName)`します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="b44f6-126">ほとんどは、フォームのいる可能性がある<xref:System.Windows.Forms.Form.Load>イベント。</span><span class="sxs-lookup"><span data-stu-id="b44f6-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="b44f6-127">イベント ハンドラーを作成、<xref:System.Windows.Forms.ToolStripItem.Click>のイベント、**ロード**<xref:System.Windows.Forms.ToolStripButton>以前に作成し、このデータ読み込みコードを移動します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="b44f6-128">コードは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b44f6-128">Your code should now look similar to the following:</span></span>  
  
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
  
11. <span data-ttu-id="b44f6-129">イベント ハンドラーを作成、<xref:System.Windows.Forms.ToolStripItem.Click>のイベント、**保存**<xref:System.Windows.Forms.ToolStripButton>前に作成され、テーブル コントロール内のデータを更新するコードを記述にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b44f6-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
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
    > <span data-ttu-id="b44f6-130">場合によってで、<xref:System.Windows.Forms.BindingNavigator>コンポーネントでは既に、**保存**コードではなく、ボタンはによって生成された、Windows フォーム デザイナー。</span><span class="sxs-lookup"><span data-stu-id="b44f6-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a **Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="b44f6-131">ここで上記のコードを配置することができます、<xref:System.Windows.Forms.ToolStripItem.Click>で、まったく新しいボタンを作成するのではなく、そのボタンのイベント ハンドラー、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="b44f6-132">ボタンが既定では、無効になりますので、設定する必要があります、<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>プロパティをボタンの`true`ボタンの機能を正しくが。</span><span class="sxs-lookup"><span data-stu-id="b44f6-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>
  
12. <span data-ttu-id="b44f6-133">イベント ハンドラーを作成、<xref:System.Windows.Forms.ToolStripItem.Click>のイベント、**キャンセル**<xref:System.Windows.Forms.ToolStripButton>以前に作成し、表示されるデータのレコードに変更をキャンセルするコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
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
    >  <span data-ttu-id="b44f6-134"><xref:System.Windows.Forms.BindingSource.CancelEdit%2A>メソッドのスコープは、データの行にします。</span><span class="sxs-lookup"><span data-stu-id="b44f6-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="b44f6-135">次のレコードに移動する前に個々 のレコードを表示中に加えたあらゆる変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="b44f6-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b44f6-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="b44f6-136">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="b44f6-137">BindingNavigator コントロール</span><span class="sxs-lookup"><span data-stu-id="b44f6-137">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="b44f6-138">BindingSource コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="b44f6-138">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
