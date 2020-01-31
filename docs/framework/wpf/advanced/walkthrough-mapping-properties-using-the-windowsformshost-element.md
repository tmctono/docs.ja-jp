---
title: 'チュートリアル : WindowsFormsHost 要素を使用したプロパティの割り当て'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: c076937d6431adf1750793d47ece88dc82edf95c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794100"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="ea264-102">チュートリアル : WindowsFormsHost 要素を使用したプロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="ea264-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="ea264-103">このチュートリアルでは、<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> プロパティを使用して、ホストされている Windows フォームコントロールの対応するプロパティに [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] プロパティをマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea264-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted Windows Forms control.</span></span>

<span data-ttu-id="ea264-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="ea264-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="ea264-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="ea264-105">Creating the project.</span></span>

- <span data-ttu-id="ea264-106">アプリケーションレイアウトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea264-106">Defining the application layout.</span></span>

- <span data-ttu-id="ea264-107">新しいプロパティマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea264-107">Defining a new property mapping.</span></span>

- <span data-ttu-id="ea264-108">既定のプロパティマッピングを削除しています。</span><span class="sxs-lookup"><span data-stu-id="ea264-108">Removing a default property mapping.</span></span>

- <span data-ttu-id="ea264-109">既定のプロパティマッピングを置き換える。</span><span class="sxs-lookup"><span data-stu-id="ea264-109">Replacing a default property mapping.</span></span>

- <span data-ttu-id="ea264-110">既定のプロパティマッピングの拡張。</span><span class="sxs-lookup"><span data-stu-id="ea264-110">Extending a default property mapping.</span></span>

