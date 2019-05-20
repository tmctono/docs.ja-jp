---
title: 'チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
ms.openlocfilehash: 4d741beffa5649d1d1593ba3dbb7a1918b669b80
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882310"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a><span data-ttu-id="ded80-102">チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="ded80-102">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>

<span data-ttu-id="ded80-103">関連するカスタム デザイナーを作成することにより、カスタム コントロールのデザイン時エクスペリエンスを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="ded80-103">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>

<span data-ttu-id="ded80-104">このチュートリアルでは、カスタム コントロールのカスタム デザイナーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ded80-104">This walkthrough illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="ded80-105">実装、`MarqueeControl`型およびと呼ばれる、関連付けられているデザイナー クラス`MarqueeControlRootDesigner`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-105">You will implement a `MarqueeControl` type and an associated designer class, called `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="ded80-106">`MarqueeControl`アニメーションと点滅しているテキストのシアター マーキーのような表示を実装する型。</span><span class="sxs-lookup"><span data-stu-id="ded80-106">The `MarqueeControl` type implements a display similar to a theater marquee, with animated lights and flashing text.</span></span>

<span data-ttu-id="ded80-107">このコントロールのデザイナーは、カスタムのデザイン時エクスペリエンスを提供するデザイン環境と対話します。</span><span class="sxs-lookup"><span data-stu-id="ded80-107">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="ded80-108">カスタムのデザイナーを使用したカスタムをアセンブルできます`MarqueeControl`アニメーションと多くの組み合わせで点滅しているテキストの実装。</span><span class="sxs-lookup"><span data-stu-id="ded80-108">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="ded80-109">アセンブルされたコントロールは、他の Windows フォーム コントロールのような形式を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ded80-109">You can use the assembled control on a form like any other Windows Forms control.</span></span>

<span data-ttu-id="ded80-110">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="ded80-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="ded80-111">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="ded80-111">Creating the Project</span></span>

- <span data-ttu-id="ded80-112">コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-112">Creating a Control Library Project</span></span>

- <span data-ttu-id="ded80-113">カスタム コントロール プロジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="ded80-113">Referencing the Custom Control Project</span></span>

- <span data-ttu-id="ded80-114">カスタム コントロールとそのカスタム デザイナーを定義します。</span><span class="sxs-lookup"><span data-stu-id="ded80-114">Defining a Custom Control and Its Custom Designer</span></span>

- <span data-ttu-id="ded80-115">カスタム コントロールのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-115">Creating an Instance of Your Custom Control</span></span>

- <span data-ttu-id="ded80-116">デザイン時のデバッグ プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="ded80-116">Setting Up the Project for Design-Time Debugging</span></span>

- <span data-ttu-id="ded80-117">カスタム コントロールを実装します。</span><span class="sxs-lookup"><span data-stu-id="ded80-117">Implementing Your Custom Control</span></span>

- <span data-ttu-id="ded80-118">カスタム コントロールの子コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-118">Creating a Child Control for Your Custom Control</span></span>

- <span data-ttu-id="ded80-119">MarqueeBorder 子コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-119">Create the MarqueeBorder Child Control</span></span>

- <span data-ttu-id="ded80-120">シャドウとフィルターのプロパティにカスタム デザイナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-120">Creating a Custom Designer to Shadow and Filter Properties</span></span>

- <span data-ttu-id="ded80-121">コンポーネントの変更の処理</span><span class="sxs-lookup"><span data-stu-id="ded80-121">Handling Component Changes</span></span>

- <span data-ttu-id="ded80-122">デザイナー動詞をカスタム デザイナーに追加します。</span><span class="sxs-lookup"><span data-stu-id="ded80-122">Adding Designer Verbs to your Custom Designer</span></span>

- <span data-ttu-id="ded80-123">カスタムの UITypeEditor を作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-123">Creating a Custom UITypeEditor</span></span>

- <span data-ttu-id="ded80-124">デザイナーでカスタム コントロールのテスト</span><span class="sxs-lookup"><span data-stu-id="ded80-124">Testing your Custom Control in the Designer</span></span>

<span data-ttu-id="ded80-125">完了したら、カスタム コントロールは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ded80-125">When you are finished, your custom control will look something like the following:</span></span>

![テキストと開始、停止ボタンを示す範囲を表示するアプリです。](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

<span data-ttu-id="ded80-127">完全なコード一覧は、次を参照してください。[方法。デザイン時機能を活用した Windows フォーム コントロールを作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))です。</span><span class="sxs-lookup"><span data-stu-id="ded80-127">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>

> [!NOTE]
> <span data-ttu-id="ded80-128">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ded80-128">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ded80-129">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ded80-129">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ded80-130">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ded80-130">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ded80-131">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ded80-131">Prerequisites</span></span>

<span data-ttu-id="ded80-132">このチュートリアルを完了するのには、Visual Studio を必要があります。</span><span class="sxs-lookup"><span data-stu-id="ded80-132">In order to complete this walkthrough, you'll need Visual Studio.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="ded80-133">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="ded80-133">Creating the Project</span></span>

<span data-ttu-id="ded80-134">最初の手順では、アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-134">The first step is to create the application project.</span></span> <span data-ttu-id="ded80-135">このプロジェクトを使用すると、カスタム コントロールをホストするアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ded80-135">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="ded80-136">Visual Studio を開き、「ため」と呼ばれる Windows フォーム アプリケーション プロジェクトを作成する (**ファイル** > **新規** > **プロジェクト** > **Visual C#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォーム アプリケーション**).</span><span class="sxs-lookup"><span data-stu-id="ded80-136">Open Visual Studio and create a Windows Forms Application project called "MarqueeControlTest" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="creating-a-control-library-project"></a><span data-ttu-id="ded80-137">コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-137">Creating a Control Library Project</span></span>

<span data-ttu-id="ded80-138">次の手順では、コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-138">The next step is to create the control library project.</span></span> <span data-ttu-id="ded80-139">新しいカスタム コントロールとその対応するカスタム デザイナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-139">You will create a new custom control and its corresponding custom designer.</span></span>

### <a name="to-create-the-control-library-project"></a><span data-ttu-id="ded80-140">コントロール ライブラリ プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="ded80-140">To create the control library project</span></span>

1. <span data-ttu-id="ded80-141">Windows フォーム コントロール ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ded80-141">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="ded80-142">「に」プロジェクトを名前します。</span><span class="sxs-lookup"><span data-stu-id="ded80-142">Name the project "MarqueeControlLibrary."</span></span>

2. <span data-ttu-id="ded80-143">使用して**ソリューション エクスプ ローラー**、選択した言語に応じて"UserControl1.cs"または「[usercontrol1.vb]」をという名前のソース ファイルを削除することによって、プロジェクトの既定のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="ded80-143">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span> <span data-ttu-id="ded80-144">詳細については、「[方法 :削除、削除、および項目を除外](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="ded80-144">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="ded80-145">新しい追加<xref:System.Windows.Forms.UserControl>項目を`MarqueeControlLibrary`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-145">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ded80-146">新しいソース ファイル"MarqueeControl"の基本の名前を付けます</span><span class="sxs-lookup"><span data-stu-id="ded80-146">Give the new source file a base name of "MarqueeControl."</span></span>

4. <span data-ttu-id="ded80-147">使用して**ソリューション エクスプ ローラー**で新しいフォルダーを作成、`MarqueeControlLibrary`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-147">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ded80-148">詳細については、「[方法 :新しいプロジェクト項目の追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="ded80-148">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="ded80-149">新しいフォルダーの名前を「設計します」</span><span class="sxs-lookup"><span data-stu-id="ded80-149">Name the new folder "Design."</span></span>

5. <span data-ttu-id="ded80-150">右クリックし、**デザイン**フォルダーと新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="ded80-150">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="ded80-151">ソース ファイルの「ここで」基本の名前を付けます</span><span class="sxs-lookup"><span data-stu-id="ded80-151">Give the source file a base name of "MarqueeControlRootDesigner."</span></span>

6. <span data-ttu-id="ded80-152">System.Design アセンブリから型を使用して、そのためにこの参照を追加する必要があります、`MarqueeControlLibrary`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-152">You will need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ded80-153">System.Design アセンブリを使用するには、プロジェクトの .NET Framework、.NET Framework クライアント プロファイルではなく完全なバージョンを対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ded80-153">To use the System.Design assembly, your project must target the full version of the .NET Framework, not the .NET Framework Client Profile.</span></span> <span data-ttu-id="ded80-154">ターゲット フレームワークを変更するを参照してください。[方法.NET Framework のターゲット バージョンを指定する](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ded80-154">To change the target framework, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

## <a name="referencing-the-custom-control-project"></a><span data-ttu-id="ded80-155">カスタム コントロール プロジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="ded80-155">Referencing the Custom Control Project</span></span>

<span data-ttu-id="ded80-156">使用する、`MarqueeControlTest`カスタム コントロールをテストするプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-156">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="ded80-157">プロジェクト参照を追加するときに、テスト プロジェクトにカスタム コントロールを認識なります、`MarqueeControlLibrary`アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="ded80-157">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>

### <a name="to-reference-the-custom-control-project"></a><span data-ttu-id="ded80-158">カスタム コントロール プロジェクトを参照するには</span><span class="sxs-lookup"><span data-stu-id="ded80-158">To reference the custom control project</span></span>

- <span data-ttu-id="ded80-159">`MarqueeControlTest`プロジェクトで、プロジェクト参照を追加、`MarqueeControlLibrary`アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="ded80-159">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="ded80-160">使用してください、**プロジェクト** タブで、**参照の追加** ダイアログ ボックスを参照するのではなく、`MarqueeControlLibrary`直接アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="ded80-160">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>

## <a name="defining-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="ded80-161">カスタム コントロールとそのカスタム デザイナーを定義します。</span><span class="sxs-lookup"><span data-stu-id="ded80-161">Defining a Custom Control and Its Custom Designer</span></span>
 <span data-ttu-id="ded80-162">派生して、カスタム コントロール、<xref:System.Windows.Forms.UserControl>クラス。</span><span class="sxs-lookup"><span data-stu-id="ded80-162">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="ded80-163">これにより、コントロール、その他のコントロールを格納して、コントロールの既定の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ded80-163">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>

 <span data-ttu-id="ded80-164">カスタム コントロールは、関連するカスタム デザイナー必要があります。</span><span class="sxs-lookup"><span data-stu-id="ded80-164">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="ded80-165">これにより、カスタム コントロールに特化した独自のデザイン エクスペリエンスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ded80-165">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>

 <span data-ttu-id="ded80-166">使用して、デザイナーでコントロールに関連付ける、<xref:System.ComponentModel.DesignerAttribute>クラス。</span><span class="sxs-lookup"><span data-stu-id="ded80-166">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="ded80-167">カスタム デザイナーの実装は、カスタム コントロールの全体のデザイン時の動作を開発しているため、<xref:System.ComponentModel.Design.IRootDesigner>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ded80-167">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>

### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="ded80-168">カスタム コントロールとそのカスタム デザイナーを定義するには</span><span class="sxs-lookup"><span data-stu-id="ded80-168">To define a custom control and its custom designer</span></span>

1. <span data-ttu-id="ded80-169">開く、`MarqueeControl`内のソース ファイル、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-169">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="ded80-170">ファイルの上部にある次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ded80-170">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <span data-ttu-id="ded80-171">追加、<xref:System.ComponentModel.DesignerAttribute>を`MarqueeControl`クラスの宣言。</span><span class="sxs-lookup"><span data-stu-id="ded80-171">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="ded80-172">これには、そのデザイナーを使用したカスタム コントロールが関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="ded80-172">This associates the custom control with its designer.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. <span data-ttu-id="ded80-173">開く、`MarqueeControlRootDesigner`内のソース ファイル、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-173">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="ded80-174">ファイルの上部にある次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ded80-174">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. <span data-ttu-id="ded80-175">宣言を変更する`MarqueeControlRootDesigner`から継承するように、<xref:System.Windows.Forms.Design.DocumentDesigner>クラス。</span><span class="sxs-lookup"><span data-stu-id="ded80-175">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="ded80-176">適用、<xref:System.ComponentModel.ToolboxItemFilterAttribute>デザイナーとの対話を指定する、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-176">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>

     <span data-ttu-id="ded80-177">**注**の定義、 `MarqueeControlRootDesigner` "MarqueeControlLibrary.Design"と呼ばれる名前空間のクラスが囲まれています。</span><span class="sxs-lookup"><span data-stu-id="ded80-177">**Note** The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called "MarqueeControlLibrary.Design."</span></span> <span data-ttu-id="ded80-178">この宣言は配置特別な名前空間でのデザイナーをデザインに関連する型用に予約します。</span><span class="sxs-lookup"><span data-stu-id="ded80-178">This declaration places the designer in a special namespace reserved for design-related types.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. <span data-ttu-id="ded80-179">コンス トラクターを定義、`MarqueeControlRootDesigner`クラス。</span><span class="sxs-lookup"><span data-stu-id="ded80-179">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="ded80-180">挿入、<xref:System.Diagnostics.Trace.WriteLine%2A>コンス トラクター本体のステートメント。</span><span class="sxs-lookup"><span data-stu-id="ded80-180">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="ded80-181">これは、デバッグのための便利になります。</span><span class="sxs-lookup"><span data-stu-id="ded80-181">This will be useful for debugging purposes.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="creating-an-instance-of-your-custom-control"></a><span data-ttu-id="ded80-182">カスタム コントロールのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-182">Creating an Instance of Your Custom Control</span></span>
 <span data-ttu-id="ded80-183">フォーム上にコントロールのインスタンスを配置するカスタム コントロールのデザイン時動作を観察する`MarqueeControlTest`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-183">To observe the custom design-time behavior of your control, you will place an instance of your control on the form in `MarqueeControlTest` project.</span></span>

### <a name="to-create-an-instance-of-your-custom-control"></a><span data-ttu-id="ded80-184">カスタム コントロールのインスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="ded80-184">To create an instance of your custom control</span></span>

1. <span data-ttu-id="ded80-185">新しい追加<xref:System.Windows.Forms.UserControl>項目を`MarqueeControlTest`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-185">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="ded80-186">新しいソース ファイル「により」の基本の名前を付けます</span><span class="sxs-lookup"><span data-stu-id="ded80-186">Give the new source file a base name of "DemoMarqueeControl."</span></span>

2. <span data-ttu-id="ded80-187">開く、`DemoMarqueeControl`ファイル、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-187">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="ded80-188">インポート ファイルの上部にある、`MarqueeControlLibrary`名前空間。</span><span class="sxs-lookup"><span data-stu-id="ded80-188">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>

```vb
Imports MarqueeControlLibrary
```

```csharp
using MarqueeControlLibrary;
```

1. <span data-ttu-id="ded80-189">宣言を変更する`DemoMarqueeControl`から継承するように、`MarqueeControl`クラス。</span><span class="sxs-lookup"><span data-stu-id="ded80-189">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>

2. <span data-ttu-id="ded80-190">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ded80-190">Build the project.</span></span>

3. <span data-ttu-id="ded80-191">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="ded80-191">Open `Form1` in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="ded80-192">検索、**ためコンポーネント** タブで、**ツールボックス**を開きます。</span><span class="sxs-lookup"><span data-stu-id="ded80-192">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="ded80-193">ドラッグ、`DemoMarqueeControl`から、**ツールボックス**フォームにします。</span><span class="sxs-lookup"><span data-stu-id="ded80-193">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="ded80-194">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ded80-194">Build the project.</span></span>

## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="ded80-195">デザイン時のデバッグ プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="ded80-195">Setting Up the Project for Design-Time Debugging</span></span>

<span data-ttu-id="ded80-196">カスタム デザイン時エクスペリエンスを開発しているときに、コントロールとコンポーネントをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ded80-196">When you are developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="ded80-197">デザイン時にデバッグを許可するプロジェクトを設定する簡単な方法があります。</span><span class="sxs-lookup"><span data-stu-id="ded80-197">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="ded80-198">詳細については、「[チュートリアル:デザイン時にフォーム コントロールのカスタムの Windows をデバッグ](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)します。</span><span class="sxs-lookup"><span data-stu-id="ded80-198">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="ded80-199">デザイン時のデバッグ プロジェクトを設定するには</span><span class="sxs-lookup"><span data-stu-id="ded80-199">To set up the project for design-time debugging</span></span>

1. <span data-ttu-id="ded80-200">右クリックし、`MarqueeControlLibrary`順に選択して**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-200">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>

2. <span data-ttu-id="ded80-201">"にプロパティ ページ ダイアログ ボックスで選択、**デバッグ**ページ。</span><span class="sxs-lookup"><span data-stu-id="ded80-201">In the "MarqueeControlLibrary Property Pages" dialog box, select the **Debug** page.</span></span>

3. <span data-ttu-id="ded80-202">**開始動作**セクションで、**外部プログラムの開始**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-202">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="ded80-203">できますので、省略記号をクリックして、Visual Studio の別のインスタンスをデバッグ (![. Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png))、Visual Studio IDE を参照するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ded80-203">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="ded80-204">実行可能ファイルの名前は、devenv.exe と既定の場所にインストールされている場合は、%programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe がそのパスです。</span><span class="sxs-lookup"><span data-stu-id="ded80-204">The name of the executable file is devenv.exe, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

4. <span data-ttu-id="ded80-205">ダイアログ ボックスを閉じるには、[ok] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ded80-205">Click OK to close the dialog box.</span></span>

5. <span data-ttu-id="ded80-206">右クリックし、`MarqueeControlLibrary`プロジェクトし、「設定スタートアップ プロジェクトに」このデバッグ構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ded80-206">Right-click the `MarqueeControlLibrary` project and select "Set as StartUp Project" to enable this debugging configuration.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="ded80-207">チェックポイント</span><span class="sxs-lookup"><span data-stu-id="ded80-207">Checkpoint</span></span>

<span data-ttu-id="ded80-208">カスタム コントロールのデザイン時の動作をデバッグする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="ded80-208">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="ded80-209">デバッグ環境が正しく設定されているを確認したら、カスタム コントロールとカスタム デザイナー間の関連付けをテストします。</span><span class="sxs-lookup"><span data-stu-id="ded80-209">Once you have determined that the debugging environment is set up correctly, you will test the association between the custom control and the custom designer.</span></span>

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="ded80-210">デバッグ環境とデザイナーの関連付けをテストするには</span><span class="sxs-lookup"><span data-stu-id="ded80-210">To test the debugging environment and the designer association</span></span>

1. <span data-ttu-id="ded80-211">開く、`MarqueeControlRootDesigner`内のソース ファイル、**コード エディター**にブレークポイントを配置し、<xref:System.Diagnostics.Trace.WriteLine%2A>ステートメント。</span><span class="sxs-lookup"><span data-stu-id="ded80-211">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>

2. <span data-ttu-id="ded80-212">F5 キーを押して、デバッグ セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="ded80-212">Press F5 to start the debugging session.</span></span> <span data-ttu-id="ded80-213">Visual Studio の新しいインスタンスが作成されたことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ded80-213">Note that a new instance of Visual Studio is created.</span></span>

3. <span data-ttu-id="ded80-214">Visual Studio の新しいインスタンスでは、「ため」ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="ded80-214">In the new instance of Visual Studio, open the "MarqueeControlTest" solution.</span></span> <span data-ttu-id="ded80-215">選択して、ソリューションを簡単に見つけることができます**最近使ったプロジェクト**から、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="ded80-215">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="ded80-216">"MarqueeControlTest.sln"ソリューション ファイルは、最近使用したファイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ded80-216">The "MarqueeControlTest.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="ded80-217">開く、`DemoMarqueeControl`デザイナー。</span><span class="sxs-lookup"><span data-stu-id="ded80-217">Open the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="ded80-218">Visual Studio のデバッグ インスタンスがフォーカスを取得し、ブレークポイントで実行を停止することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ded80-218">Note that the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="ded80-219">F5 キーを押して、デバッグ セッションを続行します。</span><span class="sxs-lookup"><span data-stu-id="ded80-219">Press F5 to continue the debugging session.</span></span>

<span data-ttu-id="ded80-220">この時点では、すべてが、カスタム コントロールおよびそれに関連付けられているカスタム デザイナーを開発、デバッグするためにします。</span><span class="sxs-lookup"><span data-stu-id="ded80-220">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="ded80-221">このチュートリアルの残りの部分は、コントロールと、デザイナーの機能の実装の詳細に集中します。</span><span class="sxs-lookup"><span data-stu-id="ded80-221">The remainder of this walkthrough will concentrate on the details of implementing features of the control and the designer.</span></span>

## <a name="implementing-your-custom-control"></a><span data-ttu-id="ded80-222">カスタム コントロールを実装します。</span><span class="sxs-lookup"><span data-stu-id="ded80-222">Implementing Your Custom Control</span></span>

<span data-ttu-id="ded80-223">`MarqueeControl`は、<xref:System.Windows.Forms.UserControl>少しカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="ded80-223">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="ded80-224">2 つのメソッドを公開します: `Start`、マーキーのアニメーションを開始して`Stop`アニメーションが停止します。</span><span class="sxs-lookup"><span data-stu-id="ded80-224">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="ded80-225">`MarqueeControl`を実装する子コントロールが含まれています、`IMarqueeWidget`インターフェイス、`Start`と`Stop`各子コントロールと呼び出しを列挙、`StartMarquee`と`StopMarquee`メソッドでは、それぞれ、各子コントロール上実装する`IMarqueeWidget`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-225">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>

<span data-ttu-id="ded80-226">外観、`MarqueeBorder`と`MarqueeText`コントロールは、レイアウトに依存ように`MarqueeControl`よりも優先されます、<xref:System.Windows.Forms.Control.OnLayout%2A>メソッドと呼び出し<xref:System.Windows.Forms.Control.PerformLayout%2A>でこの型の子コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-226">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>

<span data-ttu-id="ded80-227">これは、程度、`MarqueeControl`カスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="ded80-227">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="ded80-228">ランタイムの機能を実装して、`MarqueeBorder`と`MarqueeText`コントロール、およびデザイン時機能がによって実装される、`MarqueeBorderDesigner`と`MarqueeControlRootDesigner`クラス。</span><span class="sxs-lookup"><span data-stu-id="ded80-228">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>

### <a name="to-implement-your-custom-control"></a><span data-ttu-id="ded80-229">カスタム コントロールを実装するには</span><span class="sxs-lookup"><span data-stu-id="ded80-229">To implement your custom control</span></span>

1. <span data-ttu-id="ded80-230">開く、`MarqueeControl`内のソース ファイル、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-230">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="ded80-231">実装、`Start`と`Stop`メソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-231">Implement the `Start` and `Stop` methods.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. <span data-ttu-id="ded80-232"><xref:System.Windows.Forms.Control.OnLayout%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ded80-232">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="creating-a-child-control-for-your-custom-control"></a><span data-ttu-id="ded80-233">カスタム コントロールの子コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-233">Creating a Child Control for Your Custom Control</span></span>

<span data-ttu-id="ded80-234">`MarqueeControl` 2 種類の子コントロールをホストする:`MarqueeBorder`コントロールと`MarqueeText`コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-234">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>

- <span data-ttu-id="ded80-235">`MarqueeBorder`:このコントロールは、「ライト」周囲の境界線を描画します。</span><span class="sxs-lookup"><span data-stu-id="ded80-235">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="ded80-236">ライトは、境界線を移動するように表示されるように、シーケンスで点滅します。</span><span class="sxs-lookup"><span data-stu-id="ded80-236">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="ded80-237">ライトが点滅する速度がという名前のプロパティによって制御される`UpdatePeriod`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-237">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="ded80-238">その他のいくつかのカスタム プロパティは、他のコントロールの外観を決定します。</span><span class="sxs-lookup"><span data-stu-id="ded80-238">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="ded80-239">2 つのメソッドと呼ばれる`StartMarquee`と`StopMarquee`アニメーションが開始し、停止を制御します。</span><span class="sxs-lookup"><span data-stu-id="ded80-239">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>

- <span data-ttu-id="ded80-240">`MarqueeText`:このコントロールは、点滅している文字列を描画します。</span><span class="sxs-lookup"><span data-stu-id="ded80-240">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="ded80-241">ように、`MarqueeBorder`コントロール、テキストが点滅速度はによって制御される、`UpdatePeriod`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ded80-241">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="ded80-242">`MarqueeText`コントロールもあります、`StartMarquee`と`StopMarquee`で共通のメソッド、`MarqueeBorder`コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-242">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>

<span data-ttu-id="ded80-243">デザイン時に、`MarqueeControlRootDesigner`これら 2 つの制御の型に追加することができます、`MarqueeControl`の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="ded80-243">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>

<span data-ttu-id="ded80-244">2 つのコントロールの一般的な機能を考慮にというインターフェイス`IMarqueeWidget`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-244">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="ded80-245">これにより、`MarqueeControl`を範囲に関連する子コントロールを検出し、特別な処理を付与します。</span><span class="sxs-lookup"><span data-stu-id="ded80-245">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>

<span data-ttu-id="ded80-246">定期的なアニメーション機能を実装するには、使用<xref:System.ComponentModel.BackgroundWorker>オブジェクトから、<xref:System.ComponentModel?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="ded80-246">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="ded80-247">使って<xref:System.Windows.Forms.Timer>オブジェクトが多く`IMarqueeWidget`オブジェクトが存在する、1 つの UI スレッドが、アニメーションを進めることができません。</span><span class="sxs-lookup"><span data-stu-id="ded80-247">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>

### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="ded80-248">カスタム コントロールの子コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="ded80-248">To create a child control for your custom control</span></span>

1. <span data-ttu-id="ded80-249">クラスの新しいアイテムを追加、`MarqueeControlLibrary`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-249">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ded80-250">新しいソース ファイル"IMarqueeWidget"の基本の名前を付けます</span><span class="sxs-lookup"><span data-stu-id="ded80-250">Give the new source file a base name of "IMarqueeWidget."</span></span>

2. <span data-ttu-id="ded80-251">開く、`IMarqueeWidget`内のソース ファイル、**コード エディター**から宣言を変更して`class`に`interface`:</span><span class="sxs-lookup"><span data-stu-id="ded80-251">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. <span data-ttu-id="ded80-252">次のコードを追加、 `IMarqueeWidget` 2 つの方法と、マーキー アニメーションを操作するプロパティを公開するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ded80-252">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. <span data-ttu-id="ded80-253">新しい追加**カスタム コントロール**項目を`MarqueeControlLibrary`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-253">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ded80-254">新しいソース ファイル「ただし」の基本の名前を付けます</span><span class="sxs-lookup"><span data-stu-id="ded80-254">Give the new source file a base name of "MarqueeText."</span></span>

5. <span data-ttu-id="ded80-255">ドラッグ、<xref:System.ComponentModel.BackgroundWorker>コンポーネントから、**ツールボックス**上に、`MarqueeText`コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-255">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="ded80-256">このコンポーネントを許可するが、`MarqueeText`自体を非同期的に更新するコントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-256">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>

6. <span data-ttu-id="ded80-257">[プロパティ] ウィンドウで次のように設定します。、<xref:System.ComponentModel.BackgroundWorker>コンポーネントの`WorkerReportsProgress`と<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>プロパティ`true`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-257">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="ded80-258">これらの設定により、<xref:System.ComponentModel.BackgroundWorker>定期的に発生させるコンポーネント、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベントと非同期更新をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="ded80-258">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="ded80-259">詳細については、次を参照してください。 [BackgroundWorker コンポーネント](backgroundworker-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="ded80-259">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

7. <span data-ttu-id="ded80-260">開く、`MarqueeText`内のソース ファイル、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-260">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="ded80-261">ファイルの上部にある次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ded80-261">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. <span data-ttu-id="ded80-262">宣言を変更する`MarqueeText`から継承する<xref:System.Windows.Forms.Label>を実装して、`IMarqueeWidget`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ded80-262">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. <span data-ttu-id="ded80-263">公開したプロパティに対応するインスタンス変数を宣言し、それらをコンス トラクターで初期化します。</span><span class="sxs-lookup"><span data-stu-id="ded80-263">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="ded80-264">`isLit`フィールドかどうかをテキストで指定された色で描画する、`LightColor`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ded80-264">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. <span data-ttu-id="ded80-265">`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="ded80-265">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="ded80-266">`StartMarquee`と`StopMarquee`メソッドを呼び出す、<xref:System.ComponentModel.BackgroundWorker>コンポーネントの<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>と<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>開始およびアニメーションを停止するメソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-266">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="ded80-267"><xref:System.ComponentModel.CategoryAttribute.Category%2A>と<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>属性に適用されます、 `UpdatePeriod` 「マーキー」と呼ばれる [プロパティ] ウィンドウのカスタム セクションに表示されるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ded80-267">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. <span data-ttu-id="ded80-268">プロパティ アクセサーを実装します。</span><span class="sxs-lookup"><span data-stu-id="ded80-268">Implement the property accessors.</span></span> <span data-ttu-id="ded80-269">クライアントに 2 つのプロパティを公開:`LightColor`と`DarkColor`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-269">You will expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="ded80-270"><xref:System.ComponentModel.CategoryAttribute.Category%2A>と<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>属性はこれらのプロパティに適用されるため、「マーキー。」と呼ばれる [プロパティ] ウィンドウのカスタムのセクションでプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ded80-270">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. <span data-ttu-id="ded80-271">ハンドラーを実装、<xref:System.ComponentModel.BackgroundWorker>コンポーネントの<xref:System.ComponentModel.BackgroundWorker.DoWork>と<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="ded80-271">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="ded80-272"><xref:System.ComponentModel.BackgroundWorker.DoWork>によって指定されたミリ秒数のイベント ハンドラーがスリープ状態`UpdatePeriod`が発生し、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベント、コードが呼び出すことによって、アニメーションを停止するまで<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ded80-272">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="ded80-273"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベント ハンドラーは、テキストの点滅の外観を与える、明暗の状態を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="ded80-273">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. <span data-ttu-id="ded80-274">上書き、<xref:System.Windows.Forms.Control.OnPaint%2A>アニメーションを有効にするメソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-274">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. <span data-ttu-id="ded80-275">F6 キーを押してソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ded80-275">Press F6 to build the solution.</span></span>

## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="ded80-276">MarqueeBorder 子コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-276">Create the MarqueeBorder Child Control</span></span>

<span data-ttu-id="ded80-277">`MarqueeBorder`コントロールがやや高度な`MarqueeText`コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-277">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="ded80-278">その他のプロパティと、アニメーションがある、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドは、複雑です。</span><span class="sxs-lookup"><span data-stu-id="ded80-278">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="ded80-279">原則として、これとよく似ていますが、`MarqueeText`コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-279">In principle, it is quite similar to the `MarqueeText` control.</span></span>

<span data-ttu-id="ded80-280">`MarqueeBorder`コントロールで子コントロールを持つことができます、注意する必要がある<xref:System.Windows.Forms.Control.Layout>イベント。</span><span class="sxs-lookup"><span data-stu-id="ded80-280">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>

### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="ded80-281">MarqueeBorder コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="ded80-281">To create the MarqueeBorder control</span></span>

1. <span data-ttu-id="ded80-282">新しい追加**カスタム コントロール**項目を`MarqueeControlLibrary`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-282">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ded80-283">新しいソース ファイル"MarqueeBorder"の基本の名前を付けます</span><span class="sxs-lookup"><span data-stu-id="ded80-283">Give the new source file a base name of "MarqueeBorder."</span></span>

