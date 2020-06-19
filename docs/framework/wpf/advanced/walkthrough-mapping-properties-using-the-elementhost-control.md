---
title: 'チュートリアル: ElementHost コントロールを使用したプロパティの割り当て'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 7ff4ff607ab70b55cda1e2c4736ff773d4907a22
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794114"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="8841b-102">チュートリアル: ElementHost コントロールを使用したプロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="8841b-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="8841b-103">このチュートリアルでは、<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> プロパティを使用して、ホストされている [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 要素の対応するプロパティに Windows フォーム プロパティをマップする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8841b-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map Windows Forms properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="8841b-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="8841b-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="8841b-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="8841b-105">Creating the project.</span></span>

- <span data-ttu-id="8841b-106">新しいプロパティ マッピングの定義。</span><span class="sxs-lookup"><span data-stu-id="8841b-106">Defining a new property mapping.</span></span>

- <span data-ttu-id="8841b-107">既定のプロパティ マッピングの削除。</span><span class="sxs-lookup"><span data-stu-id="8841b-107">Removing a default property mapping.</span></span>

- <span data-ttu-id="8841b-108">既定のプロパティ マッピングの拡張。</span><span class="sxs-lookup"><span data-stu-id="8841b-108">Extending a default property mapping.</span></span>

<span data-ttu-id="8841b-109">このチュートリアルで示されているタスクの完全なコード一覧については、「[ElementHost コントロールを使用したプロパティ マッピング](https://go.microsoft.com/fwlink/?LinkID=160018)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8841b-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="8841b-110">完了すると、ホストされている要素の対応する [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] プロパティに Windows フォーム プロパティをマップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="8841b-110">When you are finished, you will be able to map Windows Forms properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8841b-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8841b-111">Prerequisites</span></span>

<span data-ttu-id="8841b-112">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="8841b-112">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="8841b-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8841b-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="8841b-114">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="8841b-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="8841b-115">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="8841b-115">To create the project</span></span>

1. <span data-ttu-id="8841b-116">`PropertyMappingWithElementHost` という名前の **Windows フォーム アプリ** プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8841b-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="8841b-117">**ソリューション エクスプローラー**で、次の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="8841b-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    - <span data-ttu-id="8841b-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="8841b-118">PresentationCore</span></span>

    - <span data-ttu-id="8841b-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="8841b-119">PresentationFramework</span></span>

    - <span data-ttu-id="8841b-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="8841b-120">WindowsBase</span></span>

    - <span data-ttu-id="8841b-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="8841b-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="8841b-122">`Form1` コード ファイルの先頭に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="8841b-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="8841b-123">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="8841b-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="8841b-124">フォームをダブルクリックして、<xref:System.Windows.Forms.Form.Load> イベントのイベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8841b-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="8841b-125">Windows フォーム デザイナーに戻り、フォームの <xref:System.Windows.Forms.Control.Resize> イベントのイベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8841b-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="8841b-126">詳細については、[方法: デザイナーを使用してイベント ハンドラーを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8841b-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="8841b-127">`Form1` クラスで <xref:System.Windows.Forms.Integration.ElementHost> フィールドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="8841b-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="8841b-128">新しいプロパティ マッピングの定義</span><span class="sxs-lookup"><span data-stu-id="8841b-128">Defining New Property Mappings</span></span>

<span data-ttu-id="8841b-129"><xref:System.Windows.Forms.Integration.ElementHost> コントロールには、いくつかの既定のプロパティ マッピングが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8841b-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="8841b-130"><xref:System.Windows.Forms.Integration.ElementHost> コントロールの <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> に対して <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> メソッドを呼び出して、新しいプロパティ マッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="8841b-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="8841b-131">新しいプロパティ マッピングを定義するには</span><span class="sxs-lookup"><span data-stu-id="8841b-131">To define new property mappings</span></span>

1. <span data-ttu-id="8841b-132">次のコードを `Form1` クラスの定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8841b-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="8841b-133">`AddMarginMapping` メソッドを使用して、<xref:System.Windows.Forms.Control.Margin%2A> プロパティの新しいマッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="8841b-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="8841b-134">`OnMarginChange` メソッドを使用して、<xref:System.Windows.Forms.Control.Margin%2A> プロパティを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> プロパティに変換します。</span><span class="sxs-lookup"><span data-stu-id="8841b-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="8841b-135">次のコードを `Form1` クラスの定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8841b-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="8841b-136">`AddRegionMapping` メソッドを使用して、<xref:System.Windows.Forms.Control.Region%2A> プロパティの新しいマッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="8841b-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="8841b-137">`OnRegionChange` メソッドを使用して、<xref:System.Windows.Forms.Control.Region%2A> プロパティを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> プロパティに変換します。</span><span class="sxs-lookup"><span data-stu-id="8841b-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="8841b-138">`Form1_Resize` メソッドを使用して、フォームの <xref:System.Windows.Forms.Control.Resize> イベントを処理し、ホストされている要素に合わせてクリッピング領域のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="8841b-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="8841b-139">既定のプロパティ マッピングの削除</span><span class="sxs-lookup"><span data-stu-id="8841b-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="8841b-140"><xref:System.Windows.Forms.Integration.ElementHost> コントロールの <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> に対して <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> メソッドを呼び出して、既定のプロパティ マッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="8841b-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="8841b-141">既定のプロパティ マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="8841b-141">To remove a default property mapping</span></span>

- <span data-ttu-id="8841b-142">次のコードを `Form1` クラスの定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8841b-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="8841b-143">`RemoveCursorMapping` メソッドを使用して、<xref:System.Windows.Forms.Control.Cursor%2A> プロパティの既定のマッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="8841b-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="8841b-144">既定のプロパティ マッピングの拡張</span><span class="sxs-lookup"><span data-stu-id="8841b-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="8841b-145">既定のプロパティ マッピングを使用できます。また、独自のマッピングを使用して拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="8841b-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="8841b-146">既定のプロパティ マッピングを拡張するには</span><span class="sxs-lookup"><span data-stu-id="8841b-146">To extend a default property mapping</span></span>

- <span data-ttu-id="8841b-147">次のコードを `Form1` クラスの定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8841b-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="8841b-148">`ExtendBackColorMapping` メソッドを使用して、カスタム プロパティ トランスレーターを既存の <xref:System.Windows.Forms.Control.BackColor%2A> プロパティ マッピングに追加します。</span><span class="sxs-lookup"><span data-stu-id="8841b-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="8841b-149">`OnBackColorChange` メソッドを使用して、ホストされているコントロールの <xref:System.Windows.Controls.Control.Background%2A> プロパティに特定の画像を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8841b-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="8841b-150">`OnBackColorChange` メソッドは、既定のプロパティ マッピングが適用された後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8841b-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="8841b-151">プロパティ マッピングを初期化する</span><span class="sxs-lookup"><span data-stu-id="8841b-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="8841b-152">次のコードを `Form1` クラスの定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8841b-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="8841b-153">`Form1_Load` メソッドを使用して <xref:System.Windows.Forms.Form.Load> イベントを処理し、次の初期化を実行します。</span><span class="sxs-lookup"><span data-stu-id="8841b-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    - <span data-ttu-id="8841b-154">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8841b-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    - <span data-ttu-id="8841b-155">このチュートリアルで前に定義したメソッドを呼び出して、プロパティ マッピングを設定します。</span><span class="sxs-lookup"><span data-stu-id="8841b-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="8841b-156">マップされたプロパティに初期値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8841b-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="8841b-157">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="8841b-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="8841b-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="8841b-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="8841b-159">Windows フォームと WPF プロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="8841b-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="8841b-160">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="8841b-160">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="8841b-161">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="8841b-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
