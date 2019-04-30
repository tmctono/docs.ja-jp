---
title: '方法: 複合コントロールを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
ms.openlocfilehash: 8bb630d3fb7e064935440439f2f07816e87c77dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010957"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="cf542-102">方法: 複合コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="cf542-102">How to: Author Composite Controls</span></span>
<span data-ttu-id="cf542-103">複合コントロールはさまざまな方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf542-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="cf542-104">Windows デスクトップ アプリケーション プロジェクトの一部として複合コントロールを作成し、プロジェクト内のフォーム上でのみ使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cf542-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="cf542-105">または、Windows コントロール ライブラリ プロジェクトで複合コントロールを作成し、プロジェクトをアセンブリにコンパイルして、他のプロジェクトで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf542-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="cf542-106">そのコントロールから継承することや、ビジュアル継承を使用して特殊な用途のために簡単にカスタマイズすることまでできます。</span><span class="sxs-lookup"><span data-stu-id="cf542-106">You can even inherit from them, and use visual inheritance to customize them quickly for special purposes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf542-107">Web フォームで使用する複合コントロールを作成する場合は、「[カスタム ASP.NET サーバー コントロールの開発](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf542-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>  
>   
>  <span data-ttu-id="cf542-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf542-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cf542-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf542-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cf542-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf542-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-author-a-composite-control"></a><span data-ttu-id="cf542-111">複合コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="cf542-111">To author a composite control</span></span>  
  
1. <span data-ttu-id="cf542-112">`DemoControlHost` という新しい **Windows アプリケーション** プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="cf542-112">Open a new **Windows Application** project called `DemoControlHost`.</span></span>  
  
2. <span data-ttu-id="cf542-113">**[プロジェクト]** メニューの **[ユーザー コントロールの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf542-113">On the **Project** menu, click **Add User Control**.</span></span>  
  
3. <span data-ttu-id="cf542-114">**[新しい項目の追加]** ダイアログ ボックスで、クラス ファイル (.vb または .cs ファイル) に複合コントロールに付ける名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf542-114">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>  
  
4. <span data-ttu-id="cf542-115">選択、**追加**複合コントロールのクラス ファイルを作成するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf542-115">Select the **Add** button to create the class file for the composite control.</span></span>  
  
5. <span data-ttu-id="cf542-116">複合コントロールのサーフェスに **[ツールボックス]** からコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf542-116">Add controls from the **Toolbox** to the composite control surface.</span></span>  
  
6. <span data-ttu-id="cf542-117">複合コントロールまたはその内在コントロールによって発生したイベントを処理するために、イベント プロシージャにコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="cf542-117">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>  
  
7. <span data-ttu-id="cf542-118">複合コントロールのデザイナーを閉じて、メッセージが表示されたらファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cf542-118">Close the designer for the composite control, and save the file when you are prompted.</span></span>  
  
8. <span data-ttu-id="cf542-119">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf542-119">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="cf542-120">カスタム コントロールが **[ツールボックス]** に表示されるようにプロジェクトをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf542-120">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>  
  
9. <span data-ttu-id="cf542-121">**[ツールボックス]** の **[DemoControlHost]** タブを使用して、コントロールのインスタンスを `Form1` に追加します。</span><span class="sxs-lookup"><span data-stu-id="cf542-121">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>  
  
### <a name="to-author-a-control-class-library"></a><span data-ttu-id="cf542-122">コントロール クラス ライブラリを作成するには</span><span class="sxs-lookup"><span data-stu-id="cf542-122">To author a control class library</span></span>  
  
1. <span data-ttu-id="cf542-123">新しい **Windows コントロール ライブラリ** プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="cf542-123">Open a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="cf542-124">既定では、プロジェクトに複合コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf542-124">By default, the project contains a composite control.</span></span>  
  
2. <span data-ttu-id="cf542-125">上記の手順の説明に従ってコントロールとコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf542-125">Add controls and code as described in the procedure above.</span></span>  
  
3. <span data-ttu-id="cf542-126">継承クラスで変更しないコントロールを選択して、このコントロールの **Modifiers** プロパティを **Private** に設定します。</span><span class="sxs-lookup"><span data-stu-id="cf542-126">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>  
  
4. <span data-ttu-id="cf542-127">DLL をビルドします。</span><span class="sxs-lookup"><span data-stu-id="cf542-127">Build the DLL.</span></span>  
  
### <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="cf542-128">コントロール クラス ライブラリの複合コントロールから継承するには</span><span class="sxs-lookup"><span data-stu-id="cf542-128">To inherit from a composite control in a control class library</span></span>  
  
1. <span data-ttu-id="cf542-129">**[ファイル]** メニューで、**[追加]** をポイントし、**[新しいプロジェクト]** を選択して、新しい **Windows アプリケーション** プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="cf542-129">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>  
  
2. <span data-ttu-id="cf542-130">**ソリューション エクスプローラー**で、新しいプロジェクトの **[参照設定]** フォルダーを右クリックし、**[参照の追加]** をクリックして **[参照の追加]** ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="cf542-130">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
3. <span data-ttu-id="cf542-131">**[プロジェクト]** タブを選択し、コントロール ライブラリ プロジェクトをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf542-131">Select the **Projects** tab and double-click your control library project.</span></span>  
  
4. <span data-ttu-id="cf542-132">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf542-132">On the **Build** menu, click **Build Solution**.</span></span>  
  
5. <span data-ttu-id="cf542-133">**ソリューション エクスプローラー**で、コントロール ライブラリ プロジェクトを右クリックし、ショートカット メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf542-133">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>  
  
6. <span data-ttu-id="cf542-134">**[新しい項目の追加]** ダイアログ ボックスの **[継承されたユーザー コントロール]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf542-134">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>  
  
7. <span data-ttu-id="cf542-135">**[継承ピッカー]** ダイアログ ボックスで、継承元のコントロールをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf542-135">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>  
  
     <span data-ttu-id="cf542-136">新しいコントロールがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cf542-136">A new control is added to your project.</span></span>  
  
8. <span data-ttu-id="cf542-137">新しいコントロールのビジュアル デザイナーを開き、別の内在コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf542-137">Open the visual designer for the new control and add additional constituent controls.</span></span>  
  
     <span data-ttu-id="cf542-138">DLL の複合コントロールから継承された内在コントロールを表示し、**Modifiers** プロパティが **Public** であるコントロールのプロパティを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="cf542-138">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="cf542-139">**Modifiers** プロパティが **Private** であるコントロールのプロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf542-139">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf542-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf542-140">See also</span></span>

- [<span data-ttu-id="cf542-141">チュートリアル: Visual Basic による複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="cf542-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="cf542-142">チュートリアル: ビジュアルを含む複合コントロールの作成C#</span><span class="sxs-lookup"><span data-stu-id="cf542-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="cf542-143">チュートリアル: Visual Basic による Windows フォーム コントロールから継承します。</span><span class="sxs-lookup"><span data-stu-id="cf542-143">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="cf542-144">チュートリアル: ビジュアルを含む Windows フォーム コントロールからの継承C#</span><span class="sxs-lookup"><span data-stu-id="cf542-144">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="cf542-145">コントロールの種類に関するアドバイス</span><span class="sxs-lookup"><span data-stu-id="cf542-145">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="cf542-146">方法: Windows フォームのコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="cf542-146">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="cf542-147">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="cf542-147">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