2. <span data-ttu-id="ded80-284">ドラッグ、<xref:System.ComponentModel.BackgroundWorker>コンポーネントから、**ツールボックス**上に、`MarqueeBorder`コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-284">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="ded80-285">このコンポーネントを許可するが、`MarqueeBorder`自体を非同期的に更新するコントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-285">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>

3. <span data-ttu-id="ded80-286">[プロパティ] ウィンドウで次のように設定します。、<xref:System.ComponentModel.BackgroundWorker>コンポーネントの`WorkerReportsProgress`と<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>プロパティ`true`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-286">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="ded80-287">これらの設定により、<xref:System.ComponentModel.BackgroundWorker>定期的に発生させるコンポーネント、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベントと非同期更新をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="ded80-287">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="ded80-288">詳細については、次を参照してください。 [BackgroundWorker コンポーネント](backgroundworker-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="ded80-288">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

4. <span data-ttu-id="ded80-289">[プロパティ] ウィンドウで、イベント ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ded80-289">In the Properties window, click the Events button.</span></span> <span data-ttu-id="ded80-290">ハンドラーのアタッチ、<xref:System.ComponentModel.BackgroundWorker.DoWork>と<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="ded80-290">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

5. <span data-ttu-id="ded80-291">開く、`MarqueeBorder`内のソース ファイル、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-291">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="ded80-292">ファイルの上部にある次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ded80-292">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. <span data-ttu-id="ded80-293">宣言を変更する`MarqueeBorder`から継承する<xref:System.Windows.Forms.Panel>を実装して、`IMarqueeWidget`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ded80-293">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. <span data-ttu-id="ded80-294">管理するための 2 つの列挙型を宣言、`MarqueeBorder`コントロールの状態:`MarqueeSpinDirection`をライト「回転」境界線の方向を決定して`MarqueeLightShape`、(正方形または循環) のライトの形状を決定します。</span><span class="sxs-lookup"><span data-stu-id="ded80-294">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="ded80-295">配置する前にこれらの宣言、`MarqueeBorder`クラスの宣言。</span><span class="sxs-lookup"><span data-stu-id="ded80-295">Place these declarations before the `MarqueeBorder` class declaration.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. <span data-ttu-id="ded80-296">公開したプロパティに対応するインスタンス変数を宣言し、それらをコンス トラクターで初期化します。</span><span class="sxs-lookup"><span data-stu-id="ded80-296">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. <span data-ttu-id="ded80-297">`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="ded80-297">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="ded80-298">`StartMarquee`と`StopMarquee`メソッドを呼び出す、<xref:System.ComponentModel.BackgroundWorker>コンポーネントの<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>と<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>開始およびアニメーションを停止するメソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-298">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="ded80-299">`MarqueeBorder`コントロールで子コントロールを含めることができます、`StartMarquee`メソッドは、すべての子コントロールと呼び出しを列挙します。`StartMarquee`を実装するもので`IMarqueeWidget`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-299">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="ded80-300">`StopMarquee`メソッドのような実装があります。</span><span class="sxs-lookup"><span data-stu-id="ded80-300">The `StopMarquee` method has a similar implementation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. <span data-ttu-id="ded80-301">プロパティ アクセサーを実装します。</span><span class="sxs-lookup"><span data-stu-id="ded80-301">Implement the property accessors.</span></span> <span data-ttu-id="ded80-302">`MarqueeBorder`コントロールの外観を制御するためのいくつかのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ded80-302">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. <span data-ttu-id="ded80-303">ハンドラーを実装、<xref:System.ComponentModel.BackgroundWorker>コンポーネントの<xref:System.ComponentModel.BackgroundWorker.DoWork>と<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="ded80-303">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="ded80-304"><xref:System.ComponentModel.BackgroundWorker.DoWork>によって指定されたミリ秒数のイベント ハンドラーがスリープ状態`UpdatePeriod`が発生し、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベント、コードが呼び出すことによって、アニメーションを停止するまで<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ded80-304">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="ded80-305"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベント ハンドラーは、元となる、他のライトの/暗状態を判断は、"base"光と呼び出しの位置をインクリメント、<xref:System.Windows.Forms.Control.Refresh%2A>メソッドを呼び出すと、コントロール自体を再描画します。</span><span class="sxs-lookup"><span data-stu-id="ded80-305">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. <span data-ttu-id="ded80-306">ヘルパー メソッドを実装`IsLit`と`DrawLight`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-306">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>

    <span data-ttu-id="ded80-307">`IsLit`メソッドは、指定された位置にライトの色を決定します。</span><span class="sxs-lookup"><span data-stu-id="ded80-307">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="ded80-308">指定された色では「点灯」ライトが描画される、`LightColor`プロパティ、および [ダーク] にあるものがで指定された色で描画される、`DarkColor`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ded80-308">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>

    <span data-ttu-id="ded80-309">`DrawLight`メソッドが適切な色、形状、および位置を使用して、ライトを描画します。</span><span class="sxs-lookup"><span data-stu-id="ded80-309">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. <span data-ttu-id="ded80-310">上書き、<xref:System.Windows.Forms.Control.OnLayout%2A>と<xref:System.Windows.Forms.Control.OnPaint%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-310">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>

    <span data-ttu-id="ded80-311"><xref:System.Windows.Forms.Control.OnPaint%2A>メソッドは、ライトの端を描画、`MarqueeBorder`コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-311">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>

    <span data-ttu-id="ded80-312"><xref:System.Windows.Forms.Control.OnPaint%2A>メソッドの大きさによって異なります、`MarqueeBorder`コントロール、レイアウトが変更されるたびに呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ded80-312">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="ded80-313">これを実現するにはオーバーライド<xref:System.Windows.Forms.Control.OnLayout%2A>を呼び出すと<xref:System.Windows.Forms.Control.Refresh%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ded80-313">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="ded80-314">シャドウとフィルターのプロパティにカスタム デザイナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-314">Creating a Custom Designer to Shadow and Filter Properties</span></span>

