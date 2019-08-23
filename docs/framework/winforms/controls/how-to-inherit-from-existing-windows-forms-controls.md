---
title: '方法: 既存の Windows フォーム コントロールから継承する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 9ac18fae126425126712dafeb80f05663dfc2ebc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966587"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="d6cd7-102">方法: 既存の Windows フォーム コントロールから継承する</span><span class="sxs-lookup"><span data-stu-id="d6cd7-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="d6cd7-103">既存のコントロールの機能を拡張する場合は、継承によって既存のコントロールから派生したコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="d6cd7-104">既存のコントロールから継承すると、そのコントロールのすべての機能およびビジュアル プロパティが引き継がれます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="d6cd7-105">たとえば、から<xref:System.Windows.Forms.Button>継承されたコントロールを作成した場合、新しいコントロールは標準<xref:System.Windows.Forms.Button>コントロールとまったく同じように見え、動作します。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="d6cd7-106">その後で、カスタム メソッドやカスタム プロパティの実装によって、新しいコントロールの機能を拡張または変更できます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="d6cd7-107">一部のコントロールでは、 <xref:System.Windows.Forms.Control.OnPaint%2A>メソッドをオーバーライドすることによって、継承されたコントロールの外観を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

## <a name="to-create-an-inherited-control"></a><span data-ttu-id="d6cd7-108">継承したコントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="d6cd7-108">To create an inherited control</span></span>

1. <span data-ttu-id="d6cd7-109">新しい **Windows フォーム アプリケーション プロジェクト**を作成します。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-109">Create a new **Windows Forms Application** project.</span></span>

2. <span data-ttu-id="d6cd7-110">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-110">From the **Project** menu, choose **Add New Item**.</span></span>

     <span data-ttu-id="d6cd7-111">**[新しい項目の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-111">The **Add New Item** dialog box appears.</span></span>

3. <span data-ttu-id="d6cd7-112">**[新しい項目の追加]** ダイアログ ボックスの **[カスタム コントロール]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-112">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>

     <span data-ttu-id="d6cd7-113">新しいカスタム コントロールがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-113">A new custom control is added to your project.</span></span>

4. <span data-ttu-id="d6cd7-114">Visual Basic を使用している場合は、**ソリューション エクスプローラー**の上部にある **[すべてのファイルを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-114">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="d6cd7-115">CustomControl1.vb を展開し、コード エディターで CustomControl1.Designer.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-115">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>

5. <span data-ttu-id="d6cd7-116">C# を使用している場合は、コード エディターで CustomControl1.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-116">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>

6. <span data-ttu-id="d6cd7-117">から<xref:System.Windows.Forms.Control>継承するクラス宣言を探します。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-117">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>

7. <span data-ttu-id="d6cd7-118">基底クラスを継承元のコントロールに変更します。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-118">Change the base class to the control that you want to inherit from.</span></span>

     <span data-ttu-id="d6cd7-119">たとえば、から<xref:System.Windows.Forms.Button>継承する場合は、クラスの宣言を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-119">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

8. <span data-ttu-id="d6cd7-120">Visual Basic を使用している場合は、CustomControl1.Designer.vb を保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-120">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="d6cd7-121">コード エディターで CustomControl1.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-121">Open CustomControl1.vb in the Code Editor.</span></span>

9. <span data-ttu-id="d6cd7-122">コントロールに組み込むカスタム メソッドやカスタム プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-122">Implement any custom methods or properties that your control will incorporate.</span></span>

10. <span data-ttu-id="d6cd7-123">コントロールのグラフィカルな外観を変更する場合は、 <xref:System.Windows.Forms.Control.OnPaint%2A>メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-123">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d6cd7-124">を<xref:System.Windows.Forms.Control.OnPaint%2A>オーバーライドしても、すべてのコントロールの外観を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-124">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="d6cd7-125">Windows によって実行されるすべての描画 (たとえば、 <xref:System.Windows.Forms.TextBox>) を持つコントロールは、 <xref:System.Windows.Forms.Control.OnPaint%2A>メソッドを呼び出すことがないため、カスタムコードは使用されません。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-125">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="d6cd7-126"><xref:System.Windows.Forms.Control.OnPaint%2A>メソッドが使用可能かどうかを確認するには、変更する特定のコントロールのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-126">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="d6cd7-127">すべての Windows フォーム コントロールの一覧については、「[Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-127">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="d6cd7-128">コントロールがメンバーメソッドとし<xref:System.Windows.Forms.Control.OnPaint%2A>てリストされていない場合は、このメソッドをオーバーライドすることによって外観を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-128">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="d6cd7-129">カスタム描画の詳細については、「[コントロールのカスタム描画およびレンダリング](custom-control-painting-and-rendering.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-129">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

11. <span data-ttu-id="d6cd7-130">コントロールを保存して、動作確認を行います。</span><span class="sxs-lookup"><span data-stu-id="d6cd7-130">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6cd7-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6cd7-131">See also</span></span>

- [<span data-ttu-id="d6cd7-132">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="d6cd7-132">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="d6cd7-133">方法: コントロールクラスから継承する</span><span class="sxs-lookup"><span data-stu-id="d6cd7-133">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="d6cd7-134">方法: UserControl クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="d6cd7-134">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="d6cd7-135">方法: Windows フォームの作成者コントロール</span><span class="sxs-lookup"><span data-stu-id="d6cd7-135">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="d6cd7-136">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d6cd7-136">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="d6cd7-137">チュートリアル: Visual Basic を使用した Windows フォームコントロールからの継承</span><span class="sxs-lookup"><span data-stu-id="d6cd7-137">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="d6cd7-138">チュートリアル: ビジュアルを使用した Windows フォームコントロールからの継承C#</span><span class="sxs-lookup"><span data-stu-id="d6cd7-138">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
