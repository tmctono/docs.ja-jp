---
title: Visual Studio のデザイン時機能を利用するコントロールを作成する
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7166b4203c54ab31f1d929c85cf1e6481ff120f8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744079"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a><span data-ttu-id="4e69c-102">チュートリアル: デザイン時機能を活用したコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="4e69c-102">Walkthrough: Create a control that takes advantage of design-time features</span></span>

<span data-ttu-id="4e69c-103">カスタムコントロールのデザイン時のエクスペリエンスは、関連するカスタムデザイナーを作成することによって拡張できます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-103">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>

<span data-ttu-id="4e69c-104">この記事では、カスタムコントロールのカスタムデザイナーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-104">This article illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="4e69c-105">`MarqueeControl` 型と、それに関連付けられた `MarqueeControlRootDesigner`と呼ばれるデザイナークラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-105">You'll implement a `MarqueeControl` type and an associated designer class called `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="4e69c-106">`MarqueeControl` 型は、アニメーション化されたライトと点滅するテキストを含むシアターマーキーに似た表示を実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-106">The `MarqueeControl` type implements a display similar to a theater marquee with animated lights and flashing text.</span></span>

<span data-ttu-id="4e69c-107">このコントロールのデザイナーは、デザイン時のカスタムエクスペリエンスを提供するために、デザイン環境と対話します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-107">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="4e69c-108">カスタムデザイナーを使用すると、さまざまな組み合わせでアニメーション化されたライトと点滅するテキストを使用して、カスタム `MarqueeControl` 実装を組み立てることができます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-108">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="4e69c-109">アセンブルされたコントロールは、他の Windows フォームコントロールと同様に、フォーム上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-109">You can use the assembled control on a form like any other Windows Forms control.</span></span>

<span data-ttu-id="4e69c-110">このチュートリアルを終了すると、カスタムコントロールは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-110">When you're finished with this walkthrough, your custom control will look something like the following:</span></span>