<span data-ttu-id="ded80-315">`MarqueeControlRootDesigner`クラスがルート デザイナーの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="ded80-315">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="ded80-316">動作するだけでなく、このデザイナー、 `MarqueeControl`、カスタム デザイナーに具体的には関連付けられている必要があります、`MarqueeBorder`コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-316">In addition to this designer, which operates on the `MarqueeControl`, you will need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="ded80-317">このデザイナーは、カスタム ルート デザイナーのコンテキストで適切なカスタム動作を提供します。</span><span class="sxs-lookup"><span data-stu-id="ded80-317">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>

<span data-ttu-id="ded80-318">具体的には、 `MarqueeBorderDesigner` 「シャドウ」され、特定のプロパティをフィルター処理、`MarqueeBorder`コントロール、デザイン環境との相互作用を変更します。</span><span class="sxs-lookup"><span data-stu-id="ded80-318">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>

<span data-ttu-id="ded80-319">コンポーネントのプロパティ アクセサーの呼び出しを受け取ることは「シャドウ」と呼ばれます</span><span class="sxs-lookup"><span data-stu-id="ded80-319">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="ded80-320">デザイナーによって、ユーザーによって設定された値を追跡し、必要に応じてその値をデザインするコンポーネントに渡します。</span><span class="sxs-lookup"><span data-stu-id="ded80-320">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>

