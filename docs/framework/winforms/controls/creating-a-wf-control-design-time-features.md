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
ms.openlocfilehash: 733f22c122dd6acdad41371419375e55e977c016
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039933"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a><span data-ttu-id="d26dc-102">チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-102">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>

<span data-ttu-id="d26dc-103">カスタムコントロールのデザイン時のエクスペリエンスは、関連するカスタムデザイナーを作成することによって拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-103">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>

<span data-ttu-id="d26dc-104">このチュートリアルでは、カスタムコントロールのカスタムデザイナーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-104">This walkthrough illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="d26dc-105">`MarqueeControl`型と、それに関連付けられたデザイナークラス`MarqueeControlRootDesigner`(と呼ばれる) を実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-105">You will implement a `MarqueeControl` type and an associated designer class, called `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="d26dc-106">この`MarqueeControl`型は、シアターマーキーに似た表示を実装し、アニメーション化されたライトと点滅するテキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-106">The `MarqueeControl` type implements a display similar to a theater marquee, with animated lights and flashing text.</span></span>

<span data-ttu-id="d26dc-107">このコントロールのデザイナーは、デザイン時のカスタムエクスペリエンスを提供するために、デザイン環境と対話します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-107">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="d26dc-108">カスタムデザイナーを使用すると、アニメーション化さ`MarqueeControl`れたライトと、さまざまな組み合わせで点滅するテキストを使用して、カスタム実装を組み立てることができます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-108">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="d26dc-109">アセンブルされたコントロールは、他の Windows フォームコントロールと同様に、フォーム上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-109">You can use the assembled control on a form like any other Windows Forms control.</span></span>

<span data-ttu-id="d26dc-110">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="d26dc-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="d26dc-111">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-111">Creating the Project</span></span>

- <span data-ttu-id="d26dc-112">コントロールライブラリプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-112">Creating a Control Library Project</span></span>

- <span data-ttu-id="d26dc-113">カスタムコントロールプロジェクトの参照</span><span class="sxs-lookup"><span data-stu-id="d26dc-113">Referencing the Custom Control Project</span></span>

- <span data-ttu-id="d26dc-114">カスタムコントロールとそのカスタムデザイナーの定義</span><span class="sxs-lookup"><span data-stu-id="d26dc-114">Defining a Custom Control and Its Custom Designer</span></span>

- <span data-ttu-id="d26dc-115">カスタムコントロールのインスタンスの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-115">Creating an Instance of Your Custom Control</span></span>

- <span data-ttu-id="d26dc-116">デザイン時デバッグのためのプロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="d26dc-116">Setting Up the Project for Design-Time Debugging</span></span>

- <span data-ttu-id="d26dc-117">カスタムコントロールの実装</span><span class="sxs-lookup"><span data-stu-id="d26dc-117">Implementing Your Custom Control</span></span>

- <span data-ttu-id="d26dc-118">カスタムコントロールの子コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-118">Creating a Child Control for Your Custom Control</span></span>

- <span data-ttu-id="d26dc-119">MarqueeBorder 子コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="d26dc-119">Create the MarqueeBorder Child Control</span></span>

- <span data-ttu-id="d26dc-120">カスタムデザイナーを作成してプロパティをシャドウおよびフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="d26dc-120">Creating a Custom Designer to Shadow and Filter Properties</span></span>

- <span data-ttu-id="d26dc-121">コンポーネントの変更の処理</span><span class="sxs-lookup"><span data-stu-id="d26dc-121">Handling Component Changes</span></span>

- <span data-ttu-id="d26dc-122">デザイナー動詞をカスタムデザイナーに追加する</span><span class="sxs-lookup"><span data-stu-id="d26dc-122">Adding Designer Verbs to your Custom Designer</span></span>

- <span data-ttu-id="d26dc-123">カスタム UITypeEditor の作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-123">Creating a Custom UITypeEditor</span></span>

- <span data-ttu-id="d26dc-124">デザイナーでのカスタムコントロールのテスト</span><span class="sxs-lookup"><span data-stu-id="d26dc-124">Testing your Custom Control in the Designer</span></span>

<span data-ttu-id="d26dc-125">完了すると、カスタムコントロールは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-125">When you are finished, your custom control will look something like the following:</span></span>

![テキストと [開始] および [停止] ボタンを示すマーキーを表示するアプリ。](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

<span data-ttu-id="d26dc-127">完全なコードリストについて[は、「方法:デザイン時機能](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))を利用する Windows フォームコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-127">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>


## <a name="prerequisites"></a><span data-ttu-id="d26dc-128">前提条件</span><span class="sxs-lookup"><span data-stu-id="d26dc-128">Prerequisites</span></span>

<span data-ttu-id="d26dc-129">このチュートリアルを完了するには、Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="d26dc-129">In order to complete this walkthrough, you'll need Visual Studio.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="d26dc-130">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-130">Creating the Project</span></span>

<span data-ttu-id="d26dc-131">最初の手順では、アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-131">The first step is to create the application project.</span></span> <span data-ttu-id="d26dc-132">このプロジェクトは、カスタムコントロールをホストするアプリケーションをビルドするために使用します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-132">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="d26dc-133">Visual Studio を開き、"MarqueeControlTest" という名前の Windows フォームアプリケーションプロジェクトを作成します (**ファイル** >  **新しい** > **プロジェクト** >  **ビジュアルC#**  または  **Visual Basic**  > **クラシックデスクトップ** **Windows フォームアプリケーション)。**  > </span><span class="sxs-lookup"><span data-stu-id="d26dc-133">Open Visual Studio and create a Windows Forms Application project called "MarqueeControlTest" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="creating-a-control-library-project"></a><span data-ttu-id="d26dc-134">コントロールライブラリプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-134">Creating a Control Library Project</span></span>

<span data-ttu-id="d26dc-135">次の手順では、コントロールライブラリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-135">The next step is to create the control library project.</span></span> <span data-ttu-id="d26dc-136">新しいカスタムコントロールとそれに対応するカスタムデザイナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-136">You will create a new custom control and its corresponding custom designer.</span></span>

### <a name="to-create-the-control-library-project"></a><span data-ttu-id="d26dc-137">コントロールライブラリプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-137">To create the control library project</span></span>

1. <span data-ttu-id="d26dc-138">ソリューションに Windows フォームコントロールライブラリプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-138">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="d26dc-139">プロジェクトに "MarqueeControlLibrary" という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-139">Name the project "MarqueeControlLibrary."</span></span>

2. <span data-ttu-id="d26dc-140">**ソリューションエクスプローラー**を使用して、選択した言語に応じて、"UserControl1.cs" または "UserControl1" という名前のソースファイルを削除して、プロジェクトの既定のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-140">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span> <span data-ttu-id="d26dc-141">詳細については、「[方法 :項目](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))を削除、削除、および除外します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-141">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="d26dc-142">新しい<xref:System.Windows.Forms.UserControl>項目を`MarqueeControlLibrary`プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-142">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="d26dc-143">新しいソースファイルに "MarqueeControl" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-143">Give the new source file a base name of "MarqueeControl."</span></span>

4. <span data-ttu-id="d26dc-144">**ソリューションエクスプローラー**を使用して、 `MarqueeControlLibrary`プロジェクトに新しいフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-144">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="d26dc-145">詳細については、「[方法 :新しいプロジェクト項目](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))を追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-145">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="d26dc-146">新しいフォルダーに「Design」という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-146">Name the new folder "Design."</span></span>

5. <span data-ttu-id="d26dc-147">**Design**フォルダーを右クリックし、新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-147">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="d26dc-148">ソースファイルに "MarqueeControlRootDesigner" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-148">Give the source file a base name of "MarqueeControlRootDesigner."</span></span>

6. <span data-ttu-id="d26dc-149">System.string アセンブリの型を使用する必要があるため、この参照をプロジェクトに追加し`MarqueeControlLibrary`てください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-149">You will need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d26dc-150">System.servicemodel アセンブリを使用するには、プロジェクトで .NET Framework クライアントプロファイルではなく、完全バージョンの .NET Framework を対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-150">To use the System.Design assembly, your project must target the full version of the .NET Framework, not the .NET Framework Client Profile.</span></span> <span data-ttu-id="d26dc-151">ターゲットフレームワークを変更するには[、「方法:.NET Framework のターゲット バージョンを指定する](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-151">To change the target framework, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

## <a name="referencing-the-custom-control-project"></a><span data-ttu-id="d26dc-152">カスタムコントロールプロジェクトの参照</span><span class="sxs-lookup"><span data-stu-id="d26dc-152">Referencing the Custom Control Project</span></span>

<span data-ttu-id="d26dc-153">カスタムコントロールをテスト`MarqueeControlTest`するには、プロジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-153">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="d26dc-154">`MarqueeControlLibrary`アセンブリにプロジェクト参照を追加すると、テストプロジェクトはカスタムコントロールを認識するようになります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-154">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>

### <a name="to-reference-the-custom-control-project"></a><span data-ttu-id="d26dc-155">カスタムコントロールプロジェクトを参照するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-155">To reference the custom control project</span></span>

- <span data-ttu-id="d26dc-156">プロジェクトで、 `MarqueeControlLibrary`アセンブリへのプロジェクト参照を追加します。 `MarqueeControlTest`</span><span class="sxs-lookup"><span data-stu-id="d26dc-156">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="d26dc-157">`MarqueeControlLibrary`アセンブリを直接参照するのではなく、 **[参照の追加]** ダイアログボックスの **[プロジェクト]** タブを使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-157">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>

## <a name="defining-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="d26dc-158">カスタムコントロールとそのカスタムデザイナーの定義</span><span class="sxs-lookup"><span data-stu-id="d26dc-158">Defining a Custom Control and Its Custom Designer</span></span>
 <span data-ttu-id="d26dc-159">カスタムコントロールは<xref:System.Windows.Forms.UserControl>クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-159">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="d26dc-160">これにより、コントロールに他のコントロールを含めることができます。また、コントロールには、既定の機能が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-160">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>

 <span data-ttu-id="d26dc-161">カスタムコントロールには、関連付けられたカスタムデザイナーがあります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-161">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="d26dc-162">これにより、カスタムコントロール専用にカスタマイズされた独自のデザインエクスペリエンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-162">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>

 <span data-ttu-id="d26dc-163">コントロールをデザイナーに関連付けるには、 <xref:System.ComponentModel.DesignerAttribute>クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-163">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="d26dc-164">カスタムコントロールのデザイン時動作全体を開発しているため、カスタムデザイナーは<xref:System.ComponentModel.Design.IRootDesigner>インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-164">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>

### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="d26dc-165">カスタムコントロールとそのカスタムデザイナーを定義するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-165">To define a custom control and its custom designer</span></span>

1. <span data-ttu-id="d26dc-166">`MarqueeControl` **コードエディター**でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-166">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="d26dc-167">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-167">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <span data-ttu-id="d26dc-168">をクラス`MarqueeControl`宣言に追加します。<xref:System.ComponentModel.DesignerAttribute></span><span class="sxs-lookup"><span data-stu-id="d26dc-168">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="d26dc-169">これにより、カスタムコントロールがデザイナーに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-169">This associates the custom control with its designer.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. <span data-ttu-id="d26dc-170">`MarqueeControlRootDesigner` **コードエディター**でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-170">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="d26dc-171">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-171">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. <span data-ttu-id="d26dc-172"><xref:System.Windows.Forms.Design.DocumentDesigner>クラスを継承する`MarqueeControlRootDesigner`ようにの宣言を変更します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-172">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="d26dc-173">を適用して、デザイナーと**ツールボックス**の対話を指定します。 <xref:System.ComponentModel.ToolboxItemFilterAttribute></span><span class="sxs-lookup"><span data-stu-id="d26dc-173">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>

     <span data-ttu-id="d26dc-174">**メモ**`MarqueeControlRootDesigner`クラスの定義は、"MarqueeControlLibrary" という名前空間で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-174">**Note** The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called "MarqueeControlLibrary.Design."</span></span> <span data-ttu-id="d26dc-175">この宣言により、デザイン関連の型用に予約された特殊な名前空間にデザイナーが配置されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-175">This declaration places the designer in a special namespace reserved for design-related types.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. <span data-ttu-id="d26dc-176">`MarqueeControlRootDesigner`クラスのコンストラクターを定義します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-176">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="d26dc-177">コンストラクター本体<xref:System.Diagnostics.Trace.WriteLine%2A>にステートメントを挿入します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-177">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="d26dc-178">これは、デバッグのために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-178">This will be useful for debugging purposes.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="creating-an-instance-of-your-custom-control"></a><span data-ttu-id="d26dc-179">カスタムコントロールのインスタンスの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-179">Creating an Instance of Your Custom Control</span></span>
 <span data-ttu-id="d26dc-180">コントロールのカスタムデザイン時の動作を確認するには、コントロールのインスタンスを project の`MarqueeControlTest`フォームに配置します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-180">To observe the custom design-time behavior of your control, you will place an instance of your control on the form in `MarqueeControlTest` project.</span></span>

### <a name="to-create-an-instance-of-your-custom-control"></a><span data-ttu-id="d26dc-181">カスタムコントロールのインスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-181">To create an instance of your custom control</span></span>

1. <span data-ttu-id="d26dc-182">新しい<xref:System.Windows.Forms.UserControl>項目を`MarqueeControlTest`プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-182">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="d26dc-183">新しいソースファイルに "DemoMarqueeControl" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-183">Give the new source file a base name of "DemoMarqueeControl."</span></span>

2. <span data-ttu-id="d26dc-184">`DemoMarqueeControl` **コードエディター**でファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-184">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="d26dc-185">ファイルの先頭に、 `MarqueeControlLibrary`名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-185">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>

```vb
Imports MarqueeControlLibrary
```

```csharp
using MarqueeControlLibrary;
```

1. <span data-ttu-id="d26dc-186">`MarqueeControl`クラスを継承する`DemoMarqueeControl`ようにの宣言を変更します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-186">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>

2. <span data-ttu-id="d26dc-187">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-187">Build the project.</span></span>

3. <span data-ttu-id="d26dc-188">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-188">Open `Form1` in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="d26dc-189">**ツールボックス**の **[MarqueeControlTest Components]** タブを見つけて開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-189">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="d26dc-190">`DemoMarqueeControl` **ツールボックス**からフォームにをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-190">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="d26dc-191">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-191">Build the project.</span></span>

## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="d26dc-192">デザイン時デバッグのためのプロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="d26dc-192">Setting Up the Project for Design-Time Debugging</span></span>

<span data-ttu-id="d26dc-193">カスタムデザイン時のエクスペリエンスを開発する場合は、コントロールとコンポーネントをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-193">When you are developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="d26dc-194">デザイン時にデバッグを許可するようにプロジェクトを設定する簡単な方法があります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-194">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="d26dc-195">詳細については、「[チュートリアル:デザイン時](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)にカスタム Windows フォームコントロールをデバッグする。</span><span class="sxs-lookup"><span data-stu-id="d26dc-195">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="d26dc-196">デザイン時デバッグ用にプロジェクトを設定するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-196">To set up the project for design-time debugging</span></span>

1. <span data-ttu-id="d26dc-197">プロジェクトを右クリック`MarqueeControlLibrary`し、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-197">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>

2. <span data-ttu-id="d26dc-198">MarqueeControlLibrary プロパティページ ダイアログボックスで、**デバッグ** ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-198">In the "MarqueeControlLibrary Property Pages" dialog box, select the **Debug** page.</span></span>

3. <span data-ttu-id="d26dc-199">**[開始アクション]** セクションで、 **[外部プログラムの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-199">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="d26dc-200">Visual studio の別のインスタンスをデバッグする場合は、省略記号 (![[visual](./media/visual-studio-ellipsis-button.png)studio のプロパティウィンドウ] の省略記号ボタン (...)) をクリックして、visual studio IDE を参照します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-200">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="d26dc-201">実行可能ファイルの名前は devenv.exe で、を既定の場所にインストールした場合、パスは%programfiles%\Microsoft Visual Studio 9.0 \ Common7\IDE\devenv.exe. になります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-201">The name of the executable file is devenv.exe, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

4. <span data-ttu-id="d26dc-202">[OK] をクリックして、ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-202">Click OK to close the dialog box.</span></span>

5. <span data-ttu-id="d26dc-203">プロジェクトを右クリック`MarqueeControlLibrary`し、[スタートアッププロジェクトに設定] を選択して、このデバッグ構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-203">Right-click the `MarqueeControlLibrary` project and select "Set as StartUp Project" to enable this debugging configuration.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="d26dc-204">チェックポイント</span><span class="sxs-lookup"><span data-stu-id="d26dc-204">Checkpoint</span></span>

<span data-ttu-id="d26dc-205">これで、カスタムコントロールのデザイン時動作をデバッグする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="d26dc-205">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="d26dc-206">デバッグ環境が正しく設定されていることを確認したら、カスタムコントロールとカスタムデザイナーの関連付けをテストします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-206">Once you have determined that the debugging environment is set up correctly, you will test the association between the custom control and the custom designer.</span></span>

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="d26dc-207">デバッグ環境とデザイナーの関連付けをテストするには</span><span class="sxs-lookup"><span data-stu-id="d26dc-207">To test the debugging environment and the designer association</span></span>

1. <span data-ttu-id="d26dc-208">**コードエディター**で<xref:System.Diagnostics.Trace.WriteLine%2A>ソースファイルを開き、ステートメントにブレークポイントを設定します。 `MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="d26dc-208">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>