![テキストと [開始] および [停止] ボタンを示すマーキーを表示するアプリ。](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

<span data-ttu-id="4e69c-112">完全なコードリストについては、「[方法: デザイン時機能を利用する Windows フォームコントロールを作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e69c-112">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4e69c-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="4e69c-113">Prerequisites</span></span>

<span data-ttu-id="4e69c-114">このチュートリアルを完了するには、Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="4e69c-114">In order to complete this walkthrough, you'll need Visual Studio.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="4e69c-115">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="4e69c-115">Create the project</span></span>

<span data-ttu-id="4e69c-116">最初にアプリケーションのプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-116">The first step is to create the application project.</span></span> <span data-ttu-id="4e69c-117">このプロジェクトは、カスタムコントロールをホストするアプリケーションをビルドするために使用します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-117">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="4e69c-118">Visual Studio で、新しい Windows フォームアプリケーションプロジェクトを作成し、 **MarqueeControlTest**という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-118">In Visual Studio, create a new Windows Forms Application project, and name it **MarqueeControlTest**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="4e69c-119">コントロールライブラリプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="4e69c-119">Create the control library project</span></span>

1. <span data-ttu-id="4e69c-120">ソリューションに Windows フォームコントロールライブラリプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-120">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="4e69c-121">プロジェクトに**MarqueeControlLibrary**という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-121">Name the project **MarqueeControlLibrary**.</span></span>

2. <span data-ttu-id="4e69c-122">**ソリューションエクスプローラー**を使用して、選択した言語に応じて、"UserControl1.cs" または "UserControl1" という名前のソースファイルを削除して、プロジェクトの既定のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-122">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

3. <span data-ttu-id="4e69c-123">新しい <xref:System.Windows.Forms.UserControl> 項目を `MarqueeControlLibrary` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-123">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4e69c-124">新しいソースファイルに**MarqueeControl**のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-124">Give the new source file a base name of **MarqueeControl**.</span></span>

4. <span data-ttu-id="4e69c-125">**ソリューションエクスプローラー**を使用して、`MarqueeControlLibrary` プロジェクトに新しいフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-125">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span>

5. <span data-ttu-id="4e69c-126">**Design**フォルダーを右クリックし、新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-126">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="4e69c-127">**MarqueeControlRootDesigner**という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-127">Name it **MarqueeControlRootDesigner**.</span></span>

6. <span data-ttu-id="4e69c-128">System.string アセンブリの型を使用する必要があるため、この参照を `MarqueeControlLibrary` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-128">You'll need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>

## <a name="reference-the-custom-control-project"></a><span data-ttu-id="4e69c-129">カスタムコントロールプロジェクトを参照する</span><span class="sxs-lookup"><span data-stu-id="4e69c-129">Reference the Custom Control Project</span></span>

<span data-ttu-id="4e69c-130">カスタムコントロールをテストするには、`MarqueeControlTest` プロジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-130">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="4e69c-131">`MarqueeControlLibrary` アセンブリにプロジェクト参照を追加すると、テストプロジェクトはカスタムコントロールを認識するようになります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-131">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>

<span data-ttu-id="4e69c-132">`MarqueeControlTest` プロジェクトで、`MarqueeControlLibrary` アセンブリへのプロジェクト参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-132">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="4e69c-133">`MarqueeControlLibrary` アセンブリを直接参照するのではなく、 **[参照の追加]** ダイアログボックスの **[プロジェクト]** タブを使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4e69c-133">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>

## <a name="define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="4e69c-134">カスタムコントロールとそのカスタムデザイナーを定義する</span><span class="sxs-lookup"><span data-stu-id="4e69c-134">Define a Custom Control and Its Custom Designer</span></span>

<span data-ttu-id="4e69c-135">カスタムコントロールは <xref:System.Windows.Forms.UserControl> クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-135">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="4e69c-136">これにより、コントロールに他のコントロールを含めることができます。また、コントロールには、既定の機能が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="4e69c-136">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>

<span data-ttu-id="4e69c-137">カスタムコントロールには、関連付けられたカスタムデザイナーがあります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-137">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="4e69c-138">これにより、カスタムコントロール専用にカスタマイズされた独自のデザインエクスペリエンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-138">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>

<span data-ttu-id="4e69c-139">コントロールをデザイナーに関連付けるには、<xref:System.ComponentModel.DesignerAttribute> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-139">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="4e69c-140">カスタムコントロールのデザイン時動作全体を開発しているため、カスタムデザイナーは <xref:System.ComponentModel.Design.IRootDesigner> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-140">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>

### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="4e69c-141">カスタムコントロールとそのカスタムデザイナーを定義するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-141">To define a custom control and its custom designer</span></span>

1. <span data-ttu-id="4e69c-142">**コードエディター**で `MarqueeControl` ソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-142">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="4e69c-143">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-143">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <span data-ttu-id="4e69c-144"><xref:System.ComponentModel.DesignerAttribute> を `MarqueeControl` クラスの宣言に追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-144">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="4e69c-145">これにより、カスタムコントロールがデザイナーに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-145">This associates the custom control with its designer.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. <span data-ttu-id="4e69c-146">**コードエディター**で `MarqueeControlRootDesigner` ソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-146">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="4e69c-147">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-147">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. <span data-ttu-id="4e69c-148"><xref:System.Windows.Forms.Design.DocumentDesigner> クラスを継承するように `MarqueeControlRootDesigner` の宣言を変更します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-148">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="4e69c-149"><xref:System.ComponentModel.ToolboxItemFilterAttribute> を適用して、デザイナーと**ツールボックス**の対話を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-149">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4e69c-150">`MarqueeControlRootDesigner` クラスの定義は、MarqueeControlLibrary という名前空間で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="4e69c-150">The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called MarqueeControlLibrary.Design.</span></span> <span data-ttu-id="4e69c-151">この宣言により、デザイン関連の型用に予約された特殊な名前空間にデザイナーが配置されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-151">This declaration places the designer in a special namespace reserved for design-related types.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. <span data-ttu-id="4e69c-152">`MarqueeControlRootDesigner` クラスのコンストラクターを定義します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-152">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="4e69c-153"><xref:System.Diagnostics.Trace.WriteLine%2A> ステートメントをコンストラクター本体に挿入します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-153">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="4e69c-154">これはデバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-154">This will be useful for debugging.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a><span data-ttu-id="4e69c-155">カスタムコントロールのインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="4e69c-155">Create an instance of your custom control</span></span>

1. <span data-ttu-id="4e69c-156">新しい <xref:System.Windows.Forms.UserControl> 項目を `MarqueeControlTest` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-156">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="4e69c-157">新しいソースファイルに**DemoMarqueeControl**のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-157">Give the new source file a base name of **DemoMarqueeControl**.</span></span>

2. <span data-ttu-id="4e69c-158">**コードエディター**で `DemoMarqueeControl` ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-158">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="4e69c-159">ファイルの先頭に、`MarqueeControlLibrary` 名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-159">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. <span data-ttu-id="4e69c-160">`MarqueeControl` クラスを継承するように `DemoMarqueeControl` の宣言を変更します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-160">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>

4. <span data-ttu-id="4e69c-161">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-161">Build the project.</span></span>

5. <span data-ttu-id="4e69c-162">Windows フォームデザイナーで Form1 を開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-162">Open Form1 in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="4e69c-163">**ツールボックス**の **[MarqueeControlTest Components]** タブを見つけて開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-163">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="4e69c-164">**[ツールボックス]** から `DemoMarqueeControl` をフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-164">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>

7. <span data-ttu-id="4e69c-165">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-165">Build the project.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="4e69c-166">デザイン時デバッグ用にプロジェクトを設定する</span><span class="sxs-lookup"><span data-stu-id="4e69c-166">Set Up the Project for Design-Time Debugging</span></span>

<span data-ttu-id="4e69c-167">カスタムデザイン時のエクスペリエンスを開発している場合は、コントロールとコンポーネントをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-167">When you're developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="4e69c-168">デザイン時にデバッグを許可するようにプロジェクトを設定する簡単な方法があります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-168">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="4e69c-169">詳細については、「[チュートリアル: デザイン時のカスタム Windows フォームコントロールのデバッグ](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e69c-169">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

1. <span data-ttu-id="4e69c-170">`MarqueeControlLibrary` プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-170">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>

2. <span data-ttu-id="4e69c-171">**[MarqueeControlLibrary プロパティページ]** ダイアログボックスで、 **[デバッグ]** ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-171">In the **MarqueeControlLibrary Property Pages** dialog box, select the **Debug** page.</span></span>

3. <span data-ttu-id="4e69c-172">**[開始アクション]** セクションで、 **[外部プログラムの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-172">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="4e69c-173">Visual Studio の別のインスタンスをデバッグするには、省略記号![([Visual Studio のプロパティウィンドウの](./media/visual-studio-ellipsis-button.png))] ボタンをクリックして、Visual Studio IDE を参照します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-173">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="4e69c-174">実行可能ファイルの名前は devenv.exe で、を既定の場所にインストールした場合、そのパスは *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<edition > \Common7\IDE\devenv.exe*になります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-174">The name of the executable file is devenv.exe, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE\devenv.exe*.</span></span>

4. <span data-ttu-id="4e69c-175">**[OK]** を選択してダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-175">Select **OK** to close the dialog box.</span></span>

5. <span data-ttu-id="4e69c-176">MarqueeControlLibrary プロジェクトを右クリックし、 **[スタートアッププロジェクトに設定]** を選択して、このデバッグ構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-176">Right-click the MarqueeControlLibrary project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="4e69c-177">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="4e69c-177">Checkpoint</span></span>

<span data-ttu-id="4e69c-178">これで、カスタムコントロールのデザイン時動作をデバッグする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="4e69c-178">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="4e69c-179">デバッグ環境が正しく設定されていることを確認したら、カスタムコントロールとカスタムデザイナーの関連付けをテストします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-179">Once you've determined that the debugging environment is set up correctly, you'll test the association between the custom control and the custom designer.</span></span>

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="4e69c-180">デバッグ環境とデザイナーの関連付けをテストするには</span><span class="sxs-lookup"><span data-stu-id="4e69c-180">To test the debugging environment and the designer association</span></span>

1. <span data-ttu-id="4e69c-181">**コードエディター**で MarqueeControlRootDesigner ソースファイルを開き、<xref:System.Diagnostics.Trace.WriteLine%2A> ステートメントにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-181">Open the MarqueeControlRootDesigner source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>

2. <span data-ttu-id="4e69c-182">**F5**キーを押してデバッグセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-182">Press **F5** to start the debugging session.</span></span>

   <span data-ttu-id="4e69c-183">Visual Studio の新しいインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-183">A new instance of Visual Studio is created.</span></span>

3. <span data-ttu-id="4e69c-184">Visual Studio の新しいインスタンスで、MarqueeControlTest ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-184">In the new instance of Visual Studio, open the MarqueeControlTest solution.</span></span> <span data-ttu-id="4e69c-185">**[ファイル]** メニューから **[最近使ったプロジェクト]** を選択すると、ソリューションを簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-185">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="4e69c-186">MarqueeControlTest ソリューションファイルは、最近使用したファイルとして一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-186">The MarqueeControlTest.sln solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="4e69c-187">デザイナーで `DemoMarqueeControl` を開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-187">Open the `DemoMarqueeControl` in the designer.</span></span>

   <span data-ttu-id="4e69c-188">Visual Studio のデバッグインスタンスによってフォーカスが取得され、ブレークポイントで実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-188">The debugging instance of Visual Studio obtains focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="4e69c-189">**F5**キーを押してデバッグセッションを続行します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-189">Press **F5** to continue the debugging session.</span></span>

<span data-ttu-id="4e69c-190">この時点で、カスタムコントロールとそれに関連付けられているカスタムデザイナーを開発およびデバッグするために、すべてが準備されています。</span><span class="sxs-lookup"><span data-stu-id="4e69c-190">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="4e69c-191">この記事の残りの部分では、コントロールとデザイナーの機能を実装する方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-191">The remainder of this article concentrates on the details of implementing features of the control and the designer.</span></span>

## <a name="implement-the-custom-control"></a><span data-ttu-id="4e69c-192">カスタムコントロールを実装する</span><span class="sxs-lookup"><span data-stu-id="4e69c-192">Implement the Custom Control</span></span>

<span data-ttu-id="4e69c-193">`MarqueeControl` は、カスタマイズが少ししかない <xref:System.Windows.Forms.UserControl> です。</span><span class="sxs-lookup"><span data-stu-id="4e69c-193">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="4e69c-194">これは、マーキーアニメーションを開始する `Start`と、アニメーションを停止する `Stop`の2つのメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-194">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="4e69c-195">`MarqueeControl` には `IMarqueeWidget` インターフェイスを実装する子コントロールが含まれているため、`StartMarquee` を実装する各子コントロールに対して、それぞれの子コントロールを `Start` および `Stop` 列挙し、それぞれ `StopMarquee` メソッドと `IMarqueeWidget`メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-195">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>

<span data-ttu-id="4e69c-196">`MarqueeBorder` コントロールと `MarqueeText` コントロールの外観はレイアウトに依存しているため、`MarqueeControl` は <xref:System.Windows.Forms.Control.OnLayout%2A> メソッドをオーバーライドし、この型の子コントロールに対して <xref:System.Windows.Forms.Control.PerformLayout%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-196">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>

<span data-ttu-id="4e69c-197">これは `MarqueeControl` カスタマイズの範囲です。</span><span class="sxs-lookup"><span data-stu-id="4e69c-197">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="4e69c-198">実行時の機能は `MarqueeBorder` および `MarqueeText` コントロールによって実装され、デザイン時の機能は `MarqueeBorderDesigner` クラスと `MarqueeControlRootDesigner` クラスによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-198">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>

### <a name="to-implement-your-custom-control"></a><span data-ttu-id="4e69c-199">カスタムコントロールを実装するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-199">To implement your custom control</span></span>

1. <span data-ttu-id="4e69c-200">**コードエディター**で `MarqueeControl` ソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-200">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="4e69c-201">`Start` メソッドと `Stop` メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-201">Implement the `Start` and `Stop` methods.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. <span data-ttu-id="4e69c-202"><xref:System.Windows.Forms.Control.OnLayout%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-202">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a><span data-ttu-id="4e69c-203">カスタムコントロールの子コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="4e69c-203">Create a Child Control for Your Custom Control</span></span>

<span data-ttu-id="4e69c-204">`MarqueeControl` は、`MarqueeBorder` コントロールと `MarqueeText` コントロールの2種類の子コントロールをホストします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-204">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>

- <span data-ttu-id="4e69c-205">`MarqueeBorder`: このコントロールは、端の周りに "ライト" の境界線を描画します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-205">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="4e69c-206">ライトが連続して点滅しているように見えます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-206">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="4e69c-207">ライトフラッシュが `UpdatePeriod`というプロパティによって制御される速度。</span><span class="sxs-lookup"><span data-stu-id="4e69c-207">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="4e69c-208">他のいくつかのカスタムプロパティによって、コントロールの外観の他の側面が決まります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-208">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="4e69c-209">`StartMarquee` と `StopMarquee`と呼ばれる2つのメソッドは、アニメーションの開始時と停止時に制御します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-209">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>

- <span data-ttu-id="4e69c-210">`MarqueeText`: このコントロールは、点滅する文字列を描画します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-210">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="4e69c-211">`MarqueeBorder` コントロールと同様に、テキストが点滅する速度は、`UpdatePeriod` プロパティによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-211">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="4e69c-212">`MarqueeText` コントロールには、`MarqueeBorder` コントロールと共通の `StartMarquee` および `StopMarquee` メソッドもあります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-212">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>

<span data-ttu-id="4e69c-213">デザイン時には、この `MarqueeControlRootDesigner` によって、これら2つのコントロール型を任意の組み合わせで `MarqueeControl` に追加できます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-213">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>

<span data-ttu-id="4e69c-214">2つのコントロールの共通機能は、`IMarqueeWidget`と呼ばれるインターフェイスに考慮されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-214">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="4e69c-215">これにより、`MarqueeControl` は、マーキーに関連する子コントロールを検出し、特別な処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-215">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>

<span data-ttu-id="4e69c-216">定期的なアニメーション機能を実装するには、<xref:System.ComponentModel?displayProperty=nameWithType> 名前空間の <xref:System.ComponentModel.BackgroundWorker> オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-216">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="4e69c-217"><xref:System.Windows.Forms.Timer> オブジェクトを使用することもできますが、多くの `IMarqueeWidget` オブジェクトが存在すると、1つの UI スレッドがアニメーションを維持できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-217">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>

### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="4e69c-218">カスタムコントロールの子コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-218">To create a child control for your custom control</span></span>

1. <span data-ttu-id="4e69c-219">新しいクラス項目を `MarqueeControlLibrary` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-219">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4e69c-220">新しいソースファイルに "IMarqueeWidget" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-220">Give the new source file a base name of "IMarqueeWidget."</span></span>

2. <span data-ttu-id="4e69c-221">**コードエディター**で `IMarqueeWidget` ソースファイルを開き、宣言を `class` から `interface`に変更します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-221">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. <span data-ttu-id="4e69c-222">次のコードを `IMarqueeWidget` インターフェイスに追加して、2つのメソッドと、マーキーアニメーションを操作するプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-222">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. <span data-ttu-id="4e69c-223">新しい**カスタムコントロール**項目を `MarqueeControlLibrary` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-223">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4e69c-224">新しいソースファイルに "MarqueeText" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-224">Give the new source file a base name of "MarqueeText."</span></span>

5. <span data-ttu-id="4e69c-225"><xref:System.ComponentModel.BackgroundWorker> コンポーネントを **[ツールボックス]** から `MarqueeText` コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-225">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="4e69c-226">このコンポーネントを使用すると、`MarqueeText` コントロール自体を非同期的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-226">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>

6. <span data-ttu-id="4e69c-227">**[プロパティ]** ウィンドウで、<xref:System.ComponentModel.BackgroundWorker> コンポーネントの `WorkerReportsProgress` と <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-227">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to **true**.</span></span> <span data-ttu-id="4e69c-228">これらの設定により、<xref:System.ComponentModel.BackgroundWorker> コンポーネントは定期的に <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントを発生させ、非同期更新を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-228">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span>

   <span data-ttu-id="4e69c-229">詳細については、「 [BackgroundWorker Component](backgroundworker-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e69c-229">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

7. <span data-ttu-id="4e69c-230">**コードエディター**で `MarqueeText` ソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-230">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="4e69c-231">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-231">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. <span data-ttu-id="4e69c-232"><xref:System.Windows.Forms.Label> から継承するように `MarqueeText` の宣言を変更し、`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-232">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. <span data-ttu-id="4e69c-233">公開されたプロパティに対応するインスタンス変数を宣言し、コンストラクターで初期化します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-233">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="4e69c-234">`isLit` フィールドは、`LightColor` プロパティによって指定された色でテキストを描画するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-234">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. <span data-ttu-id="4e69c-235">`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-235">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="4e69c-236">`StartMarquee` メソッドと `StopMarquee` メソッドは、<xref:System.ComponentModel.BackgroundWorker> コンポーネントの <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> および <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> メソッドを呼び出して、アニメーションを開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-236">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="4e69c-237"><xref:System.ComponentModel.CategoryAttribute.Category%2A> 属性と <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 属性が `UpdatePeriod` プロパティに適用されるため、"Marquee" と呼ばれるプロパティウィンドウのカスタムセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-237">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. <span data-ttu-id="4e69c-238">プロパティアクセサーを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-238">Implement the property accessors.</span></span> <span data-ttu-id="4e69c-239">クライアントには、`LightColor` と `DarkColor`の2つのプロパティが公開されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-239">You'll expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="4e69c-240">これらのプロパティには <xref:System.ComponentModel.CategoryAttribute.Category%2A> 属性と <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 属性が適用されるため、"Marquee" と呼ばれるプロパティウィンドウのカスタムセクションにプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-240">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. <span data-ttu-id="4e69c-241"><xref:System.ComponentModel.BackgroundWorker> コンポーネントの <xref:System.ComponentModel.BackgroundWorker.DoWork> イベントと <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-241">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="4e69c-242"><xref:System.ComponentModel.BackgroundWorker.DoWork> イベントハンドラーは、`UpdatePeriod` によって指定されたミリ秒数、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントを発生させます。これにより、コードは <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>を呼び出してアニメーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-242">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="4e69c-243"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントハンドラーは、テキストを淡色と濃色の状態の間で切り替えて、点滅のようにします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-243">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. <span data-ttu-id="4e69c-244">アニメーションを有効にするには、<xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-244">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. <span data-ttu-id="4e69c-245">**F6** キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-245">Press **F6** to build the solution.</span></span>

## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="4e69c-246">MarqueeBorder 子コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="4e69c-246">Create the MarqueeBorder Child Control</span></span>

<span data-ttu-id="4e69c-247">`MarqueeBorder` コントロールは、`MarqueeText` コントロールよりも多少洗練されています。</span><span class="sxs-lookup"><span data-stu-id="4e69c-247">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="4e69c-248">これには、さらに多くのプロパティがあり、<xref:System.Windows.Forms.Control.OnPaint%2A> メソッドのアニメーションも複雑になります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-248">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="4e69c-249">原則として、`MarqueeText` コントロールと非常によく似ています。</span><span class="sxs-lookup"><span data-stu-id="4e69c-249">In principle, it is quite similar to the `MarqueeText` control.</span></span>

<span data-ttu-id="4e69c-250">`MarqueeBorder` コントロールは子コントロールを持つことができるため、<xref:System.Windows.Forms.Control.Layout> イベントに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-250">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>

### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="4e69c-251">MarqueeBorder コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-251">To create the MarqueeBorder control</span></span>

1. <span data-ttu-id="4e69c-252">新しい**カスタムコントロール**項目を `MarqueeControlLibrary` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-252">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4e69c-253">新しいソースファイルに "MarqueeBorder" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-253">Give the new source file a base name of "MarqueeBorder."</span></span>

2. <span data-ttu-id="4e69c-254"><xref:System.ComponentModel.BackgroundWorker> コンポーネントを **[ツールボックス]** から `MarqueeBorder` コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-254">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="4e69c-255">このコンポーネントを使用すると、`MarqueeBorder` コントロール自体を非同期的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-255">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>

3. <span data-ttu-id="4e69c-256">**[プロパティ]** ウィンドウで、<xref:System.ComponentModel.BackgroundWorker> コンポーネントの `WorkerReportsProgress` と <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-256">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to **true**.</span></span> <span data-ttu-id="4e69c-257">これらの設定により、<xref:System.ComponentModel.BackgroundWorker> コンポーネントは定期的に <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントを発生させ、非同期更新を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-257">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="4e69c-258">詳細については、「 [BackgroundWorker Component](backgroundworker-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e69c-258">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

4. <span data-ttu-id="4e69c-259">**[プロパティ]** ウィンドウで、 **[イベント]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-259">In the **Properties** window, select the **Events** button.</span></span> <span data-ttu-id="4e69c-260"><xref:System.ComponentModel.BackgroundWorker.DoWork> イベントと <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントのハンドラーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-260">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

5. <span data-ttu-id="4e69c-261">**コードエディター**で `MarqueeBorder` ソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-261">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="4e69c-262">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-262">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. <span data-ttu-id="4e69c-263"><xref:System.Windows.Forms.Panel> から継承するように `MarqueeBorder` の宣言を変更し、`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-263">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. <span data-ttu-id="4e69c-264">`MarqueeBorder` コントロールの状態を管理するための2つの列挙体を宣言します。 `MarqueeSpinDirection`は、光源の周囲を "スピン" する方向を決定し、`MarqueeLightShape`、ライトの形状 (正方形または円) を決定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-264">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="4e69c-265">これらの宣言は `MarqueeBorder` クラス宣言の前に配置します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-265">Place these declarations before the `MarqueeBorder` class declaration.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. <span data-ttu-id="4e69c-266">公開されたプロパティに対応するインスタンス変数を宣言し、コンストラクターで初期化します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-266">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. <span data-ttu-id="4e69c-267">`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-267">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="4e69c-268">`StartMarquee` メソッドと `StopMarquee` メソッドは、<xref:System.ComponentModel.BackgroundWorker> コンポーネントの <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> および <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> メソッドを呼び出して、アニメーションを開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-268">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="4e69c-269">`MarqueeBorder` コントロールには子コントロールを含めることができるため、`StartMarquee` メソッドは、すべての子コントロールを列挙し、`IMarqueeWidget`を実装するコントロールに対して `StartMarquee` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-269">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="4e69c-270">`StopMarquee` メソッドには同様の実装があります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-270">The `StopMarquee` method has a similar implementation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. <span data-ttu-id="4e69c-271">プロパティアクセサーを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-271">Implement the property accessors.</span></span> <span data-ttu-id="4e69c-272">`MarqueeBorder` コントロールには、外観を制御するためのプロパティがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-272">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. <span data-ttu-id="4e69c-273"><xref:System.ComponentModel.BackgroundWorker> コンポーネントの <xref:System.ComponentModel.BackgroundWorker.DoWork> イベントと <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-273">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="4e69c-274"><xref:System.ComponentModel.BackgroundWorker.DoWork> イベントハンドラーは、`UpdatePeriod` によって指定されたミリ秒数、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントを発生させます。これにより、コードは <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>を呼び出してアニメーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-274">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="4e69c-275"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントハンドラーは、他のライトのライト/ダーク状態が決定される "基本" ライトの位置をインクリメントし、<xref:System.Windows.Forms.Control.Refresh%2A> メソッドを呼び出して、コントロール自体を再描画します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-275">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. <span data-ttu-id="4e69c-276">ヘルパーメソッド、`IsLit` および `DrawLight`を実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-276">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>

    <span data-ttu-id="4e69c-277">`IsLit` メソッドは、指定された位置にあるライトの色を決定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-277">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="4e69c-278">"Lit" のライトは、`LightColor` プロパティによって指定された色で描画され、"ダーク" であるライトは、`DarkColor` プロパティによって指定された色で描画されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-278">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>

    <span data-ttu-id="4e69c-279">`DrawLight` メソッドは、適切な色、形状、および位置を使用してライトを描画します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-279">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. <span data-ttu-id="4e69c-280"><xref:System.Windows.Forms.Control.OnLayout%2A> メソッドと <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-280">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>

    <span data-ttu-id="4e69c-281"><xref:System.Windows.Forms.Control.OnPaint%2A> メソッドは、`MarqueeBorder` コントロールの端に沿ってライトを描画します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-281">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>

    <span data-ttu-id="4e69c-282"><xref:System.Windows.Forms.Control.OnPaint%2A> メソッドは `MarqueeBorder` コントロールの大きさに依存しているため、レイアウトが変更されるたびに呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-282">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="4e69c-283">これを実現するには、<xref:System.Windows.Forms.Control.OnLayout%2A> をオーバーライドし、<xref:System.Windows.Forms.Control.Refresh%2A>を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-283">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="4e69c-284">カスタムデザイナーを作成してプロパティをシャドウおよびフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="4e69c-284">Create a Custom Designer to Shadow and Filter Properties</span></span>

<span data-ttu-id="4e69c-285">`MarqueeControlRootDesigner` クラスは、ルートデザイナーの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-285">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="4e69c-286">`MarqueeControl`で動作するこのデザイナーに加えて、`MarqueeBorder` コントロールに特に関連付けられたカスタムデザイナーが必要です。</span><span class="sxs-lookup"><span data-stu-id="4e69c-286">In addition to this designer, which operates on the `MarqueeControl`, you'll need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="4e69c-287">このデザイナーには、カスタムルートデザイナーのコンテキストに適したカスタム動作が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4e69c-287">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>

<span data-ttu-id="4e69c-288">具体的には、`MarqueeBorderDesigner` は `MarqueeBorder` コントロールの特定のプロパティを "シャドウ" してフィルター処理し、デザイン環境との相互作用を変更します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-288">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>

<span data-ttu-id="4e69c-289">コンポーネントのプロパティアクセサーへの呼び出しのインターセプトは、"シャドウ処理" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-289">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="4e69c-290">これにより、デザイナーはユーザーが設定した値を追跡し、必要に応じてその値をデザイン対象のコンポーネントに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-290">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>

<span data-ttu-id="4e69c-291">この例では、<xref:System.Windows.Forms.Control.Visible%2A> プロパティと <xref:System.Windows.Forms.Control.Enabled%2A> プロパティが `MarqueeBorderDesigner`によってシャドウされます。これにより、デザイン時にユーザーが `MarqueeBorder` コントロールを非表示または無効にすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-291">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>

<span data-ttu-id="4e69c-292">デザイナーでは、プロパティを追加および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-292">Designers can also add and remove properties.</span></span> <span data-ttu-id="4e69c-293">この例では、`MarqueeBorder` コントロールは `LightSize` プロパティによって指定されたライトのサイズに基づいて埋め込みを設定するため、デザイン時に <xref:System.Windows.Forms.Control.Padding%2A> プロパティは削除されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-293">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>

<span data-ttu-id="4e69c-294">`MarqueeBorderDesigner` の基本クラスは <xref:System.ComponentModel.Design.ComponentDesigner>です。このクラスには、デザイン時にコントロールによって公開される属性、プロパティ、およびイベントを変更するためのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-294">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

<span data-ttu-id="4e69c-295">これらのメソッドを使用してコンポーネントのパブリックインターフェイスを変更する場合は、次の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="4e69c-295">When changing the public interface of a component using these methods, follow these rules:</span></span>

- <span data-ttu-id="4e69c-296">`PreFilter` メソッドでのみ項目を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="4e69c-296">Add or remove items in the `PreFilter` methods only</span></span>

- <span data-ttu-id="4e69c-297">`PostFilter` メソッドの既存の項目のみを変更する</span><span class="sxs-lookup"><span data-stu-id="4e69c-297">Modify existing items in the `PostFilter` methods only</span></span>

- <span data-ttu-id="4e69c-298">常に基本実装を `PreFilter` メソッドで呼び出す</span><span class="sxs-lookup"><span data-stu-id="4e69c-298">Always call the base implementation first in the `PreFilter` methods</span></span>

- <span data-ttu-id="4e69c-299">`PostFilter` メソッドの最後に基本実装を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-299">Always call the base implementation last in the `PostFilter` methods</span></span>

<span data-ttu-id="4e69c-300">これらの規則に従うことで、デザイン時環境のすべてのデザイナーが、デザインされているすべてのコンポーネントの一貫したビューを確実に表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-300">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>

<span data-ttu-id="4e69c-301"><xref:System.ComponentModel.Design.ComponentDesigner> クラスは、シャドウプロパティの値を管理するためのディクショナリを提供します。これにより、特定のインスタンス変数を作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-301">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="4e69c-302">プロパティをシャドウおよびフィルター処理するためのカスタムデザイナーを作成するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-302">To create a custom designer to shadow and filter properties</span></span>

1. <span data-ttu-id="4e69c-303">**Design**フォルダーを右クリックし、新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-303">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="4e69c-304">ソースファイルに**MarqueeBorderDesigner**のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-304">Give the source file a base name of **MarqueeBorderDesigner**.</span></span>

2. <span data-ttu-id="4e69c-305">**コードエディター**で MarqueeBorderDesigner ソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-305">Open the MarqueeBorderDesigner source file in the **Code Editor**.</span></span> <span data-ttu-id="4e69c-306">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-306">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. <span data-ttu-id="4e69c-307"><xref:System.Windows.Forms.Design.ParentControlDesigner>から継承するように `MarqueeBorderDesigner` の宣言を変更します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-307">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>

    <span data-ttu-id="4e69c-308">`MarqueeBorder` コントロールには子コントロールを含めることができるため、`MarqueeBorderDesigner` は親子の相互作用を処理する <xref:System.Windows.Forms.Design.ParentControlDesigner>から継承されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-308">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. <span data-ttu-id="4e69c-309"><xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>の基本実装をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-309">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. <span data-ttu-id="4e69c-310"><xref:System.Windows.Forms.Control.Enabled%2A> プロパティと <xref:System.Windows.Forms.Control.Visible%2A> プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-310">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="4e69c-311">これらの実装は、コントロールのプロパティをシャドウします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-311">These implementations shadow the control's properties.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a><span data-ttu-id="4e69c-312">コンポーネントの変更を処理する</span><span class="sxs-lookup"><span data-stu-id="4e69c-312">Handle Component Changes</span></span>

<span data-ttu-id="4e69c-313">`MarqueeControlRootDesigner` クラスは、`MarqueeControl` インスタンスのカスタムデザイン時エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-313">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="4e69c-314">デザイン時の機能のほとんどは、<xref:System.Windows.Forms.Design.DocumentDesigner> クラスから継承されています。</span><span class="sxs-lookup"><span data-stu-id="4e69c-314">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="4e69c-315">コードには、コンポーネントの変更の処理とデザイナー動詞の追加という2つのカスタマイズのカスタマイズが実装されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-315">Your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>

<span data-ttu-id="4e69c-316">ユーザーが `MarqueeControl` インスタンスをデザインすると、ルートデザイナーは `MarqueeControl` とその子コントロールに対する変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-316">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="4e69c-317">デザイン時環境では、コンポーネントの状態への変更を追跡するための便利なサービス <xref:System.ComponentModel.Design.IComponentChangeService>が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-317">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>

<span data-ttu-id="4e69c-318">このサービスへの参照を取得するには、<xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> メソッドを使用して環境に対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-318">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="4e69c-319">クエリが成功した場合、デザイナーは <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> イベントのハンドラーをアタッチし、デザイン時に一貫性のある状態を維持するために必要なすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-319">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>

<span data-ttu-id="4e69c-320">`MarqueeControlRootDesigner` クラスの場合は、`MarqueeControl`に含まれる各 `IMarqueeWidget` オブジェクトで <xref:System.Windows.Forms.Control.Refresh%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-320">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="4e69c-321">これにより、親の <xref:System.Windows.Forms.Control.Size%2A> のようなプロパティが変更された場合に、`IMarqueeWidget` オブジェクトが適切に再描画されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-321">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>

### <a name="to-handle-component-changes"></a><span data-ttu-id="4e69c-322">コンポーネントの変更を処理するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-322">To handle component changes</span></span>

1. <span data-ttu-id="4e69c-323">**コードエディター**で `MarqueeControlRootDesigner` ソースファイルを開き、<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-323">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="4e69c-324"><xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> の基本実装を呼び出し、<xref:System.ComponentModel.Design.IComponentChangeService>に対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-324">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. <span data-ttu-id="4e69c-325"><xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> イベントハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-325">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="4e69c-326">送信コンポーネントの型をテストし、それが `IMarqueeWidget`である場合は、その <xref:System.Windows.Forms.Control.Refresh%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-326">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="4e69c-327">デザイナー動詞をカスタムデザイナーに追加する</span><span class="sxs-lookup"><span data-stu-id="4e69c-327">Add Designer Verbs to your Custom Designer</span></span>

<span data-ttu-id="4e69c-328">デザイナー動詞は、イベント ハンドラーにリンクされたメニュー コマンドです。</span><span class="sxs-lookup"><span data-stu-id="4e69c-328">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="4e69c-329">デザイナー動詞は、デザイン時にコンポーネントのショートカットメニューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-329">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="4e69c-330">詳細については、<xref:System.ComponentModel.Design.DesignerVerb> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e69c-330">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>

<span data-ttu-id="4e69c-331">デザイナーに2つのデザイナー動詞を追加します。**テストを実行**し、**テストを停止**します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-331">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="4e69c-332">これらの動詞を使用すると、デザイン時に `MarqueeControl` の実行時の動作を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-332">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="4e69c-333">これらの動詞は `MarqueeControlRootDesigner`に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-333">These verbs will be added to `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="4e69c-334">**実行テスト**が呼び出されると、動詞イベントハンドラーが `MarqueeControl`で `StartMarquee` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-334">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="4e69c-335">**停止テスト**が呼び出されると、動詞イベントハンドラーは `MarqueeControl`で `StopMarquee` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-335">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="4e69c-336">`StartMarquee` メソッドと `StopMarquee` メソッドの実装では、`IMarqueeWidget`を実装する含まれるコントロールに対してこれらのメソッドを呼び出します。そのため、含まれているすべての `IMarqueeWidget` コントロールもテストに関与します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-336">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>

### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="4e69c-337">デザイナー動詞をカスタムデザイナーに追加するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-337">To add designer verbs to your custom designers</span></span>

1. <span data-ttu-id="4e69c-338">`MarqueeControlRootDesigner` クラスで、`OnVerbRunTest` と `OnVerbStopTest`という名前のイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-338">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. <span data-ttu-id="4e69c-339">これらのイベントハンドラーを、対応するデザイナー動詞に接続します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-339">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="4e69c-340">`MarqueeControlRootDesigner` は、基本クラスから <xref:System.ComponentModel.Design.DesignerVerbCollection> を継承します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-340">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="4e69c-341">2つの新しい <xref:System.ComponentModel.Design.DesignerVerb> オブジェクトを作成し、<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> メソッドでこのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-341">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a><span data-ttu-id="4e69c-342">カスタム UITypeEditor を作成する</span><span class="sxs-lookup"><span data-stu-id="4e69c-342">Create a Custom UITypeEditor</span></span>

<span data-ttu-id="4e69c-343">ユーザーに対してカスタムのデザイン時エクスペリエンスを作成する場合、多くの場合、プロパティウィンドウとのカスタム操作を作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-343">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="4e69c-344">これを行うには、<xref:System.Drawing.Design.UITypeEditor>を作成します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-344">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span>

<span data-ttu-id="4e69c-345">`MarqueeBorder` コントロールは、プロパティウィンドウ内のいくつかのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-345">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="4e69c-346">これらのプロパティのうち、`MarqueeSpinDirection` と `MarqueeLightShape` の2つが列挙体によって表されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-346">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="4e69c-347">UI 型エディターの使用方法を示すために、`MarqueeLightShape` プロパティには関連付けられた <xref:System.Drawing.Design.UITypeEditor> クラスがあります。</span><span class="sxs-lookup"><span data-stu-id="4e69c-347">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>

### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="4e69c-348">カスタム UI 型エディターを作成するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-348">To create a custom UI type editor</span></span>

1. <span data-ttu-id="4e69c-349">**コードエディター**で `MarqueeBorder` ソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-349">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>

2. <span data-ttu-id="4e69c-350">`MarqueeBorder` クラスの定義で、<xref:System.Drawing.Design.UITypeEditor>から派生する `LightShapeEditor` というクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-350">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. <span data-ttu-id="4e69c-351">`editorService`と呼ばれる <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> インスタンス変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-351">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. <span data-ttu-id="4e69c-352"><xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-352">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="4e69c-353">この実装は <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>を返します。これは、デザイン環境に `LightShapeEditor`を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-353">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. <span data-ttu-id="4e69c-354"><xref:System.Drawing.Design.UITypeEditor.EditValue%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-354">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="4e69c-355">この実装は、<xref:System.Windows.Forms.Design.IWindowsFormsEditorService> オブジェクトのデザイン環境に対してクエリを行います。</span><span class="sxs-lookup"><span data-stu-id="4e69c-355">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="4e69c-356">成功すると、`LightShapeSelectionControl`が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-356">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="4e69c-357"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> メソッドは、`LightShapeEditor`を開始するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-357">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="4e69c-358">この呼び出しからの戻り値がデザイン環境に返されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-358">The return value from this invocation is returned to the design environment.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="4e69c-359">カスタム UITypeEditor のビューコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="4e69c-359">Create a View Control for your Custom UITypeEditor</span></span>

<span data-ttu-id="4e69c-360">`MarqueeLightShape` プロパティは、`Square` と `Circle`の2種類のライト形状をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4e69c-360">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="4e69c-361">プロパティウィンドウでこれらの値をグラフィカルに表示する目的でのみ使用されるカスタムコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-361">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="4e69c-362">このカスタムコントロールは、プロパティウィンドウと対話するために <xref:System.Drawing.Design.UITypeEditor> によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-362">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="4e69c-363">カスタム UI 型エディターのビューコントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-363">To create a view control for your custom UI type editor</span></span>

1. <span data-ttu-id="4e69c-364">新しい <xref:System.Windows.Forms.UserControl> 項目を `MarqueeControlLibrary` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-364">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4e69c-365">新しいソースファイルに**LightShapeSelectionControl**のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-365">Give the new source file a base name of **LightShapeSelectionControl**.</span></span>

2. <span data-ttu-id="4e69c-366">**ツールボックス**から2つの <xref:System.Windows.Forms.Panel> コントロールを `LightShapeSelectionControl`にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-366">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="4e69c-367">名前を `squarePanel` し、`circlePanel`します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-367">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="4e69c-368">それらを並べて配置します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-368">Arrange them side by side.</span></span> <span data-ttu-id="4e69c-369">両方の <xref:System.Windows.Forms.Panel> コントロールの <xref:System.Windows.Forms.Control.Size%2A> プロパティを **(60, 60)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-369">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to **(60, 60)**.</span></span> <span data-ttu-id="4e69c-370">`squarePanel` コントロールの <xref:System.Windows.Forms.Control.Location%2A> プロパティを **(8, 10)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-370">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to **(8, 10)**.</span></span> <span data-ttu-id="4e69c-371">`circlePanel` コントロールの <xref:System.Windows.Forms.Control.Location%2A> プロパティを **(80, 10)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-371">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to **(80, 10)**.</span></span> <span data-ttu-id="4e69c-372">最後に、`LightShapeSelectionControl` の <xref:System.Windows.Forms.Control.Size%2A> プロパティを **(150, 80)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-372">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to **(150, 80)**.</span></span>

3. <span data-ttu-id="4e69c-373">**コードエディター**で `LightShapeSelectionControl` ソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-373">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="4e69c-374">ファイルの先頭に、<xref:System.Windows.Forms.Design?displayProperty=nameWithType> 名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-374">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. <span data-ttu-id="4e69c-375">`squarePanel` コントロールと `circlePanel` コントロールに対して <xref:System.Windows.Forms.Control.Click> イベントハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-375">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="4e69c-376">これらのメソッドは <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> を呼び出して、カスタム <xref:System.Drawing.Design.UITypeEditor> 編集セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-376">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. <span data-ttu-id="4e69c-377">`editorService`と呼ばれる <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> インスタンス変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-377">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. <span data-ttu-id="4e69c-378">`lightShapeValue`と呼ばれる `MarqueeLightShape` インスタンス変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-378">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. <span data-ttu-id="4e69c-379">`LightShapeSelectionControl` コンストラクターで、<xref:System.Windows.Forms.Control.Click> イベントハンドラーを `squarePanel` および `circlePanel` コントロールの <xref:System.Windows.Forms.Control.Click> イベントにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-379">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="4e69c-380">また、デザイン環境から `lightShapeValue` フィールドに `MarqueeLightShape` 値を割り当てるコンストラクターのオーバーロードを定義します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-380">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. <span data-ttu-id="4e69c-381"><xref:System.ComponentModel.Component.Dispose%2A> メソッドで、<xref:System.Windows.Forms.Control.Click> イベントハンドラーをデタッチします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-381">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. <span data-ttu-id="4e69c-382">**ソリューション エクスプローラー**で、 **[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-382">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="4e69c-383">LightShapeSelectionControl.Designer.cs または LightShapeSelectionControl ファイルを開き、<xref:System.ComponentModel.Component.Dispose%2A> メソッドの既定の定義を削除します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-383">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>

10. <span data-ttu-id="4e69c-384">`LightShape` プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-384">Implement the `LightShape` property.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. <span data-ttu-id="4e69c-385"><xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-385">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="4e69c-386">この実装では、塗りつぶされた正方形と円を描画します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-386">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="4e69c-387">また、1つの図形の周りに境界線を描画して、選択された値を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-387">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a><span data-ttu-id="4e69c-388">デザイナーでカスタムコントロールをテストする</span><span class="sxs-lookup"><span data-stu-id="4e69c-388">Test your Custom Control in the Designer</span></span>

<span data-ttu-id="4e69c-389">この時点で、`MarqueeControlLibrary` プロジェクトをビルドできます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-389">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4e69c-390">`MarqueeControl` クラスから継承し、フォームで使用するコントロールを作成して、実装をテストします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-390">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>

### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="4e69c-391">カスタムの MarqueeControl 実装を作成するには</span><span class="sxs-lookup"><span data-stu-id="4e69c-391">To create a custom MarqueeControl implementation</span></span>

1. <span data-ttu-id="4e69c-392">Windows フォーム デザイナーで `DemoMarqueeControl` を開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-392">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="4e69c-393">これにより `DemoMarqueeControl` 型のインスタンスが作成され、`MarqueeControlRootDesigner` 型のインスタンスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-393">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>

2. <span data-ttu-id="4e69c-394">**ツールボックス**で、 **[MarqueeControlLibrary Components]** タブを開きます。選択できる `MarqueeBorder` および `MarqueeText` コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-394">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>

3. <span data-ttu-id="4e69c-395">`MarqueeBorder` コントロールのインスタンスを `DemoMarqueeControl` デザインサーフェイスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-395">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="4e69c-396">この `MarqueeBorder` コントロールを親コントロールにドッキングします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-396">Dock this `MarqueeBorder` control to the parent control.</span></span>

4. <span data-ttu-id="4e69c-397">`MarqueeText` コントロールのインスタンスを `DemoMarqueeControl` デザインサーフェイスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-397">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>

5. <span data-ttu-id="4e69c-398">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-398">Build the solution.</span></span>

6. <span data-ttu-id="4e69c-399">`DemoMarqueeControl` を右クリックし、ショートカットメニューの **[テストの実行]** オプションを選択して、アニメーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-399">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="4e69c-400">アニメーションを停止するには、 **[テストの停止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-400">Click **Stop Test** to stop the animation.</span></span>

7. <span data-ttu-id="4e69c-401">デザイン ビューで **[Form1]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-401">Open **Form1** in Design view.</span></span>

8. <span data-ttu-id="4e69c-402">フォームに2つの <xref:System.Windows.Forms.Button> コントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-402">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="4e69c-403">名前を `startButton` して `stopButton`し、<xref:System.Windows.Forms.Control.Text%2A> プロパティの値をそれぞれ**Start**および**Stop**に変更します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-403">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>

9. <span data-ttu-id="4e69c-404">両方の <xref:System.Windows.Forms.Button> コントロールに <xref:System.Windows.Forms.Control.Click> イベントハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-404">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>

10. <span data-ttu-id="4e69c-405">**ツールボックス**で、 **[MarqueeControlTest Components]** タブを開きます。選択できる `DemoMarqueeControl` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-405">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>

11. <span data-ttu-id="4e69c-406">`DemoMarqueeControl` のインスタンスを**Form1**デザインサーフェイスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-406">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>

12. <span data-ttu-id="4e69c-407"><xref:System.Windows.Forms.Control.Click> イベントハンドラーで、`DemoMarqueeControl`の `Start` および `Stop` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-407">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>

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

13. <span data-ttu-id="4e69c-408">`MarqueeControlTest` プロジェクトをスタートアッププロジェクトとして設定し、実行します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-408">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="4e69c-409">`DemoMarqueeControl`を表示するフォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-409">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="4e69c-410">**[開始]** ボタンを選択して、アニメーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-410">Select the **Start** button to start the animation.</span></span> <span data-ttu-id="4e69c-411">テキストが点滅し、ライトが境界内を移動していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-411">You should see the text flashing and the lights moving around the border.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e69c-412">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4e69c-412">Next steps</span></span>

<span data-ttu-id="4e69c-413">`MarqueeControlLibrary` は、カスタムコントロールおよび関連するデザイナーの単純な実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="4e69c-413">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="4e69c-414">このサンプルは、いくつかの方法でより高度なものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-414">You can make this sample more sophisticated in several ways:</span></span>

- <span data-ttu-id="4e69c-415">デザイナーで `DemoMarqueeControl` のプロパティ値を変更します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-415">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="4e69c-416">`MarqueBorder` コントロールを追加し、親インスタンス内にドッキングして、入れ子になった効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-416">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="4e69c-417">`UpdatePeriod` とライト関連のプロパティに対して異なる設定を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="4e69c-417">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>

- <span data-ttu-id="4e69c-418">`IMarqueeWidget`の独自の実装を作成します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-418">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="4e69c-419">たとえば、点滅する "ネオンサイン" や、複数のイメージを使用したアニメーション化された記号を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-419">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>

- <span data-ttu-id="4e69c-420">デザイン時のエクスペリエンスをさらにカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="4e69c-420">Further customize the design-time experience.</span></span> <span data-ttu-id="4e69c-421"><xref:System.Windows.Forms.Control.Enabled%2A> と <xref:System.Windows.Forms.Control.Visible%2A>よりも多くのプロパティをシャドウすることができます。また、新しいプロパティを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e69c-421">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="4e69c-422">新しいデザイナー動詞を追加して、子コントロールのドッキングなどの一般的なタスクを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-422">Add new designer verbs to simplify common tasks like docking child controls.</span></span>

- <span data-ttu-id="4e69c-423">`MarqueeControl`のライセンスを付与します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-423">License the `MarqueeControl`.</span></span>

- <span data-ttu-id="4e69c-424">コントロールのシリアル化方法とコードの生成方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="4e69c-424">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="4e69c-425">詳細については、「[動的なソースコードの生成とコンパイル](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e69c-425">For more information, see [Dynamic Source Code Generation and Compilation](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e69c-426">参照</span><span class="sxs-lookup"><span data-stu-id="4e69c-426">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