<span data-ttu-id="ded80-321">この例で、<xref:System.Windows.Forms.Control.Visible%2A>と<xref:System.Windows.Forms.Control.Enabled%2A>でプロパティをシャドウは、`MarqueeBorderDesigner`からユーザーを防ぐことが、`MarqueeBorder`コントロールを非表示またはデザイン時に無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ded80-321">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>

<span data-ttu-id="ded80-322">デザイナーを追加およびプロパティを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="ded80-322">Designers can also add and remove properties.</span></span> <span data-ttu-id="ded80-323">この例で、 <xref:System.Windows.Forms.Control.Padding%2A> 、デザイン時にプロパティを削除は、`MarqueeBorder`コントロールで指定されたライトのサイズに基づいての余白をプログラムで設定する、`LightSize`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ded80-323">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>

<span data-ttu-id="ded80-324">基本クラス`MarqueeBorderDesigner`は<xref:System.ComponentModel.Design.ComponentDesigner>属性、プロパティ、およびデザイン時にコントロールによって公開されるイベントを変更するメソッドを持ちます。</span><span class="sxs-lookup"><span data-stu-id="ded80-324">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

<span data-ttu-id="ded80-325">これらのメソッドを使用して、コンポーネントのパブリック インターフェイスを変更する場合は、これらの規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ded80-325">When changing the public interface of a component using these methods, you must follow these rules:</span></span>

- <span data-ttu-id="ded80-326">項目の追加または削除、`PreFilter`メソッドのみ</span><span class="sxs-lookup"><span data-stu-id="ded80-326">Add or remove items in the `PreFilter` methods only</span></span>

- <span data-ttu-id="ded80-327">既存の項目を変更、`PostFilter`メソッドのみ</span><span class="sxs-lookup"><span data-stu-id="ded80-327">Modify existing items in the `PostFilter` methods only</span></span>

- <span data-ttu-id="ded80-328">常に最初に呼び出す基本の実装、`PreFilter`メソッド</span><span class="sxs-lookup"><span data-stu-id="ded80-328">Always call the base implementation first in the `PreFilter` methods</span></span>