2. <span data-ttu-id="d26dc-209">F5 キーを押してデバッグセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-209">Press F5 to start the debugging session.</span></span> <span data-ttu-id="d26dc-210">Visual Studio の新しいインスタンスが作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-210">Note that a new instance of Visual Studio is created.</span></span>

3. <span data-ttu-id="d26dc-211">Visual Studio の新しいインスタンスで、"MarqueeControlTest" ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-211">In the new instance of Visual Studio, open the "MarqueeControlTest" solution.</span></span> <span data-ttu-id="d26dc-212">**[ファイル]** メニューから **[最近使ったプロジェクト]** を選択すると、ソリューションを簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-212">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="d26dc-213">"MarqueeControlTest" ソリューションファイルは、最近使用したファイルとして一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-213">The "MarqueeControlTest.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="d26dc-214">デザイナーで`DemoMarqueeControl`を開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-214">Open the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="d26dc-215">Visual Studio のデバッグインスタンスがフォーカスを取得し、ブレークポイントで実行を停止することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-215">Note that the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="d26dc-216">F5 キーを押してデバッグセッションを続行します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-216">Press F5 to continue the debugging session.</span></span>

<span data-ttu-id="d26dc-217">この時点で、カスタムコントロールとそれに関連付けられているカスタムデザイナーを開発およびデバッグするために、すべてが準備されています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-217">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="d26dc-218">このチュートリアルの残りの部分では、コントロールとデザイナーの機能を実装する方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-218">The remainder of this walkthrough will concentrate on the details of implementing features of the control and the designer.</span></span>