<span data-ttu-id="ea264-111">このチュートリアルで示すタスクの完全なコード一覧については、「 [WindowsFormsHost 要素のサンプルを使用したプロパティのマッピング](https://go.microsoft.com/fwlink/?LinkID=160019)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea264-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="ea264-112">終了すると、ホストされている Windows フォームコントロールの対応するプロパティに [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] プロパティをマップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ea264-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted Windows Forms control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea264-113">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="ea264-113">Prerequisites</span></span>

<span data-ttu-id="ea264-114">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea264-114">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="ea264-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ea264-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="ea264-116">プロジェクトを作成して設定する</span><span class="sxs-lookup"><span data-stu-id="ea264-116">Create and set up the project</span></span>

1. <span data-ttu-id="ea264-117">`PropertyMappingWithWfhSample`という名前の**WPF アプリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea264-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2. <span data-ttu-id="ea264-118">**ソリューションエクスプローラー**で、windowsフォーム統合アセンブリへの参照を追加します。このアセンブリには、windowsフォーム integration .dll という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="ea264-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="ea264-119">**ソリューションエクスプローラー**で、Drawing アセンブリおよび system.string アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="ea264-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="ea264-120">アプリケーションレイアウトの定義</span><span class="sxs-lookup"><span data-stu-id="ea264-120">Defining the Application Layout</span></span>

<span data-ttu-id="ea264-121">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ベースのアプリケーションでは、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を使用して Windows フォームコントロールをホストします。</span><span class="sxs-lookup"><span data-stu-id="ea264-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a Windows Forms control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="ea264-122">アプリケーションのレイアウトを定義するには</span><span class="sxs-lookup"><span data-stu-id="ea264-122">To define the application layout</span></span>

1. <span data-ttu-id="ea264-123">WPF デザイナーで Window1.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="ea264-123">Open Window1.xaml in the WPF Designer.</span></span>

2. <span data-ttu-id="ea264-124">既存のコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ea264-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. <span data-ttu-id="ea264-125">コードエディターで Window1.xaml.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="ea264-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4. <span data-ttu-id="ea264-126">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ea264-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="ea264-127">新しいプロパティマッピングの定義</span><span class="sxs-lookup"><span data-stu-id="ea264-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="ea264-128"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素には、いくつかの既定のプロパティマッピングが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea264-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="ea264-129">新しいプロパティマッピングを追加するには、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>の <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ea264-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="ea264-130">新しいプロパティマッピングを定義するには</span><span class="sxs-lookup"><span data-stu-id="ea264-130">To define a new property mapping</span></span>

- <span data-ttu-id="ea264-131">`Window1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ea264-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="ea264-132">`AddClipMapping` メソッドは、<xref:System.Windows.UIElement.Clip%2A> プロパティの新しいマッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="ea264-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="ea264-133">`OnClipChange` メソッドは、<xref:System.Windows.UIElement.Clip%2A> プロパティを Windows フォーム<xref:System.Windows.Forms.Control.Region%2A> プロパティに変換します。</span><span class="sxs-lookup"><span data-stu-id="ea264-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the Windows Forms<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="ea264-134">`Window1_SizeChanged` メソッドは、ウィンドウの <xref:System.Windows.FrameworkElement.SizeChanged> イベントを処理し、アプリケーションウィンドウに合うようにクリッピング領域のサイズを調整します。</span><span class="sxs-lookup"><span data-stu-id="ea264-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="ea264-135">既定のプロパティマッピングの削除</span><span class="sxs-lookup"><span data-stu-id="ea264-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="ea264-136"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>の <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> メソッドを呼び出すことによって、既定のプロパティマッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="ea264-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="ea264-137">既定のプロパティマッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="ea264-137">To remove a default property mapping</span></span>

- <span data-ttu-id="ea264-138">`Window1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ea264-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="ea264-139">`RemoveCursorMapping` メソッドは、<xref:System.Windows.FrameworkElement.Cursor%2A> プロパティの既定のマッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="ea264-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="ea264-140">既定のプロパティマッピングの置換</span><span class="sxs-lookup"><span data-stu-id="ea264-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="ea264-141">既定のマッピングを削除し、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>に対して <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> メソッドを呼び出すことによって、既定のプロパティマッピングを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ea264-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="ea264-142">既定のプロパティマッピングを置き換えるには</span><span class="sxs-lookup"><span data-stu-id="ea264-142">To replace a default property mapping</span></span>

- <span data-ttu-id="ea264-143">`Window1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ea264-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="ea264-144">`ReplaceFlowDirectionMapping` メソッドは、<xref:System.Windows.FrameworkElement.FlowDirection%2A> プロパティの既定のマッピングを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ea264-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="ea264-145">`OnFlowDirectionChange` メソッドは、<xref:System.Windows.FrameworkElement.FlowDirection%2A> プロパティを Windows フォーム<xref:System.Windows.Forms.Control.RightToLeft%2A> プロパティに変換します。</span><span class="sxs-lookup"><span data-stu-id="ea264-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the Windows Forms<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="ea264-146">`cb_CheckedChanged` メソッドは、<xref:System.Windows.Forms.CheckBox> コントロールの <xref:System.Windows.Forms.CheckBox.CheckedChanged> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="ea264-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="ea264-147"><xref:System.Windows.Forms.CheckBox.CheckState%2A> プロパティの値に基づいて <xref:System.Windows.FrameworkElement.FlowDirection%2A> プロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ea264-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="ea264-148">既定のプロパティマッピングの拡張</span><span class="sxs-lookup"><span data-stu-id="ea264-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="ea264-149">既定のプロパティマッピングを使用し、独自のマッピングで拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea264-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="ea264-150">既定のプロパティマッピングを拡張するには</span><span class="sxs-lookup"><span data-stu-id="ea264-150">To extend a default property mapping</span></span>

- <span data-ttu-id="ea264-151">`Window1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ea264-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="ea264-152">`ExtendBackgroundMapping` メソッドは、既存の <xref:System.Windows.Controls.Control.Background%2A> プロパティのマッピングにカスタムプロパティトランスレーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="ea264-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="ea264-153">`OnBackgroundChange` メソッドは、ホストされているコントロールの <xref:System.Windows.Forms.Control.BackgroundImage%2A> プロパティに特定のイメージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ea264-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="ea264-154">`OnBackgroundChange` メソッドは、既定のプロパティマッピングが適用された後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ea264-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="ea264-155">プロパティマッピングの初期化</span><span class="sxs-lookup"><span data-stu-id="ea264-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="ea264-156"><xref:System.Windows.FrameworkElement.Loaded> イベントハンドラーで前に説明したメソッドを呼び出すことによって、プロパティマッピングを設定します。</span><span class="sxs-lookup"><span data-stu-id="ea264-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="ea264-157">プロパティマッピングを初期化するには</span><span class="sxs-lookup"><span data-stu-id="ea264-157">To initialize your property mappings</span></span>

1. <span data-ttu-id="ea264-158">`Window1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ea264-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="ea264-159">`WindowLoaded` メソッドは、<xref:System.Windows.FrameworkElement.Loaded> イベントを処理し、次の初期化を実行します。</span><span class="sxs-lookup"><span data-stu-id="ea264-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    - <span data-ttu-id="ea264-160"><xref:System.Windows.Forms.CheckBox> コントロール Windows フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea264-160">Creates a Windows Forms<xref:System.Windows.Forms.CheckBox> control.</span></span>

    - <span data-ttu-id="ea264-161">チュートリアルの前の手順で定義したメソッドを呼び出して、プロパティマッピングを設定します。</span><span class="sxs-lookup"><span data-stu-id="ea264-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="ea264-162">マップされたプロパティに初期値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ea264-162">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="ea264-163">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="ea264-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="ea264-164"><xref:System.Windows.FrameworkElement.FlowDirection%2A> マッピングの効果を確認するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ea264-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="ea264-165">このチェックボックスをオンにすると、レイアウトが左から右方向に反転します。</span><span class="sxs-lookup"><span data-stu-id="ea264-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea264-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea264-166">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ea264-167">Windows フォームと WPF プロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="ea264-167">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="ea264-168">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="ea264-168">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="ea264-169">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="ea264-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