- <span data-ttu-id="ded80-329">基本実装を最終呼び出す常に、`PostFilter`メソッド</span><span class="sxs-lookup"><span data-stu-id="ded80-329">Always call the base implementation last in the `PostFilter` methods</span></span>

<span data-ttu-id="ded80-330">これらの規則に従うことにより、すべてのデザイナー、デザイン時環境であるように設計されているすべてのコンポーネントの一貫性のあるビュー。</span><span class="sxs-lookup"><span data-stu-id="ded80-330">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>

<span data-ttu-id="ded80-331"><xref:System.ComponentModel.Design.ComponentDesigner>クラスの特定のインスタンス変数を作成する必要があるが、影付きのプロパティの値を管理するためのディクショナリを提供します。</span><span class="sxs-lookup"><span data-stu-id="ded80-331">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="ded80-332">シャドウとフィルターのプロパティをカスタム デザイナーを作成するには</span><span class="sxs-lookup"><span data-stu-id="ded80-332">To create a custom designer to shadow and filter properties</span></span>

1. <span data-ttu-id="ded80-333">右クリックし、**デザイン**フォルダーと新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="ded80-333">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="ded80-334">ソース ファイル"MarqueeBorderDesigner"の基本の名前を付けます</span><span class="sxs-lookup"><span data-stu-id="ded80-334">Give the source file a base name of "MarqueeBorderDesigner."</span></span>

2. <span data-ttu-id="ded80-335">開く、`MarqueeBorderDesigner`内のソース ファイル、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-335">Open the `MarqueeBorderDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="ded80-336">ファイルの上部にある次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ded80-336">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. <span data-ttu-id="ded80-337">宣言を変更する`MarqueeBorderDesigner`から継承する<xref:System.Windows.Forms.Design.ParentControlDesigner>します。</span><span class="sxs-lookup"><span data-stu-id="ded80-337">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>

    <span data-ttu-id="ded80-338">`MarqueeBorder`コントロールで子コントロールを含めることができます`MarqueeBorderDesigner`から継承<xref:System.Windows.Forms.Design.ParentControlDesigner>親子の対話を処理します。</span><span class="sxs-lookup"><span data-stu-id="ded80-338">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. <span data-ttu-id="ded80-339">基本実装をオーバーライド<xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ded80-339">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. <span data-ttu-id="ded80-340">
  <xref:System.Windows.Forms.Control.Enabled%2A> プロパティと <xref:System.Windows.Forms.Control.Visible%2A> プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="ded80-340">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="ded80-341">これらの実装では、コントロールのプロパティをシャドウします。</span><span class="sxs-lookup"><span data-stu-id="ded80-341">These implementations shadow the control's properties.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handling-component-changes"></a><span data-ttu-id="ded80-342">コンポーネントの変更の処理</span><span class="sxs-lookup"><span data-stu-id="ded80-342">Handling Component Changes</span></span>
 <span data-ttu-id="ded80-343">`MarqueeControlRootDesigner`クラスのカスタム デザイン時エクスペリエンスを提供する、`MarqueeControl`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="ded80-343">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="ded80-344">デザイン時の機能のほとんどが継承、<xref:System.Windows.Forms.Design.DocumentDesigner>クラスは 2 つの特定のカスタマイズを実装するコードを: コンポーネントの変更の処理とデザイナー動詞を追加します。</span><span class="sxs-lookup"><span data-stu-id="ded80-344">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class; your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>

 <span data-ttu-id="ded80-345">ユーザー設計として、 `MarqueeControl` 、インスタンスのルート デザイナーに変更の追跡は、`MarqueeControl`とその子コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-345">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="ded80-346">便利なサービス、デザイン時環境では<xref:System.ComponentModel.Design.IComponentChangeService>コンポーネントの状態に変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="ded80-346">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>

 <span data-ttu-id="ded80-347">使用環境を照会することによってこのサービスへの参照を取得する、<xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-347">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="ded80-348">クエリが成功した場合、デザイナーがのハンドラーをアタッチできます、<xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged>イベントと、デザイン時に一貫性のある状態を維持するために必要なタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="ded80-348">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>

 <span data-ttu-id="ded80-349">場合、`MarqueeControlRootDesigner`呼び出しは、クラス、<xref:System.Windows.Forms.Control.Refresh%2A>各`IMarqueeWidget`オブジェクトに含まれる、`MarqueeControl`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-349">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="ded80-350">これにより、`IMarqueeWidget`オブジェクトにプロパティがその親のようなときに適切に再描画<xref:System.Windows.Forms.Control.Size%2A>変更されます。</span><span class="sxs-lookup"><span data-stu-id="ded80-350">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>

### <a name="to-handle-component-changes"></a><span data-ttu-id="ded80-351">コンポーネントの変更を処理するには</span><span class="sxs-lookup"><span data-stu-id="ded80-351">To handle component changes</span></span>

1. <span data-ttu-id="ded80-352">開く、`MarqueeControlRootDesigner`内のソース ファイル、**コード エディター**をオーバーライドし、<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-352">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="ded80-353">基本実装を呼び出す<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>に対してクエリを実行し、<xref:System.ComponentModel.Design.IComponentChangeService>します。</span><span class="sxs-lookup"><span data-stu-id="ded80-353">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. <span data-ttu-id="ded80-354">実装、<xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="ded80-354">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="ded80-355">送信側のコンポーネントの種類、テストの場合、 `IMarqueeWidget`、呼び出すその<xref:System.Windows.Forms.Control.Refresh%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-355">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="adding-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="ded80-356">デザイナー動詞をカスタム デザイナーに追加します。</span><span class="sxs-lookup"><span data-stu-id="ded80-356">Adding Designer Verbs to your Custom Designer</span></span>

<span data-ttu-id="ded80-357">デザイナー動詞は、イベント ハンドラーにリンクされているメニュー コマンドです。</span><span class="sxs-lookup"><span data-stu-id="ded80-357">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="ded80-358">デザイナー動詞は、デザイン時コンポーネントのショートカット メニューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ded80-358">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="ded80-359">詳細については、「 <xref:System.ComponentModel.Design.DesignerVerb> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ded80-359">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>