## <a name="implementing-your-custom-control"></a><span data-ttu-id="d26dc-219">カスタムコントロールの実装</span><span class="sxs-lookup"><span data-stu-id="d26dc-219">Implementing Your Custom Control</span></span>

<span data-ttu-id="d26dc-220">は、カスタマイズ<xref:System.Windows.Forms.UserControl> が少ししかないです。`MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="d26dc-220">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="d26dc-221">ここでは、2 `Start`つのメソッドを公開してい`Stop`ます。は、マーキーアニメーションを開始し、はアニメーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-221">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="d26dc-222">には`MarqueeControl` 、 `IMarqueeWidget`インターフェイス`StopMarquee` `Stop`を実装する子コントロールが含まれて`StartMarquee` おり、各子コントロールを列挙し、それぞれの子コントロールでメソッドとメソッドをそれぞれ呼び出します。`Start`を実装`IMarqueeWidget`する。</span><span class="sxs-lookup"><span data-stu-id="d26dc-222">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>

<span data-ttu-id="d26dc-223">コントロール`MarqueeBorder` <xref:System.Windows.Forms.Control.OnLayout%2A>と`MarqueeText`コントロールの外観は、レイアウトに依存している`MarqueeControl`ため、メソッドをオーバーライド<xref:System.Windows.Forms.Control.PerformLayout%2A>し、この型の子コントロールに対してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-223">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>

<span data-ttu-id="d26dc-224">これは`MarqueeControl`カスタマイズの範囲です。</span><span class="sxs-lookup"><span data-stu-id="d26dc-224">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="d26dc-225">実行時の機能は`MarqueeBorder`コントロールと`MarqueeText`コントロールによって実装され、デザイン時の`MarqueeBorderDesigner`機能はクラスおよび`MarqueeControlRootDesigner`クラスによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-225">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>

### <a name="to-implement-your-custom-control"></a><span data-ttu-id="d26dc-226">カスタムコントロールを実装するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-226">To implement your custom control</span></span>

1. <span data-ttu-id="d26dc-227">`MarqueeControl` **コードエディター**でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-227">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="d26dc-228">`Start`メソッドと`Stop`メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-228">Implement the `Start` and `Stop` methods.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. <span data-ttu-id="d26dc-229"><xref:System.Windows.Forms.Control.OnLayout%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-229">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="creating-a-child-control-for-your-custom-control"></a><span data-ttu-id="d26dc-230">カスタムコントロールの子コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-230">Creating a Child Control for Your Custom Control</span></span>

<span data-ttu-id="d26dc-231">は`MarqueeControl` 、 `MarqueeBorder`コントロールと`MarqueeText`コントロールという2種類の子コントロールをホストします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-231">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>

- <span data-ttu-id="d26dc-232">`MarqueeBorder`:このコントロールは、端の周りに "ライト" の境界線を描画します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-232">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="d26dc-233">ライトが連続して点滅しているように見えます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-233">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="d26dc-234">ライトフラッシュがという`UpdatePeriod`プロパティによって制御される速度。</span><span class="sxs-lookup"><span data-stu-id="d26dc-234">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="d26dc-235">他のいくつかのカスタムプロパティによって、コントロールの外観の他の側面が決まります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-235">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="d26dc-236">`StartMarquee` と`StopMarquee`呼ばれる2つのメソッドは、アニメーションの開始と停止を制御します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-236">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>

- <span data-ttu-id="d26dc-237">`MarqueeText`:このコントロールは、点滅する文字列を描画します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-237">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="d26dc-238">コントロールと同様に、テキストが点滅する速度は、 `UpdatePeriod`プロパティによって制御されます。 `MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="d26dc-238">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="d26dc-239">コントロールには`StopMarquee` 、コントロール`MarqueeBorder`に共通のメソッド`StartMarquee`とメソッドもあります。 `MarqueeText`</span><span class="sxs-lookup"><span data-stu-id="d26dc-239">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>

