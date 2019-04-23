---
title: 'チュートリアル: MaskedTextBox コントロールの使用'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: ff9a0edb44a95f5853edf711e0a1559e3b2e3b15
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342466"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="237f8-102">チュートリアル: MaskedTextBox コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="237f8-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="237f8-103">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="237f8-103">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="237f8-104">初期化、<xref:System.Windows.Forms.MaskedTextBox>コントロール</span><span class="sxs-lookup"><span data-stu-id="237f8-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
-   <span data-ttu-id="237f8-105">使用して、<xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>文字が、マスクに準拠していないときにユーザーに警告するイベント ハンドラー</span><span class="sxs-lookup"><span data-stu-id="237f8-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
-   <span data-ttu-id="237f8-106">型の割り当て、<xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>プロパティを使用して、<xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>コミットしようとして値の型の有効な場合、ユーザーのアラートを生成するイベント ハンドラー</span><span class="sxs-lookup"><span data-stu-id="237f8-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="237f8-107">プロジェクトを作成し、コントロールの追加</span><span class="sxs-lookup"><span data-stu-id="237f8-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="237f8-108">MaskedTextBox コントロールをフォームに追加するには</span><span class="sxs-lookup"><span data-stu-id="237f8-108">To add a MaskedTextBox control to your form</span></span>  
  
1. <span data-ttu-id="237f8-109">配置するフォームを開いて、<xref:System.Windows.Forms.MaskedTextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="237f8-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2. <span data-ttu-id="237f8-110">ドラッグ、<xref:System.Windows.Forms.MaskedTextBox>コントロールから、**ツールボックス**をフォームにします。</span><span class="sxs-lookup"><span data-stu-id="237f8-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3. <span data-ttu-id="237f8-111">コントロールを右クリックし、選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="237f8-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="237f8-112">**プロパティ**ウィンドウで、**マスク**プロパティをクリックして、 **.** プロパティ名の横にある (省略記号) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="237f8-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4. <span data-ttu-id="237f8-113">**定型入力**ダイアログ ボックスで、**短い日付**マスクし、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="237f8-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5. <span data-ttu-id="237f8-114">**プロパティ**ウィンドウのセット、<xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="237f8-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="237f8-115">このプロパティの場合、短いビープ音を鳴らす、ユーザーが入力マスクの定義に違反している文字を試みるたびにします。</span><span class="sxs-lookup"><span data-stu-id="237f8-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="237f8-116">Mask プロパティをサポートする、文字の概要については、「解説」を参照してください、<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="237f8-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="237f8-117">入力エラーをユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="237f8-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="237f8-118">拒否されたマスク入力のバルーン ヒントを追加します</span><span class="sxs-lookup"><span data-stu-id="237f8-118">Add a balloon tip for rejected mask input</span></span>  
  
1. <span data-ttu-id="237f8-119">戻り、**ツールボックス**を追加し、<xref:System.Windows.Forms.ToolTip>をフォームにします。</span><span class="sxs-lookup"><span data-stu-id="237f8-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2. <span data-ttu-id="237f8-120">イベント ハンドラーを作成、<xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>イベントを発生させる、<xref:System.Windows.Forms.ToolTip>入力エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="237f8-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="237f8-121">5 秒間、または、ユーザーがクリックするまで、バルーン ヒントが表示されたままです。</span><span class="sxs-lookup"><span data-stu-id="237f8-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="237f8-122">無効な種類のユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="237f8-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="237f8-123">無効なデータ型のバルーン ヒントを追加します</span><span class="sxs-lookup"><span data-stu-id="237f8-123">Add a balloon tip for invalid data types</span></span>  
  
1. <span data-ttu-id="237f8-124">フォームの<xref:System.Windows.Forms.Form.Load>イベント ハンドラーを割り当てる、<xref:System.Type>オブジェクトを表す、<xref:System.DateTime>型、<xref:System.Windows.Forms.MaskedTextBox>コントロールの<xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="237f8-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. <span data-ttu-id="237f8-125"><xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> イベントのイベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="237f8-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="237f8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="237f8-126">See also</span></span>

- <xref:System.Windows.Forms.MaskedTextBox>
- [<span data-ttu-id="237f8-127">MaskedTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="237f8-127">MaskedTextBox Control</span></span>](maskedtextbox-control-windows-forms.md)
