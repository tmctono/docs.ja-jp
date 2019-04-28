---
title: 'チュートリアル: WindowsFormsHost 要素を使用したプロパティの割り当て'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: edd9d6f698ba27cacb5e9a5eecab43f58d47b8e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007125"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="a0689-102">チュートリアル: WindowsFormsHost 要素を使用したプロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="a0689-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="a0689-103">このチュートリアルは、使用する方法を示します、<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>プロパティにマップする[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、ホスト型に対応するプロパティをプロパティ[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロール。</span><span class="sxs-lookup"><span data-stu-id="a0689-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="a0689-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="a0689-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="a0689-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="a0689-105">Creating the project.</span></span>

- <span data-ttu-id="a0689-106">アプリケーションのレイアウトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0689-106">Defining the application layout.</span></span>

- <span data-ttu-id="a0689-107">新しいプロパティ マッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0689-107">Defining a new property mapping.</span></span>

- <span data-ttu-id="a0689-108">既定のプロパティ マッピングを削除しています。</span><span class="sxs-lookup"><span data-stu-id="a0689-108">Removing a default property mapping.</span></span>

- <span data-ttu-id="a0689-109">既定のプロパティ マッピングを置換します。</span><span class="sxs-lookup"><span data-stu-id="a0689-109">Replacing a default property mapping.</span></span>

- <span data-ttu-id="a0689-110">既定のプロパティ マッピングを拡張します。</span><span class="sxs-lookup"><span data-stu-id="a0689-110">Extending a default property mapping.</span></span>

<span data-ttu-id="a0689-111">このチュートリアルで示すタスクの完全なコード一覧については、次を参照してください。 [WindowsFormsHost 要素のサンプルを使用してプロパティをマッピング](https://go.microsoft.com/fwlink/?LinkID=160019)します。</span><span class="sxs-lookup"><span data-stu-id="a0689-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="a0689-112">マップが完了したらができます[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、ホスト型に対応するプロパティをプロパティ[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロール。</span><span class="sxs-lookup"><span data-stu-id="a0689-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0689-113">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a0689-113">Prerequisites</span></span>

<span data-ttu-id="a0689-114">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0689-114">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="a0689-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a0689-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="a0689-116">作成し、プロジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="a0689-116">Create and set up the project</span></span>

1. <span data-ttu-id="a0689-117">作成、 **WPF アプリ**という名前のプロジェクト`PropertyMappingWithWfhSample`します。</span><span class="sxs-lookup"><span data-stu-id="a0689-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2. <span data-ttu-id="a0689-118">**ソリューション エクスプ ローラー**、WindowsFormsIntegration.dll という WindowsFormsIntegration アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="a0689-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="a0689-119">**ソリューション エクスプ ローラー**System.Drawing、および System.Windows.Forms アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="a0689-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="a0689-120">アプリケーションのレイアウトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0689-120">Defining the Application Layout</span></span>

<span data-ttu-id="a0689-121">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-ベースのアプリケーションで使用する、<xref:System.Windows.Forms.Integration.WindowsFormsHost>ホストに要素を[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロール。</span><span class="sxs-lookup"><span data-stu-id="a0689-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="a0689-122">アプリケーションのレイアウトを定義するには</span><span class="sxs-lookup"><span data-stu-id="a0689-122">To define the application layout</span></span>

1. <span data-ttu-id="a0689-123">Window1.xaml を開き、[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a0689-123">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2. <span data-ttu-id="a0689-124">既存のコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a0689-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. <span data-ttu-id="a0689-125">Window1.xaml.cs のコード エディターでを開きます。</span><span class="sxs-lookup"><span data-stu-id="a0689-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4. <span data-ttu-id="a0689-126">ファイルの上部にある次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a0689-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="a0689-127">新しいプロパティ マッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0689-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="a0689-128"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素はいくつかの既定のプロパティのマッピングを提供します。</span><span class="sxs-lookup"><span data-stu-id="a0689-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="a0689-129">新しいプロパティの割り当てを追加するには呼び出すことによって、<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>メソッドを<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素の<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a0689-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="a0689-130">新しいプロパティ マッピングを定義するには</span><span class="sxs-lookup"><span data-stu-id="a0689-130">To define a new property mapping</span></span>

- <span data-ttu-id="a0689-131">定義に次のコードをコピー、`Window1`クラス。</span><span class="sxs-lookup"><span data-stu-id="a0689-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="a0689-132">`AddClipMapping`メソッドは、新しいマッピングを追加、<xref:System.Windows.UIElement.Clip%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a0689-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="a0689-133">`OnClipChange`メソッドは、変換、<xref:System.Windows.UIElement.Clip%2A>プロパティを[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a0689-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="a0689-134">`Window1_SizeChanged`メソッドは処理ウィンドウの<xref:System.Windows.FrameworkElement.SizeChanged>イベントと、アプリケーション ウィンドウに合わせてクリッピング領域のサイズします。</span><span class="sxs-lookup"><span data-stu-id="a0689-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="a0689-135">既定のプロパティ マッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="a0689-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="a0689-136">既定のプロパティ マッピングを削除する、<xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>メソッドを<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素の<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a0689-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="a0689-137">既定のプロパティ マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="a0689-137">To remove a default property mapping</span></span>

- <span data-ttu-id="a0689-138">定義に次のコードをコピー、`Window1`クラス。</span><span class="sxs-lookup"><span data-stu-id="a0689-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="a0689-139">`RemoveCursorMapping`メソッドの既定のマッピングを削除する、<xref:System.Windows.FrameworkElement.Cursor%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a0689-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="a0689-140">既定のプロパティ マッピングを置き換える</span><span class="sxs-lookup"><span data-stu-id="a0689-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="a0689-141">既定のマッピングと呼び出しを削除することで、既定のプロパティ マッピングを置き換える、<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>メソッドを<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素の<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a0689-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="a0689-142">既定のプロパティ マッピングを置換するには</span><span class="sxs-lookup"><span data-stu-id="a0689-142">To replace a default property mapping</span></span>

- <span data-ttu-id="a0689-143">定義に次のコードをコピー、`Window1`クラス。</span><span class="sxs-lookup"><span data-stu-id="a0689-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="a0689-144">`ReplaceFlowDirectionMapping`メソッドの既定のマッピングを置き換える、<xref:System.Windows.FrameworkElement.FlowDirection%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a0689-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="a0689-145">`OnFlowDirectionChange`メソッドは、変換、<xref:System.Windows.FrameworkElement.FlowDirection%2A>プロパティを[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a0689-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="a0689-146">`cb_CheckedChanged`メソッド ハンドル、<xref:System.Windows.Forms.CheckBox.CheckedChanged>上のイベント、<xref:System.Windows.Forms.CheckBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a0689-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="a0689-147">割り当てます、<xref:System.Windows.FrameworkElement.FlowDirection%2A>プロパティの値に基づいて、<xref:System.Windows.Forms.CheckBox.CheckState%2A>プロパティ</span><span class="sxs-lookup"><span data-stu-id="a0689-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="a0689-148">既定のプロパティ マッピングの拡張</span><span class="sxs-lookup"><span data-stu-id="a0689-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="a0689-149">既定のプロパティ マッピングを使用しても、独自のマッピングでは拡張できます。</span><span class="sxs-lookup"><span data-stu-id="a0689-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="a0689-150">既定のプロパティ マッピングを拡張するには</span><span class="sxs-lookup"><span data-stu-id="a0689-150">To extend a default property mapping</span></span>

- <span data-ttu-id="a0689-151">定義に次のコードをコピー、`Window1`クラス。</span><span class="sxs-lookup"><span data-stu-id="a0689-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="a0689-152">`ExtendBackgroundMapping`メソッドでは、カスタム プロパティ トランスレーターを追加、既存<xref:System.Windows.Controls.Control.Background%2A>プロパティ マッピングします。</span><span class="sxs-lookup"><span data-stu-id="a0689-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="a0689-153">`OnBackgroundChange`メソッドは、ホストされるコントロールに、特定のイメージを割り当てます<xref:System.Windows.Forms.Control.BackgroundImage%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a0689-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="a0689-154">`OnBackgroundChange`既定のプロパティ マッピングが適用された後、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a0689-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="a0689-155">プロパティ マッピングの初期化</span><span class="sxs-lookup"><span data-stu-id="a0689-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="a0689-156">既に説明したメソッドを呼び出すことによって、プロパティのマッピングを設定、<xref:System.Windows.FrameworkElement.Loaded>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="a0689-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="a0689-157">プロパティ マッピングを初期化するには</span><span class="sxs-lookup"><span data-stu-id="a0689-157">To initialize your property mappings</span></span>

1. <span data-ttu-id="a0689-158">定義に次のコードをコピー、`Window1`クラス。</span><span class="sxs-lookup"><span data-stu-id="a0689-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="a0689-159">`WindowLoaded`メソッド ハンドル、<xref:System.Windows.FrameworkElement.Loaded>イベントと、次の初期化を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0689-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    - <span data-ttu-id="a0689-160">作成、 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a0689-160">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>

    - <span data-ttu-id="a0689-161">プロパティ マッピングを設定するチュートリアルの前半で定義されているメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a0689-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="a0689-162">マップされたプロパティに初期値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a0689-162">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="a0689-163">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="a0689-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="a0689-164">効果を確認するチェック ボックスをクリックして、<xref:System.Windows.FrameworkElement.FlowDirection%2A>マッピングします。</span><span class="sxs-lookup"><span data-stu-id="a0689-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="a0689-165">チェック ボックスをクリックすると、レイアウトは左から右方向を反転させます。</span><span class="sxs-lookup"><span data-stu-id="a0689-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0689-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0689-166">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a0689-167">Windows フォームと WPF プロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="a0689-167">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="a0689-168">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="a0689-168">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a0689-169">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="a0689-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)