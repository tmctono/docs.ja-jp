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
ms.openlocfilehash: 788addee7c024577d029626da4aeb86d0ca9076a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941155"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="9b2fa-102">方法: 既存の Windows フォーム コントロールから継承する</span><span class="sxs-lookup"><span data-stu-id="9b2fa-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="9b2fa-103">既存のコントロールの機能を拡張する場合は、継承によって既存のコントロールから派生したコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="9b2fa-104">既存のコントロールから継承すると、そのコントロールのすべての機能およびビジュアル プロパティが引き継がれます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="9b2fa-105">継承するコントロールを作成する場合など<xref:System.Windows.Forms.Button>は、新しいコントロールになります、act とまったく同じ標準<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="9b2fa-106">その後で、カスタム メソッドやカスタム プロパティの実装によって、新しいコントロールの機能を拡張または変更できます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="9b2fa-107">一部のコントロールで変更することできますも継承されたコントロールの外観をオーバーライドしてその<xref:System.Windows.Forms.Control.OnPaint%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b2fa-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9b2fa-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9b2fa-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-inherited-control"></a><span data-ttu-id="9b2fa-111">継承したコントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="9b2fa-111">To create an inherited control</span></span>  
  
1. <span data-ttu-id="9b2fa-112">新しい **Windows フォーム アプリケーション プロジェクト**を作成します。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-112">Create a new **Windows Forms Application** project.</span></span>  
  
2. <span data-ttu-id="9b2fa-113">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-113">From the **Project** menu, choose **Add New Item**.</span></span>  
  
     <span data-ttu-id="9b2fa-114">**[新しい項目の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-114">The **Add New Item** dialog box appears.</span></span>  
  
3. <span data-ttu-id="9b2fa-115">**[新しい項目の追加]** ダイアログ ボックスの **[カスタム コントロール]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-115">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>  
  
     <span data-ttu-id="9b2fa-116">新しいカスタム コントロールがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-116">A new custom control is added to your project.</span></span>  
  
4. <span data-ttu-id="9b2fa-117">Visual Basic を使用している場合は、**ソリューション エクスプローラー**の上部にある **[すべてのファイルを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-117">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="9b2fa-118">CustomControl1.vb を展開し、コード エディターで CustomControl1.Designer.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-118">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>  
  
5. <span data-ttu-id="9b2fa-119">C# を使用している場合は、コード エディターで CustomControl1.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-119">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>  
  
6. <span data-ttu-id="9b2fa-120">継承されるクラス宣言を見つけます<xref:System.Windows.Forms.Control>します。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-120">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>  
  
7. <span data-ttu-id="9b2fa-121">基底クラスを継承元のコントロールに変更します。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-121">Change the base class to the control that you want to inherit from.</span></span>  
  
     <span data-ttu-id="9b2fa-122">継承したい場合など<xref:System.Windows.Forms.Button>、クラス宣言を次に変更します。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-122">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8. <span data-ttu-id="9b2fa-123">Visual Basic を使用している場合は、CustomControl1.Designer.vb を保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-123">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="9b2fa-124">コード エディターで CustomControl1.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-124">Open CustomControl1.vb in the Code Editor.</span></span>  
  
9. <span data-ttu-id="9b2fa-125">コントロールに組み込むカスタム メソッドやカスタム プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-125">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
10. <span data-ttu-id="9b2fa-126">コントロールの外観を変更する場合は、オーバーライド、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-126">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b2fa-127">オーバーライドする<xref:System.Windows.Forms.Control.OnPaint%2A>すべてのコントロールの外観を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-127">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="9b2fa-128">これらのコントロールを持つすべての描画が Windows によって行われます (たとえば、 <xref:System.Windows.Forms.TextBox>) 呼び出すことはありません、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッド、なり、決して使用して、カスタム コード。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-128">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="9b2fa-129">かどうかを変更する特定のコントロールのヘルプ ドキュメントを参照してください、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-129">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="9b2fa-130">すべての Windows フォーム コントロールの一覧については、「[Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-130">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="9b2fa-131">コントロールがない場合<xref:System.Windows.Forms.Control.OnPaint%2A>メンバー メソッドとして一覧に表示できない外観を変更するこのメソッドをオーバーライドすることで。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-131">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="9b2fa-132">カスタム描画の詳細については、「[コントロールのカスタム描画およびレンダリング](custom-control-painting-and-rendering.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-132">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>  
  
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
  
11. <span data-ttu-id="9b2fa-133">コントロールを保存して、動作確認を行います。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-133">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2fa-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b2fa-134">See also</span></span>

- [<span data-ttu-id="9b2fa-135">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="9b2fa-135">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="9b2fa-136">方法: コントロール クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-136">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="9b2fa-137">方法: UserControl クラスを継承します。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-137">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="9b2fa-138">方法: Windows フォームのコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="9b2fa-138">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="9b2fa-139">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9b2fa-139">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="9b2fa-140">チュートリアル: Visual Basic による Windows フォーム コントロールから継承します。</span><span class="sxs-lookup"><span data-stu-id="9b2fa-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="9b2fa-141">チュートリアル: ビジュアルを含む Windows フォーム コントロールからの継承C#</span><span class="sxs-lookup"><span data-stu-id="9b2fa-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