<span data-ttu-id="ded80-360">2 つのデザイナー動詞は、デザイナーに追加されます。**テスト実行**と**テストを停止**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-360">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="ded80-361">これらの動詞の実行時の動作を表示することにより、`MarqueeControl`デザイン時にします。</span><span class="sxs-lookup"><span data-stu-id="ded80-361">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="ded80-362">これらの動詞に追加されます、`MarqueeControlRootDesigner`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-362">These verbs will be added to the `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="ded80-363">ときに**テストの実行**が呼び出されると、動詞のイベント ハンドラーが呼び出されます、`StartMarquee`メソッドを`MarqueeControl`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-363">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="ded80-364">ときに**テストの停止**が呼び出されると、動詞のイベント ハンドラーが呼び出されます、`StopMarquee`メソッドを`MarqueeControl`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-364">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="ded80-365">実装、`StartMarquee`と`StopMarquee`メソッドが格納されているコントロールを実装するのにこれらのメソッドを呼び出す`IMarqueeWidget`、すべて含まれている`IMarqueeWidget`コントロールがテストに参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ded80-365">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>

### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="ded80-366">デザイナー動詞をカスタム デザイナーに追加するには</span><span class="sxs-lookup"><span data-stu-id="ded80-366">To add designer verbs to your custom designers</span></span>

1. <span data-ttu-id="ded80-367">`MarqueeControlRootDesigner`クラスでという名前のイベント ハンドラーを追加`OnVerbRunTest`と`OnVerbStopTest`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-367">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. <span data-ttu-id="ded80-368">これらのイベント ハンドラーを対応するデザイナー動詞に接続します。</span><span class="sxs-lookup"><span data-stu-id="ded80-368">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="ded80-369">`MarqueeControlRootDesigner` 継承、<xref:System.ComponentModel.Design.DesignerVerbCollection>その基本クラスから。</span><span class="sxs-lookup"><span data-stu-id="ded80-369">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="ded80-370">2 つ作成する新しい<xref:System.ComponentModel.Design.DesignerVerb>オブジェクトし、では、このコレクションに追加、<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-370">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="creating-a-custom-uitypeeditor"></a><span data-ttu-id="ded80-371">カスタムの UITypeEditor を作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-371">Creating a Custom UITypeEditor</span></span>

<span data-ttu-id="ded80-372">ユーザーのカスタム デザイン時エクスペリエンスを作成するときに、[プロパティ] ウィンドウでカスタム操作を作成することが望ましいは多くの場合。</span><span class="sxs-lookup"><span data-stu-id="ded80-372">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="ded80-373">これを実現するには作成を<xref:System.Drawing.Design.UITypeEditor>します。</span><span class="sxs-lookup"><span data-stu-id="ded80-373">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span> <span data-ttu-id="ded80-374">詳細については、「[方法 :UI 型エディターを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120))します。</span><span class="sxs-lookup"><span data-stu-id="ded80-374">For more information, see [How to: Create a UI Type Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120)).</span></span>

<span data-ttu-id="ded80-375">`MarqueeBorder`コントロールのプロパティ ウィンドウでいくつかのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="ded80-375">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="ded80-376">これらのプロパティの 2 つ`MarqueeSpinDirection`と`MarqueeLightShape`列挙体によって表されます。</span><span class="sxs-lookup"><span data-stu-id="ded80-376">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="ded80-377">UI 型エディターでは、使用方法を示す、`MarqueeLightShape`プロパティが関連付けられている必要があります<xref:System.Drawing.Design.UITypeEditor>クラス。</span><span class="sxs-lookup"><span data-stu-id="ded80-377">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>

### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="ded80-378">カスタム UI 型エディターを作成するには</span><span class="sxs-lookup"><span data-stu-id="ded80-378">To create a custom UI type editor</span></span>

1. <span data-ttu-id="ded80-379">開く、`MarqueeBorder`内のソース ファイル、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-379">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>

2. <span data-ttu-id="ded80-380">定義で、`MarqueeBorder`クラスと呼ばれるクラスを宣言`LightShapeEditor`から派生した<xref:System.Drawing.Design.UITypeEditor>します。</span><span class="sxs-lookup"><span data-stu-id="ded80-380">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. <span data-ttu-id="ded80-381">宣言、<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>というインスタンス変数`editorService`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-381">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. <span data-ttu-id="ded80-382"><xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ded80-382">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="ded80-383">この実装を返します<xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>、デザイン環境を表示する方法について説明する、`LightShapeEditor`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-383">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. <span data-ttu-id="ded80-384"><xref:System.Drawing.Design.UITypeEditor.EditValue%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ded80-384">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="ded80-385">この実装はクエリのデザイン環境、<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-385">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="ded80-386">成功すると、作成、`LightShapeSelectionControl`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-386">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="ded80-387"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>を開始するメソッドが呼び出される、`LightShapeEditor`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-387">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="ded80-388">この呼び出しからの戻り値は、デザイン環境に返されます。</span><span class="sxs-lookup"><span data-stu-id="ded80-388">The return value from this invocation is returned to the design environment.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="ded80-389">カスタム ビュー コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-389">Creating a View Control for your Custom UITypeEditor</span></span>

1. <span data-ttu-id="ded80-390">`MarqueeLightShape`プロパティには、2 つの種類のライトの図形がサポートしています:`Square`と`Circle`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-390">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="ded80-391">[プロパティ] ウィンドウで、これらの値をグラフィカルに表示するためだけに使用するカスタム コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ded80-391">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="ded80-392">このカスタム コントロールで使用される、<xref:System.Drawing.Design.UITypeEditor>プロパティ ウィンドウと対話します。</span><span class="sxs-lookup"><span data-stu-id="ded80-392">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="ded80-393">カスタム UI 型エディターのビュー コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="ded80-393">To create a view control for your custom UI type editor</span></span>

1. <span data-ttu-id="ded80-394">新しい追加<xref:System.Windows.Forms.UserControl>項目を`MarqueeControlLibrary`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-394">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ded80-395">新しいソース ファイル"LightShapeSelectionControl"の基本の名前を付けます</span><span class="sxs-lookup"><span data-stu-id="ded80-395">Give the new source file a base name of "LightShapeSelectionControl."</span></span>

2. <span data-ttu-id="ded80-396">2 つをドラッグして<xref:System.Windows.Forms.Panel>コントロールを**ツールボックス**上に、`LightShapeSelectionControl`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-396">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="ded80-397">名前を付けます`squarePanel`と`circlePanel`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-397">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="ded80-398">サイド バイ サイドそれらを配置します。</span><span class="sxs-lookup"><span data-stu-id="ded80-398">Arrange them side by side.</span></span> <span data-ttu-id="ded80-399">設定、<xref:System.Windows.Forms.Control.Size%2A>両方のプロパティ<xref:System.Windows.Forms.Panel>にコントロールを (60, 60)。</span><span class="sxs-lookup"><span data-stu-id="ded80-399">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to (60, 60).</span></span> <span data-ttu-id="ded80-400">設定、<xref:System.Windows.Forms.Control.Location%2A>のプロパティ、`squarePanel`への制御 (8, 10)。</span><span class="sxs-lookup"><span data-stu-id="ded80-400">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to (8, 10).</span></span> <span data-ttu-id="ded80-401">設定、<xref:System.Windows.Forms.Control.Location%2A>のプロパティ、`circlePanel`への制御 (80, 10)。</span><span class="sxs-lookup"><span data-stu-id="ded80-401">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to (80, 10).</span></span> <span data-ttu-id="ded80-402">最後に、設定、<xref:System.Windows.Forms.Control.Size%2A>のプロパティ、`LightShapeSelectionControl`に (150, 80)。</span><span class="sxs-lookup"><span data-stu-id="ded80-402">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to (150, 80).</span></span>

3. <span data-ttu-id="ded80-403">開く、`LightShapeSelectionControl`内のソース ファイル、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ded80-403">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="ded80-404">インポート ファイルの上部にある、<xref:System.Windows.Forms.Design?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="ded80-404">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>

```vb
Imports System.Windows.Forms.Design
```

```csharp
using System.Windows.Forms.Design;
```

1. <span data-ttu-id="ded80-405">実装<xref:System.Windows.Forms.Control.Click>のイベント ハンドラー、`squarePanel`と`circlePanel`コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-405">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="ded80-406">これらのメソッドを呼び出す<xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A>カスタムを終了する<xref:System.Drawing.Design.UITypeEditor>セッションを編集します。</span><span class="sxs-lookup"><span data-stu-id="ded80-406">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

2. <span data-ttu-id="ded80-407">宣言、<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>というインスタンス変数`editorService`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-407">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

```vb
Private editorService As IWindowsFormsEditorService
```

```csharp
private IWindowsFormsEditorService editorService;
```

1. <span data-ttu-id="ded80-408">宣言を`MarqueeLightShape`というインスタンス変数`lightShapeValue`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-408">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

2. <span data-ttu-id="ded80-409">`LightShapeSelectionControl`コンス トラクター、アタッチ、<xref:System.Windows.Forms.Control.Click>イベント ハンドラーを`squarePanel`と`circlePanel`コントロールの<xref:System.Windows.Forms.Control.Click>イベント。</span><span class="sxs-lookup"><span data-stu-id="ded80-409">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="ded80-410">割り当てるコンス トラクター オーバー ロードを定義することも、`MarqueeLightShape`値には、デザイン環境から、`lightShapeValue`フィールド。</span><span class="sxs-lookup"><span data-stu-id="ded80-410">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

3. <span data-ttu-id="ded80-411"><xref:System.ComponentModel.Component.Dispose%2A>メソッド、デタッチ、<xref:System.Windows.Forms.Control.Click>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="ded80-411">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

4. <span data-ttu-id="ded80-412">**ソリューション エクスプローラー**で、**[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ded80-412">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="ded80-413">LightShapeSelectionControl.Designer.cs または LightShapeSelectionControl.Designer.vb ファイルを開きの既定の定義を削除、<xref:System.ComponentModel.Component.Dispose%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="ded80-413">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>

5. <span data-ttu-id="ded80-414">
  `LightShape\` プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="ded80-414">Implement the `LightShape` property.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

6. <span data-ttu-id="ded80-415"><xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ded80-415">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ded80-416">この実装は、塗りつぶされた四角形と円を描画します。</span><span class="sxs-lookup"><span data-stu-id="ded80-416">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="ded80-417">また、どちらか 1 つの図形の周りに罫線を描画することで、選択した値を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="ded80-417">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="testing-your-custom-control-in-the-designer"></a><span data-ttu-id="ded80-418">デザイナーでカスタム コントロールのテスト</span><span class="sxs-lookup"><span data-stu-id="ded80-418">Testing your Custom Control in the Designer</span></span>

<span data-ttu-id="ded80-419">この時点では、ビルドすることができます、`MarqueeControlLibrary`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded80-419">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ded80-420">継承するコントロールを作成して、実装をテスト、`MarqueeControl`クラスおよびフォーム上で使用します。</span><span class="sxs-lookup"><span data-stu-id="ded80-420">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>

### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="ded80-421">カスタムを作成するには</span><span class="sxs-lookup"><span data-stu-id="ded80-421">To create a custom MarqueeControl implementation</span></span>

1. <span data-ttu-id="ded80-422">Windows フォーム デザイナーで `DemoMarqueeControl` を開きます。</span><span class="sxs-lookup"><span data-stu-id="ded80-422">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="ded80-423">このインスタンスを作成、`DemoMarqueeControl`を入力し、インスタンス内の表示、`MarqueeControlRootDesigner`型。</span><span class="sxs-lookup"><span data-stu-id="ded80-423">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>

2. <span data-ttu-id="ded80-424">**ツールボックス**、オープン、**にコンポーネント**タブ。表示されます、`MarqueeBorder`と`MarqueeText`コントロールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ded80-424">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>

3. <span data-ttu-id="ded80-425">インスタンスをドラッグして、`MarqueeBorder`コントロールを`DemoMarqueeControl`デザイン サーフェイス。</span><span class="sxs-lookup"><span data-stu-id="ded80-425">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="ded80-426">このドッキング`MarqueeBorder`コントロールを親コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-426">Dock this `MarqueeBorder` control to the parent control.</span></span>

4. <span data-ttu-id="ded80-427">インスタンスをドラッグして、`MarqueeText`コントロールを`DemoMarqueeControl`デザイン サーフェイス。</span><span class="sxs-lookup"><span data-stu-id="ded80-427">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>

5. <span data-ttu-id="ded80-428">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ded80-428">Build the solution.</span></span>

6. <span data-ttu-id="ded80-429">右クリックし、`DemoMarqueeControl`ショートカット メニューを選択し、**テストの実行**アニメーションを開始するにはオプションです。</span><span class="sxs-lookup"><span data-stu-id="ded80-429">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="ded80-430">クリックして**テストの停止**アニメーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="ded80-430">Click **Stop Test** to stop the animation.</span></span>

7. <span data-ttu-id="ded80-431">デザイン ビューで **[Form1]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="ded80-431">Open **Form1** in Design view.</span></span>

8. <span data-ttu-id="ded80-432">2 つ配置<xref:System.Windows.Forms.Button>フォーム上のコントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-432">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="ded80-433">という名前を付けます`startButton`と`stopButton`、変更して、<xref:System.Windows.Forms.Control.Text%2A>プロパティ値を**開始**と**停止**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="ded80-433">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>

9. <span data-ttu-id="ded80-434">実装<xref:System.Windows.Forms.Control.Click>両方のイベント ハンドラー<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="ded80-434">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>

10. <span data-ttu-id="ded80-435">**ツールボックス**、オープン、**ためコンポーネント**タブ。表示されます、`DemoMarqueeControl`選択できます。</span><span class="sxs-lookup"><span data-stu-id="ded80-435">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>

11. <span data-ttu-id="ded80-436">インスタンスをドラッグ`DemoMarqueeControl`上に、 **Form1**デザイン サーフェイス。</span><span class="sxs-lookup"><span data-stu-id="ded80-436">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>

12. <span data-ttu-id="ded80-437"><xref:System.Windows.Forms.Control.Click> 、イベント ハンドラーを呼び出す、`Start`と`Stop`メソッド、`DemoMarqueeControl`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-437">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>

```vb
Private Sub startButton_Click(sender As Object, e As System.EventArgs)
    Me.demoMarqueeControl1.Start()