<span data-ttu-id="d26dc-240">デザイン時`MarqueeControlRootDesigner`に、を使用すると、これら2つのコントロール型`MarqueeControl`を任意の組み合わせでに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-240">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>

<span data-ttu-id="d26dc-241">2つのコントロールの共通機能は、と呼ばれる`IMarqueeWidget`インターフェイスに分けられています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-241">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="d26dc-242">これにより`MarqueeControl` 、は、マーキーに関連する子コントロールを検出し、特別な処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-242">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>

<span data-ttu-id="d26dc-243">定期的なアニメーション機能を実装するには、 <xref:System.ComponentModel.BackgroundWorker>名前空間の<xref:System.ComponentModel?displayProperty=nameWithType>オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-243">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="d26dc-244">オブジェクトを使用<xref:System.Windows.Forms.Timer>することもできます`IMarqueeWidget`が、多くのオブジェクトが存在する場合、1つの UI スレッドがアニメーションを維持できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-244">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>

### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="d26dc-245">カスタムコントロールの子コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-245">To create a child control for your custom control</span></span>

1. <span data-ttu-id="d26dc-246">新しいクラス項目を`MarqueeControlLibrary`プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-246">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="d26dc-247">新しいソースファイルに "IMarqueeWidget" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-247">Give the new source file a base name of "IMarqueeWidget."</span></span>

2. <span data-ttu-id="d26dc-248">**コードエディター**で`class` `interface`ソースファイルを開き、宣言をからに変更します。 `IMarqueeWidget`</span><span class="sxs-lookup"><span data-stu-id="d26dc-248">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. <span data-ttu-id="d26dc-249">次のコードを`IMarqueeWidget`インターフェイスに追加して、2つのメソッドと、マーキーアニメーションを操作するプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-249">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. <span data-ttu-id="d26dc-250">新しい**カスタムコントロール**項目を`MarqueeControlLibrary`プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-250">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="d26dc-251">新しいソースファイルに "MarqueeText" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-251">Give the new source file a base name of "MarqueeText."</span></span>

5. <span data-ttu-id="d26dc-252">コンポーネントを<xref:System.ComponentModel.BackgroundWorker> **ツールボックス**からコントロールにドラッグします。`MarqueeText`</span><span class="sxs-lookup"><span data-stu-id="d26dc-252">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="d26dc-253">このコンポーネントを使用する`MarqueeText`と、コントロール自体を非同期的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-253">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>

6. <span data-ttu-id="d26dc-254">プロパティウィンドウで、 <xref:System.ComponentModel.BackgroundWorker>コンポーネントの`WorkerReportsProgress`プロパティと<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>プロパティをに`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-254">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="d26dc-255">これらの設定に<xref:System.ComponentModel.BackgroundWorker>より、コンポーネントは定期的<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>にイベントを発生させ、非同期更新を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-255">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="d26dc-256">詳細については、「 [BackgroundWorker Component](backgroundworker-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-256">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

7. <span data-ttu-id="d26dc-257">`MarqueeText` **コードエディター**でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-257">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="d26dc-258">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-258">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. <span data-ttu-id="d26dc-259">を`MarqueeText` 継承し、`IMarqueeWidget`インターフェイスを実装するように、の宣言を変更します。<xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="d26dc-259">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. <span data-ttu-id="d26dc-260">公開されたプロパティに対応するインスタンス変数を宣言し、コンストラクターで初期化します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-260">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="d26dc-261">フィールド`isLit`は、 `LightColor`プロパティによって指定された色でテキストを描画するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-261">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. <span data-ttu-id="d26dc-262">`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-262">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="d26dc-263">メソッド`StartMarquee`と<xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>メソッドは、コンポーネントのメソッド<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>とメソッドを呼び出して、アニメーションを開始および停止します。 `StopMarquee`</span><span class="sxs-lookup"><span data-stu-id="d26dc-263">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="d26dc-264">属性と属性<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>はプロパティに適用されるため、"Marquee"と呼ばれるプロパティウィンドウのカスタムセクションに表示されます。`UpdatePeriod` <xref:System.ComponentModel.CategoryAttribute.Category%2A></span><span class="sxs-lookup"><span data-stu-id="d26dc-264">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. <span data-ttu-id="d26dc-265">プロパティアクセサーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-265">Implement the property accessors.</span></span> <span data-ttu-id="d26dc-266">クライアント`LightColor`には、と`DarkColor`の2つのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-266">You will expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="d26dc-267">これらの<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>プロパティには属性と属性が適用されるので、プロパティは"Marquee"と呼ばれるプロパティウィンドウのカスタムセクションに表示されます。<xref:System.ComponentModel.CategoryAttribute.Category%2A></span><span class="sxs-lookup"><span data-stu-id="d26dc-267">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. <span data-ttu-id="d26dc-268"><xref:System.ComponentModel.BackgroundWorker>コンポーネントとイベント<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>のハンドラーを実装します。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="d26dc-268">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="d26dc-269">イベント<xref:System.ComponentModel.BackgroundWorker.DoWork>ハンドラーは、によって`UpdatePeriod`指定されたミリ秒数<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>の間スリープ状態になり、コードがを<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>呼び出すことによってアニメーションを停止するまで、イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-269">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="d26dc-270">イベント<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>ハンドラーは、テキストを淡色と濃色の状態の間で切り替えて、点滅のようにします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-270">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. <span data-ttu-id="d26dc-271">アニメーションを<xref:System.Windows.Forms.Control.OnPaint%2A>有効にするには、メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-271">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. <span data-ttu-id="d26dc-272">F6 キーを押してソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-272">Press F6 to build the solution.</span></span>

## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="d26dc-273">MarqueeBorder 子コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="d26dc-273">Create the MarqueeBorder Child Control</span></span>

<span data-ttu-id="d26dc-274">コントロール`MarqueeBorder`は、 `MarqueeText`コントロールよりも少し洗練されています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-274">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="d26dc-275">これにはさらに多くのプロパティが<xref:System.Windows.Forms.Control.OnPaint%2A>あり、メソッドのアニメーションも複雑になります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-275">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="d26dc-276">原則として、 `MarqueeText`コントロールと非常によく似ています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-276">In principle, it is quite similar to the `MarqueeText` control.</span></span>

<span data-ttu-id="d26dc-277">コントロールは`MarqueeBorder`子コントロールを持つことができるため、 <xref:System.Windows.Forms.Control.Layout>イベントに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-277">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>

### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="d26dc-278">MarqueeBorder コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-278">To create the MarqueeBorder control</span></span>

1. <span data-ttu-id="d26dc-279">新しい**カスタムコントロール**項目を`MarqueeControlLibrary`プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-279">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="d26dc-280">新しいソースファイルに "MarqueeBorder" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-280">Give the new source file a base name of "MarqueeBorder."</span></span>

