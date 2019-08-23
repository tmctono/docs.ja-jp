---
title: '方法: Windows フォームにコントロールを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 7ee603fa5350ef81c6d32d2f22119bbe526295df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912626"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="6cf81-102">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="6cf81-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="6cf81-103">ほとんどのフォームは、ユーザーインターフェイス (UI) を定義するためにフォームの画面にコントロールを追加することによって設計されています。</span><span class="sxs-lookup"><span data-stu-id="6cf81-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="6cf81-104">*コントロール*は、情報の表示やユーザー入力の受け入れに使用されるフォーム上のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="6cf81-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="6cf81-105">コントロールの詳細については、「 [Windows フォームコントロール](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cf81-105">For more information about controls, see [Windows Forms Controls](index.md).</span></span>

## <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="6cf81-106">フォームにコントロールを描画するには</span><span class="sxs-lookup"><span data-stu-id="6cf81-106">To draw a control on a form</span></span>

1. <span data-ttu-id="6cf81-107">フォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cf81-107">Open the form.</span></span> <span data-ttu-id="6cf81-108">詳細については、「[方法 :デザイナー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))で Windows フォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="6cf81-108">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="6cf81-109">**ツールボックス**で、フォームに追加するコントロールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cf81-109">In the **Toolbox**, click the control you want to add to your form.</span></span>

3. <span data-ttu-id="6cf81-110">フォームで、コントロールの左上隅を配置する場所をクリックして、コントロールの右下隅を配置する場所にドラッグして、をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6cf81-110">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>

     <span data-ttu-id="6cf81-111">コントロールが、指定された位置とサイズでフォームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6cf81-111">The control is added to the form with the specified location and size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6cf81-112">各コントロールには、既定のサイズが定義されています。</span><span class="sxs-lookup"><span data-stu-id="6cf81-112">Each control has a default size defined.</span></span> <span data-ttu-id="6cf81-113">コントロールを**ツールボックス**からフォームにドラッグすると、コントロールの既定のサイズでコントロールをフォームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="6cf81-113">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>

## <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="6cf81-114">コントロールをフォームにドラッグするには</span><span class="sxs-lookup"><span data-stu-id="6cf81-114">To drag a control to a form</span></span>

1. <span data-ttu-id="6cf81-115">フォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cf81-115">Open the form.</span></span> <span data-ttu-id="6cf81-116">詳細については、「[方法 :デザイナー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))で Windows フォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="6cf81-116">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="6cf81-117">**ツールボックス**で、目的のコントロールをクリックし、フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6cf81-117">In the **Toolbox**, click the control you want and drag it to your form.</span></span>

     <span data-ttu-id="6cf81-118">コントロールは、既定のサイズで指定された位置にフォームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6cf81-118">The control is added to the form at the specified location in its default size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6cf81-119">**ツールボックス**のコントロールをダブルクリックすると、既定のサイズでフォームの左上隅に追加できます。</span><span class="sxs-lookup"><span data-stu-id="6cf81-119">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>

     <span data-ttu-id="6cf81-120">また、実行時にコントロールをフォームに動的に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cf81-120">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="6cf81-121">次のコード例<xref:System.Windows.Forms.TextBox>では、コントロールがクリックさ<xref:System.Windows.Forms.Button>れると、コントロールがフォームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6cf81-121">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6cf81-122">次の手順では、**ボタン**コントロール`Button1`が既に配置されているフォームが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cf81-122">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>

## <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="6cf81-123">プログラムによってフォームにコントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="6cf81-123">To add a control to a form programmatically</span></span>

1. <span data-ttu-id="6cf81-124">フォームのクラス内のボタンの`Click`イベントを処理するメソッドで、次のようなコードを挿入して、コントロール変数への参照を追加し、コントロールの`Location`を設定して、コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="6cf81-124">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>

    ```vb
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
       Dim MyText As New TextBox()
       MyText.Location = New Point(25, 25)
       Me.Controls.Add(MyText)
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
       TextBox myText = new TextBox();
       myText.Location = new Point(25,25);
       this.Controls.Add (myText);
    }
    ```

    ```cpp
    private:
      System::Void button1_Click(System::Object ^  sender,
        System::EventArgs ^  e)
      {
        TextBox ^ myText = gcnew TextBox();
        myText->Location = Point(25,25);
        this->Controls->Add(myText);
      }
    ```

    > [!NOTE]
    > <span data-ttu-id="6cf81-125">また、コントロールの他のプロパティを初期化するコードを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cf81-125">You can also add code to initialize other properties of the control.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="6cf81-126">悪意`UserControl`のあるを参照することにより、ネットワーク経由でローカルコンピューターをセキュリティ上のリスクにさらすことがあります。</span><span class="sxs-lookup"><span data-stu-id="6cf81-126">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="6cf81-127">これは、悪意のあるユーザーが有害なカスタムコントロールを作成した後、誤ってプロジェクトに追加した場合にのみ問題になります。</span><span class="sxs-lookup"><span data-stu-id="6cf81-127">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cf81-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cf81-128">See also</span></span>

- [<span data-ttu-id="6cf81-129">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="6cf81-129">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="6cf81-130">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="6cf81-130">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="6cf81-131">方法: Windows フォームのコントロールのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="6cf81-131">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="6cf81-132">方法: Windows フォームコントロールによって表示されるテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="6cf81-132">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="6cf81-133">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="6cf81-133">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