End Sub 'startButton_Click

Private Sub stopButton_Click(sender As Object, e As System.EventArgs)
Me.demoMarqueeControl1.Stop()
End Sub 'stopButton_Click
```

```csharp
private void startButton_Click(object sender, System.EventArgs e)
{
    this.demoMarqueeControl1.Start();
}

private void stopButton_Click(object sender, System.EventArgs e)
{
    this.demoMarqueeControl1.Stop();
}
```

1. <span data-ttu-id="ded80-438">設定、`MarqueeControlTest`スタートアップ プロジェクトとしてプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ded80-438">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="ded80-439">表示するフォームが表示されます、`DemoMarqueeControl`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-439">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="ded80-440">をクリックして、**開始**アニメーションを開始するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ded80-440">Click the **Start** button to start the animation.</span></span> <span data-ttu-id="ded80-441">テキストが点滅し、ライトの境界線を移動するが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ded80-441">You should see the text flashing and the lights moving around the border.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ded80-442">次の手順</span><span class="sxs-lookup"><span data-stu-id="ded80-442">Next Steps</span></span>

<span data-ttu-id="ded80-443">`MarqueeControlLibrary`カスタム コントロールと関連付けられているデザイナーの単純な実装を示します。</span><span class="sxs-lookup"><span data-stu-id="ded80-443">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="ded80-444">いくつかの方法で行うと、このサンプルがより高度です。</span><span class="sxs-lookup"><span data-stu-id="ded80-444">You can make this sample more sophisticated in several ways:</span></span>

- <span data-ttu-id="ded80-445">プロパティ値を変更、`DemoMarqueeControl`デザイナー。</span><span class="sxs-lookup"><span data-stu-id="ded80-445">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="ded80-446">さらに追加`MarqueBorder`を制御し、入れ子になった効果を作成するには、その親インスタンス内でドッキングします。</span><span class="sxs-lookup"><span data-stu-id="ded80-446">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="ded80-447">別の設定を使用した実験、`UpdatePeriod`と光に関連するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ded80-447">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>

- <span data-ttu-id="ded80-448">独自の実装を作成する`IMarqueeWidget`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-448">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="ded80-449">など、複数のイメージで、点滅「neon サインイン」またはアニメーションの記号を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ded80-449">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>

- <span data-ttu-id="ded80-450">さらに、デザイン時のエクスペリエンスをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="ded80-450">Further customize the design-time experience.</span></span> <span data-ttu-id="ded80-451">多くのプロパティをシャドウ試して<xref:System.Windows.Forms.Control.Enabled%2A>と<xref:System.Windows.Forms.Control.Visible%2A>、し、新しいプロパティを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ded80-451">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="ded80-452">子コントロールのドッキングなどの一般的なタスクを簡略化の新しいデザイナー動詞を追加します。</span><span class="sxs-lookup"><span data-stu-id="ded80-452">Add new designer verbs to simplify common tasks like docking child controls.</span></span>

- <span data-ttu-id="ded80-453">ライセンス、`MarqueeControl`します。</span><span class="sxs-lookup"><span data-stu-id="ded80-453">License the `MarqueeControl`.</span></span> <span data-ttu-id="ded80-454">詳細については、「[方法 :コンポーネントとコントロールのライセンスの](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))します。</span><span class="sxs-lookup"><span data-stu-id="ded80-454">For more information, see [How to: License Components and Controls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120)).</span></span>

- <span data-ttu-id="ded80-455">コントロールがシリアル化する方法とそれらのコードを生成する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="ded80-455">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="ded80-456">詳細については、次を参照してください。[動的ソース コードの生成とコンパイル](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)します。</span><span class="sxs-lookup"><span data-stu-id="ded80-456">For more information, see [Dynamic Source Code Generation and Compilation](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ded80-457">関連項目</span><span class="sxs-lookup"><span data-stu-id="ded80-457">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
- <span data-ttu-id="ded80-458">[方法: デザイン時機能を活用した Windows フォーム コントロールを作成します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ded80-458">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>
- <span data-ttu-id="ded80-459">[デザイン時サポートの拡張](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ded80-459">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- <span data-ttu-id="ded80-460">[カスタム デザイナー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ded80-460">[Custom Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))</span></span>