2. <span data-ttu-id="d26dc-281">コンポーネントを<xref:System.ComponentModel.BackgroundWorker> **ツールボックス**からコントロールにドラッグします。`MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="d26dc-281">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="d26dc-282">このコンポーネントを使用する`MarqueeBorder`と、コントロール自体を非同期的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-282">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>

3. <span data-ttu-id="d26dc-283">プロパティウィンドウで、 <xref:System.ComponentModel.BackgroundWorker>コンポーネントの`WorkerReportsProgress`プロパティと<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>プロパティをに`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-283">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="d26dc-284">これらの設定に<xref:System.ComponentModel.BackgroundWorker>より、コンポーネントは定期的<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>にイベントを発生させ、非同期更新を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-284">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="d26dc-285">詳細については、「 [BackgroundWorker Component](backgroundworker-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-285">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

4. <span data-ttu-id="d26dc-286">プロパティウィンドウで、[イベント] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-286">In the Properties window, click the Events button.</span></span> <span data-ttu-id="d26dc-287">イベント<xref:System.ComponentModel.BackgroundWorker.DoWork> および<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベントのハンドラーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-287">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

5. <span data-ttu-id="d26dc-288">`MarqueeBorder` **コードエディター**でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-288">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="d26dc-289">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-289">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. <span data-ttu-id="d26dc-290">から`IMarqueeWidget` `MarqueeBorder` 継承し、インターフェイスを実装するように、の宣言を変更します。<xref:System.Windows.Forms.Panel></span><span class="sxs-lookup"><span data-stu-id="d26dc-290">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. <span data-ttu-id="d26dc-291">`MarqueeBorder`コントロールの状態を管理するための2つ`MarqueeSpinDirection`の列挙体を宣言します。これは、ライトが境界の周りを`MarqueeLightShape`"スピン" する方向を決定します。は、ライトの形状 (正方形または円形) を決定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-291">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="d26dc-292">これらの宣言は、 `MarqueeBorder`クラス宣言の前に配置します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-292">Place these declarations before the `MarqueeBorder` class declaration.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. <span data-ttu-id="d26dc-293">公開されたプロパティに対応するインスタンス変数を宣言し、コンストラクターで初期化します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-293">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. <span data-ttu-id="d26dc-294">`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-294">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="d26dc-295">メソッド`StartMarquee`と<xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>メソッドは、コンポーネントのメソッド<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>とメソッドを呼び出して、アニメーションを開始および停止します。 `StopMarquee`</span><span class="sxs-lookup"><span data-stu-id="d26dc-295">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="d26dc-296">コントロールに`MarqueeBorder`子コントロールを含めることができる`StartMarquee`ため、メソッドは、すべての`StartMarquee`子コントロールを列挙`IMarqueeWidget`し、を実装する子コントロールに対してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-296">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="d26dc-297">`StopMarquee`メソッドには同様の実装があります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-297">The `StopMarquee` method has a similar implementation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. <span data-ttu-id="d26dc-298">プロパティアクセサーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-298">Implement the property accessors.</span></span> <span data-ttu-id="d26dc-299">コントロール`MarqueeBorder`には、外観を制御するためのプロパティがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-299">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. <span data-ttu-id="d26dc-300"><xref:System.ComponentModel.BackgroundWorker>コンポーネントとイベント<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>のハンドラーを実装します。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="d26dc-300">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="d26dc-301">イベント<xref:System.ComponentModel.BackgroundWorker.DoWork>ハンドラーは、によって`UpdatePeriod`指定されたミリ秒数<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>の間スリープ状態になり、コードがを<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>呼び出すことによってアニメーションを停止するまで、イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-301">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="d26dc-302">イベント<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>ハンドラーは、他のライトの明るい/暗い状態が決定される "基本" ライトの位置をインクリメントし、 <xref:System.Windows.Forms.Control.Refresh%2A>メソッドを呼び出して、コントロール自体を再描画します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-302">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. <span data-ttu-id="d26dc-303">ヘルパーメソッドと`IsLit` `DrawLight`を実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-303">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>

    <span data-ttu-id="d26dc-304">メソッド`IsLit`は、指定された位置のライトの色を決定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-304">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="d26dc-305">"Lit" のライトは、 `LightColor`プロパティによって指定された色で描画されます。 "ダーク" は、 `DarkColor`プロパティによって指定された色で描画されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-305">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>

    <span data-ttu-id="d26dc-306">メソッド`DrawLight`は、適切な色、形状、および位置を使用してライトを描画します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-306">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. <span data-ttu-id="d26dc-307"><xref:System.Windows.Forms.Control.OnLayout%2A>メソッドと<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-307">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>

    <span data-ttu-id="d26dc-308">メソッド<xref:System.Windows.Forms.Control.OnPaint%2A>は、 `MarqueeBorder`コントロールの端に沿ってライトを描画します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-308">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>

    <span data-ttu-id="d26dc-309">メソッドは<xref:System.Windows.Forms.Control.OnPaint%2A> `MarqueeBorder`コントロールのディメンションに依存するため、レイアウトが変更されるたびに呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-309">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="d26dc-310">これを実現するに<xref:System.Windows.Forms.Control.OnLayout%2A>は、 <xref:System.Windows.Forms.Control.Refresh%2A>をオーバーライドし、を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-310">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="d26dc-311">カスタムデザイナーを作成してプロパティをシャドウおよびフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="d26dc-311">Creating a Custom Designer to Shadow and Filter Properties</span></span>

<span data-ttu-id="d26dc-312">クラス`MarqueeControlRootDesigner`は、ルートデザイナーの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-312">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="d26dc-313">で`MarqueeControl`動作するこのデザイナーに加えて、 `MarqueeBorder`コントロールに特に関連付けられたカスタムデザイナーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-313">In addition to this designer, which operates on the `MarqueeControl`, you will need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="d26dc-314">このデザイナーには、カスタムルートデザイナーのコンテキストに適したカスタム動作が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-314">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>

<span data-ttu-id="d26dc-315">具体的には`MarqueeBorderDesigner` 、は、 `MarqueeBorder`コントロールの特定のプロパティを "シャドウ" してフィルター処理し、デザイン環境との相互作用を変更します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-315">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>

<span data-ttu-id="d26dc-316">コンポーネントのプロパティアクセサーへの呼び出しのインターセプトは、"シャドウ処理" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-316">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="d26dc-317">これにより、デザイナーはユーザーが設定した値を追跡し、必要に応じてその値をデザイン対象のコンポーネントに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-317">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>

<span data-ttu-id="d26dc-318">この例<xref:System.Windows.Forms.Control.Visible%2A>では、プロパティ<xref:System.Windows.Forms.Control.Enabled%2A>とプロパティがによって`MarqueeBorderDesigner`シャドウされます。これにより`MarqueeBorder` 、デザイン時にユーザーがコントロールを非表示にしたり無効にしたりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-318">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>

<span data-ttu-id="d26dc-319">デザイナーでは、プロパティを追加および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-319">Designers can also add and remove properties.</span></span> <span data-ttu-id="d26dc-320">この例<xref:System.Windows.Forms.Control.Padding%2A>では、プロパティはデザイン時に削除されます。 `MarqueeBorder`コントロールはプログラムによって、 `LightSize`プロパティによって指定されたライトのサイズに基づいて余白を設定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-320">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>

<span data-ttu-id="d26dc-321">の基本クラスは`MarqueeBorderDesigner`です<xref:System.ComponentModel.Design.ComponentDesigner>。これには、デザイン時にコントロールによって公開される属性、プロパティ、およびイベントを変更するためのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-321">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

<span data-ttu-id="d26dc-322">これらのメソッドを使用してコンポーネントのパブリックインターフェイスを変更する場合は、次の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-322">When changing the public interface of a component using these methods, you must follow these rules:</span></span>

- <span data-ttu-id="d26dc-323">メソッドでのみ項目を追加`PreFilter`または削除する</span><span class="sxs-lookup"><span data-stu-id="d26dc-323">Add or remove items in the `PreFilter` methods only</span></span>

- <span data-ttu-id="d26dc-324">メソッド内の既存の`PostFilter`項目のみを変更する</span><span class="sxs-lookup"><span data-stu-id="d26dc-324">Modify existing items in the `PostFilter` methods only</span></span>

- <span data-ttu-id="d26dc-325">常に基本実装を`PreFilter`メソッドで呼び出す</span><span class="sxs-lookup"><span data-stu-id="d26dc-325">Always call the base implementation first in the `PreFilter` methods</span></span>

- <span data-ttu-id="d26dc-326">`PostFilter`メソッドの最後に基本実装を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-326">Always call the base implementation last in the `PostFilter` methods</span></span>

<span data-ttu-id="d26dc-327">これらの規則に従うことで、デザイン時環境のすべてのデザイナーが、デザインされているすべてのコンポーネントの一貫したビューを確実に表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-327">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>

<span data-ttu-id="d26dc-328">クラス<xref:System.ComponentModel.Design.ComponentDesigner>は、シャドウプロパティの値を管理するためのディクショナリを提供します。これにより、特定のインスタンス変数を作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="d26dc-328">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="d26dc-329">プロパティをシャドウおよびフィルター処理するためのカスタムデザイナーを作成するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-329">To create a custom designer to shadow and filter properties</span></span>

1. <span data-ttu-id="d26dc-330">**Design**フォルダーを右クリックし、新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-330">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="d26dc-331">ソースファイルに "MarqueeBorderDesigner" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-331">Give the source file a base name of "MarqueeBorderDesigner."</span></span>

2. <span data-ttu-id="d26dc-332">`MarqueeBorderDesigner` **コードエディター**でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-332">Open the `MarqueeBorderDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="d26dc-333">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-333">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. <span data-ttu-id="d26dc-334">`MarqueeBorderDesigner` を<xref:System.Windows.Forms.Design.ParentControlDesigner>継承するようにの宣言を変更します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-334">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>

    <span data-ttu-id="d26dc-335">コントロールに`MarqueeBorder`子コントロールを含めることが`MarqueeBorderDesigner`できるため<xref:System.Windows.Forms.Design.ParentControlDesigner>、はを継承します。これは、親子の相互作用を処理します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-335">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. <span data-ttu-id="d26dc-336">の<xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>基本実装をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-336">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. <span data-ttu-id="d26dc-337">  <xref:System.Windows.Forms.Control.Enabled%2A> プロパティと <xref:System.Windows.Forms.Control.Visible%2A> プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-337">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="d26dc-338">これらの実装は、コントロールのプロパティをシャドウします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-338">These implementations shadow the control's properties.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handling-component-changes"></a><span data-ttu-id="d26dc-339">コンポーネントの変更の処理</span><span class="sxs-lookup"><span data-stu-id="d26dc-339">Handling Component Changes</span></span>
 <span data-ttu-id="d26dc-340">クラス`MarqueeControlRootDesigner`は、 `MarqueeControl`インスタンスのカスタムデザイン時エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-340">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="d26dc-341">デザイン時の機能のほとんどは<xref:System.Windows.Forms.Design.DocumentDesigner>クラスから継承されています。コードでは、コンポーネントの変更の処理とデザイナー動詞の追加という2つのカスタマイズのカスタマイズを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-341">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class; your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>

 <span data-ttu-id="d26dc-342">ユーザーが`MarqueeControl`インスタンスをデザイン`MarqueeControl`すると、ルートデザイナーはとその子コントロールに対する変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-342">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="d26dc-343">デザイン時環境には、コンポーネントの状態に<xref:System.ComponentModel.Design.IComponentChangeService>対する変更を追跡するための便利なサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-343">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>

 <span data-ttu-id="d26dc-344">このサービスへの参照を取得するには、 <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>メソッドを使用して環境に対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-344">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="d26dc-345">クエリが成功した場合、デザイナーは<xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged>イベントのハンドラーをアタッチし、デザイン時に一貫性のある状態を維持するために必要なすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-345">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>

 <span data-ttu-id="d26dc-346">`MarqueeControlRootDesigner`クラスの場合は、 <xref:System.Windows.Forms.Control.Refresh%2A> `IMarqueeWidget` に格納されている各オブジェクトに対してメソッド`MarqueeControl`を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-346">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="d26dc-347">これにより、 `IMarqueeWidget`親の<xref:System.Windows.Forms.Control.Size%2A>ようなプロパティが変更されたときに、オブジェクトが適切に再描画されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-347">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>

### <a name="to-handle-component-changes"></a><span data-ttu-id="d26dc-348">コンポーネントの変更を処理するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-348">To handle component changes</span></span>

1. <span data-ttu-id="d26dc-349">**コードエディター**で<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>ソースファイルを開き、メソッドをオーバーライドします。 `MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="d26dc-349">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="d26dc-350">の<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>基本実装を呼び出し、に<xref:System.ComponentModel.Design.IComponentChangeService>対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-350">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. <span data-ttu-id="d26dc-351">イベントハンドラー <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>を実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-351">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="d26dc-352">送信コンポーネントの型をテストし、が`IMarqueeWidget`の場合は、その<xref:System.Windows.Forms.Control.Refresh%2A>メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-352">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="adding-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="d26dc-353">デザイナー動詞をカスタムデザイナーに追加する</span><span class="sxs-lookup"><span data-stu-id="d26dc-353">Adding Designer Verbs to your Custom Designer</span></span>

<span data-ttu-id="d26dc-354">デザイナー動詞は、イベントハンドラーにリンクされたメニューコマンドです。</span><span class="sxs-lookup"><span data-stu-id="d26dc-354">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="d26dc-355">デザイナー動詞は、デザイン時にコンポーネントのショートカットメニューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-355">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="d26dc-356">詳細については、「 <xref:System.ComponentModel.Design.DesignerVerb> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-356">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>

<span data-ttu-id="d26dc-357">デザイナーには、次の2つのデザイナー動詞を追加します。**テストを実行**し、**テストを停止**します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-357">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="d26dc-358">これらの動詞を使用すると、 `MarqueeControl`デザイン時にの実行時の動作を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-358">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="d26dc-359">これらの`MarqueeControlRootDesigner`動詞はに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-359">These verbs will be added to the `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="d26dc-360">**実行テスト**が呼び出されると、動詞イベントハンドラーはに対し`StartMarquee` `MarqueeControl`てメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-360">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="d26dc-361">**停止テスト**が呼び出されると、動詞イベントハンドラーはに対し`StopMarquee` `MarqueeControl`てメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-361">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="d26dc-362">メソッド`StartMarquee`と`StopMarquee`メソッドの実装では、を実装`IMarqueeWidget`する含まれるコントロールに対してこれら`IMarqueeWidget`のメソッドを呼び出します。これにより、含まれるコントロールもテストに参加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-362">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>

### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="d26dc-363">デザイナー動詞をカスタムデザイナーに追加するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-363">To add designer verbs to your custom designers</span></span>

1. <span data-ttu-id="d26dc-364">クラスで、およびと`OnVerbStopTest`いう名前`OnVerbRunTest`のイベントハンドラーを追加します。 `MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="d26dc-364">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. <span data-ttu-id="d26dc-365">これらのイベントハンドラーを、対応するデザイナー動詞に接続します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-365">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="d26dc-366">`MarqueeControlRootDesigner`基底クラス<xref:System.ComponentModel.Design.DesignerVerbCollection>からを継承します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-366">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="d26dc-367">2つの新しい<xref:System.ComponentModel.Design.DesignerVerb>オブジェクトを作成し、 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>メソッドでこのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-367">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="creating-a-custom-uitypeeditor"></a><span data-ttu-id="d26dc-368">カスタム UITypeEditor の作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-368">Creating a Custom UITypeEditor</span></span>

<span data-ttu-id="d26dc-369">ユーザーに対してカスタムのデザイン時エクスペリエンスを作成する場合、多くの場合、プロパティウィンドウとのカスタム操作を作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-369">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="d26dc-370">これを行うには、を<xref:System.Drawing.Design.UITypeEditor>作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-370">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span> <span data-ttu-id="d26dc-371">詳細については、「[方法 :UI 型エディター](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120))を作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-371">For more information, see [How to: Create a UI Type Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120)).</span></span>

<span data-ttu-id="d26dc-372">コントロール`MarqueeBorder`は、プロパティウィンドウ内のいくつかのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-372">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="d26dc-373">これらのプロパティのうち`MarqueeSpinDirection`の`MarqueeLightShape` 2 つは、列挙体によって表されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-373">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="d26dc-374">UI 型エディターの使用方法を示すために、 `MarqueeLightShape`プロパティにはクラスが<xref:System.Drawing.Design.UITypeEditor>関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-374">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>

### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="d26dc-375">カスタム UI 型エディターを作成するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-375">To create a custom UI type editor</span></span>

1. <span data-ttu-id="d26dc-376">`MarqueeBorder` **コードエディター**でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-376">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>

2. <span data-ttu-id="d26dc-377">`MarqueeBorder`クラスの定義で、から<xref:System.Drawing.Design.UITypeEditor>派生するという`LightShapeEditor`クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-377">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. <span data-ttu-id="d26dc-378">という<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>名前`editorService`のインスタンス変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-378">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. <span data-ttu-id="d26dc-379"><xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-379">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="d26dc-380">この実装は<xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>を返します。これは、 `LightShapeEditor`を表示する方法をデザイン環境に指示します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-380">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. <span data-ttu-id="d26dc-381"><xref:System.Drawing.Design.UITypeEditor.EditValue%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-381">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="d26dc-382">この実装は、 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>オブジェクトのデザイン環境に対してクエリを行います。</span><span class="sxs-lookup"><span data-stu-id="d26dc-382">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="d26dc-383">成功した場合は、 `LightShapeSelectionControl`が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-383">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="d26dc-384">を開始するために<xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>メソッドが呼び出されます。 `LightShapeEditor`</span><span class="sxs-lookup"><span data-stu-id="d26dc-384">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="d26dc-385">この呼び出しからの戻り値がデザイン環境に返されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-385">The return value from this invocation is returned to the design environment.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="d26dc-386">カスタム UITypeEditor のビューコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="d26dc-386">Creating a View Control for your Custom UITypeEditor</span></span>

1. <span data-ttu-id="d26dc-387">プロパティ`MarqueeLightShape`は、 `Square`と`Circle`の2種類のライトシェイプをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-387">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="d26dc-388">プロパティウィンドウでこれらの値をグラフィカルに表示する目的でのみ使用されるカスタムコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-388">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="d26dc-389">このカスタムコントロールは、プロパティウィンドウと対話<xref:System.Drawing.Design.UITypeEditor>するためにによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-389">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="d26dc-390">カスタム UI 型エディターのビューコントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-390">To create a view control for your custom UI type editor</span></span>

1. <span data-ttu-id="d26dc-391">新しい<xref:System.Windows.Forms.UserControl>項目を`MarqueeControlLibrary`プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-391">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="d26dc-392">新しいソースファイルに "LightShapeSelectionControl" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-392">Give the new source file a base name of "LightShapeSelectionControl."</span></span>

2. <span data-ttu-id="d26dc-393">**ツールボックス**からに2つ<xref:System.Windows.Forms.Panel>のコントロールをドラッグします。`LightShapeSelectionControl`</span><span class="sxs-lookup"><span data-stu-id="d26dc-393">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="d26dc-394">とという`circlePanel`名前を指定します。 `squarePanel`</span><span class="sxs-lookup"><span data-stu-id="d26dc-394">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="d26dc-395">それらを並べて配置します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-395">Arrange them side by side.</span></span> <span data-ttu-id="d26dc-396"><xref:System.Windows.Forms.Control.Size%2A> 両方<xref:System.Windows.Forms.Panel>のコントロールのプロパティを (60, 60) に設定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-396">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to (60, 60).</span></span> <span data-ttu-id="d26dc-397">コントロールのプロパティを (8, 10) に設定します。 <xref:System.Windows.Forms.Control.Location%2A> `squarePanel`</span><span class="sxs-lookup"><span data-stu-id="d26dc-397">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to (8, 10).</span></span> <span data-ttu-id="d26dc-398">コントロールのプロパティを (80, 10) に設定します。 <xref:System.Windows.Forms.Control.Location%2A> `circlePanel`</span><span class="sxs-lookup"><span data-stu-id="d26dc-398">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to (80, 10).</span></span> <span data-ttu-id="d26dc-399">最後に、 `LightShapeSelectionControl`の<xref:System.Windows.Forms.Control.Size%2A>プロパティを (150, 80) に設定します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-399">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to (150, 80).</span></span>

3. <span data-ttu-id="d26dc-400">`LightShapeSelectionControl` **コードエディター**でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-400">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="d26dc-401">ファイルの先頭に、 <xref:System.Windows.Forms.Design?displayProperty=nameWithType>名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-401">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>

```vb
Imports System.Windows.Forms.Design
```

```csharp
using System.Windows.Forms.Design;
```

1. <span data-ttu-id="d26dc-402">コントロール<xref:System.Windows.Forms.Control.Click> `squarePanel`とコントロール`circlePanel`のイベントハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-402">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="d26dc-403">これらのメソッド<xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A>は、カスタム<xref:System.Drawing.Design.UITypeEditor>編集セッションを終了するためにを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-403">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

2. <span data-ttu-id="d26dc-404">という<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>名前`editorService`のインスタンス変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-404">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

```vb
Private editorService As IWindowsFormsEditorService
```

```csharp
private IWindowsFormsEditorService editorService;
```

1. <span data-ttu-id="d26dc-405">という`MarqueeLightShape`名前`lightShapeValue`のインスタンス変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-405">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

2. <span data-ttu-id="d26dc-406"><xref:System.Windows.Forms.Control.Click> コンストラクターで`squarePanel` 、イベント`circlePanel` ハンドラー<xref:System.Windows.Forms.Control.Click>をとコントロールのイベントにアタッチします。 `LightShapeSelectionControl`</span><span class="sxs-lookup"><span data-stu-id="d26dc-406">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="d26dc-407">また、デザイン環境から`MarqueeLightShape` `lightShapeValue`フィールドに値を割り当てるコンストラクターのオーバーロードを定義します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-407">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

3. <span data-ttu-id="d26dc-408">メソッドで、 <xref:System.Windows.Forms.Control.Click>イベントハンドラーをデタッチします。 <xref:System.ComponentModel.Component.Dispose%2A></span><span class="sxs-lookup"><span data-stu-id="d26dc-408">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

4. <span data-ttu-id="d26dc-409">**ソリューション エクスプローラー**で、 **[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-409">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="d26dc-410">LightShapeSelectionControl.Designer.cs または LightShapeSelectionControl ファイルを開き、 <xref:System.ComponentModel.Component.Dispose%2A>メソッドの既定の定義を削除します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-410">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>

5. <span data-ttu-id="d26dc-411">  `LightShape` プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-411">Implement the `LightShape` property.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

6. <span data-ttu-id="d26dc-412"><xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-412">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="d26dc-413">この実装では、塗りつぶされた正方形と円を描画します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-413">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="d26dc-414">また、1つの図形の周りに境界線を描画して、選択された値を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-414">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="testing-your-custom-control-in-the-designer"></a><span data-ttu-id="d26dc-415">デザイナーでのカスタムコントロールのテスト</span><span class="sxs-lookup"><span data-stu-id="d26dc-415">Testing your Custom Control in the Designer</span></span>

<span data-ttu-id="d26dc-416">この時点で、 `MarqueeControlLibrary`プロジェクトをビルドできます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-416">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="d26dc-417">`MarqueeControl`クラスを継承し、フォームで使用するコントロールを作成して、実装をテストします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-417">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>

### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="d26dc-418">カスタムの MarqueeControl 実装を作成するには</span><span class="sxs-lookup"><span data-stu-id="d26dc-418">To create a custom MarqueeControl implementation</span></span>

1. <span data-ttu-id="d26dc-419">Windows フォーム デザイナーで `DemoMarqueeControl` を開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-419">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="d26dc-420">これにより、 `DemoMarqueeControl`型のインスタンスが作成され、 `MarqueeControlRootDesigner`型のインスタンスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-420">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>

2. <span data-ttu-id="d26dc-421">**ツールボックス**で、 **[MarqueeControlLibrary Components]** タブを開きます。選択できるコントロールと`MarqueeBorder` `MarqueeText`コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-421">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>

3. <span data-ttu-id="d26dc-422">`MarqueeBorder`コントロールのインスタンスを`DemoMarqueeControl`デザインサーフェイスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-422">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="d26dc-423">この`MarqueeBorder`コントロールを親コントロールにドッキングします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-423">Dock this `MarqueeBorder` control to the parent control.</span></span>

4. <span data-ttu-id="d26dc-424">`MarqueeText`コントロールのインスタンスを`DemoMarqueeControl`デザインサーフェイスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-424">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>

5. <span data-ttu-id="d26dc-425">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-425">Build the solution.</span></span>

6. <span data-ttu-id="d26dc-426">を右クリック`DemoMarqueeControl`し、ショートカットメニューの **[テストの実行]** オプションを選択してアニメーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-426">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="d26dc-427">アニメーションを停止するには、 **[テストの停止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-427">Click **Stop Test** to stop the animation.</span></span>

7. <span data-ttu-id="d26dc-428">デザイン ビューで **[Form1]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-428">Open **Form1** in Design view.</span></span>

8. <span data-ttu-id="d26dc-429">フォームに<xref:System.Windows.Forms.Button> 2 つのコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-429">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="d26dc-430">それらに`startButton`と`stopButton`という<xref:System.Windows.Forms.Control.Text%2A>名前を設定し、プロパティ値をそれぞれ**Start**および**Stop**に変更します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-430">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>

9. <span data-ttu-id="d26dc-431"><xref:System.Windows.Forms.Control.Click> 両方<xref:System.Windows.Forms.Button>のコントロールにイベントハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-431">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>

10. <span data-ttu-id="d26dc-432">**ツールボックス**で、 **[MarqueeControlTest Components]** タブを開きます。選択できるが`DemoMarqueeControl`表示されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-432">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>

11. <span data-ttu-id="d26dc-433">の`DemoMarqueeControl`インスタンスを**Form1**デザインサーフェイスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-433">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>

12. <span data-ttu-id="d26dc-434">イベントハンドラーで、で`Start` メソッドと`Stop`メソッドを呼び出します。`DemoMarqueeControl` <xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="d26dc-434">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>

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

1. <span data-ttu-id="d26dc-435">`MarqueeControlTest`プロジェクトをスタートアッププロジェクトとして設定し、実行します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-435">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="d26dc-436">というフォーム`DemoMarqueeControl`が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-436">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="d26dc-437">アニメーションを開始するには、 **[開始]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-437">Click the **Start** button to start the animation.</span></span> <span data-ttu-id="d26dc-438">テキストが点滅し、ライトが境界内を移動していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-438">You should see the text flashing and the lights moving around the border.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d26dc-439">次の手順</span><span class="sxs-lookup"><span data-stu-id="d26dc-439">Next Steps</span></span>

<span data-ttu-id="d26dc-440">は`MarqueeControlLibrary` 、カスタムコントロールおよび関連するデザイナーの単純な実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="d26dc-440">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="d26dc-441">このサンプルは、いくつかの方法でより高度なものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-441">You can make this sample more sophisticated in several ways:</span></span>

- <span data-ttu-id="d26dc-442">デザイナー `DemoMarqueeControl`でのプロパティの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-442">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="d26dc-443">`MarqueBorder`コントロールを追加し、親インスタンス内にドッキングして、入れ子になった効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-443">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="d26dc-444">`UpdatePeriod`と light 関連のプロパティについて、さまざまな設定を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-444">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>

- <span data-ttu-id="d26dc-445">の独自の`IMarqueeWidget`実装を作成します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-445">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="d26dc-446">たとえば、点滅する "ネオンサイン" や、複数のイメージを使用したアニメーション化された記号を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-446">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>

- <span data-ttu-id="d26dc-447">デザイン時のエクスペリエンスをさらにカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-447">Further customize the design-time experience.</span></span> <span data-ttu-id="d26dc-448"><xref:System.Windows.Forms.Control.Enabled%2A> と<xref:System.Windows.Forms.Control.Visible%2A>より多くのプロパティをシャドウすることもできます。また、新しいプロパティを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d26dc-448">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="d26dc-449">新しいデザイナー動詞を追加して、子コントロールのドッキングなどの一般的なタスクを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-449">Add new designer verbs to simplify common tasks like docking child controls.</span></span>

- <span data-ttu-id="d26dc-450">を`MarqueeControl`ライセンスします。</span><span class="sxs-lookup"><span data-stu-id="d26dc-450">License the `MarqueeControl`.</span></span> <span data-ttu-id="d26dc-451">詳細については、「[方法 :ライセンスコンポーネントとコントロール](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="d26dc-451">For more information, see [How to: License Components and Controls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120)).</span></span>

- <span data-ttu-id="d26dc-452">コントロールのシリアル化方法とコードの生成方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="d26dc-452">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="d26dc-453">詳細については、「[動的なソースコードの生成とコンパイル](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d26dc-453">For more information, see [Dynamic Source Code Generation and Compilation](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d26dc-454">関連項目</span><span class="sxs-lookup"><span data-stu-id="d26dc-454">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
- <span data-ttu-id="d26dc-455">[方法: デザイン時機能を利用する Windows フォームコントロールを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d26dc-455">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>
- <span data-ttu-id="d26dc-456">[デザイン時サポートの拡張](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d26dc-456">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- <span data-ttu-id="d26dc-457">[カスタムデザイナー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d26dc-457">[Custom Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))</span></span>
