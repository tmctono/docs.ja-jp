---
title: 'チュートリアル : ElementHost コントロールを使用したプロパティの割り当て'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 7d1cf353f7e6c4b87c13598e7e6029960cd0f715
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197815"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="9cb1a-102">チュートリアル : ElementHost コントロールを使用したプロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="9cb1a-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="9cb1a-103">このチュートリアルでは、<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> プロパティを使用して、ホストされる [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 要素の対応するプロパティに [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] プロパティをマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="9cb1a-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="9cb1a-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-105">Creating the project.</span></span>

- <span data-ttu-id="9cb1a-106">新しいプロパティマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-106">Defining a new property mapping.</span></span>

- <span data-ttu-id="9cb1a-107">既定のプロパティマッピングを削除しています。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-107">Removing a default property mapping.</span></span>

- <span data-ttu-id="9cb1a-108">既定のプロパティマッピングの拡張。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-108">Extending a default property mapping.</span></span>

<span data-ttu-id="9cb1a-109">このチュートリアルで説明されているタスクの完全なコード一覧については、「[コントロールのプロパティを使用したプロパティのマッピング](https://go.microsoft.com/fwlink/?LinkID=160018)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="9cb1a-110">終了すると、ホストされている要素の対応する [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] プロパティに [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] プロパティをマップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9cb1a-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9cb1a-111">Prerequisites</span></span>

<span data-ttu-id="9cb1a-112">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-112">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="9cb1a-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="9cb1a-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="9cb1a-114">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="9cb1a-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="9cb1a-115">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="9cb1a-115">To create the project</span></span>

1. <span data-ttu-id="9cb1a-116">`PropertyMappingWithElementHost`という名前の**Windows フォームアプリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="9cb1a-117">**ソリューションエクスプローラー**で、次の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    - <span data-ttu-id="9cb1a-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="9cb1a-118">PresentationCore</span></span>

    - <span data-ttu-id="9cb1a-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="9cb1a-119">PresentationFramework</span></span>

    - <span data-ttu-id="9cb1a-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="9cb1a-120">WindowsBase</span></span>

    - <span data-ttu-id="9cb1a-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="9cb1a-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="9cb1a-122">`Form1` コードファイルの先頭に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="9cb1a-123">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="9cb1a-124">フォームをダブルクリックして、<xref:System.Windows.Forms.Form.Load> イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="9cb1a-125">Windows フォームデザイナーに戻り、フォームの <xref:System.Windows.Forms.Control.Resize> イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="9cb1a-126">詳細については、「[方法: デザイナーを使用してイベントハンドラーを作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="9cb1a-127">`Form1` クラスの <xref:System.Windows.Forms.Integration.ElementHost> フィールドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="9cb1a-128">新しいプロパティマッピングの定義</span><span class="sxs-lookup"><span data-stu-id="9cb1a-128">Defining New Property Mappings</span></span>

<span data-ttu-id="9cb1a-129"><xref:System.Windows.Forms.Integration.ElementHost> コントロールには、いくつかの既定のプロパティマッピングが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="9cb1a-130">新しいプロパティマッピングを追加するには、<xref:System.Windows.Forms.Integration.ElementHost> コントロールの <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>の <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="9cb1a-131">新しいプロパティマッピングを定義するには</span><span class="sxs-lookup"><span data-stu-id="9cb1a-131">To define new property mappings</span></span>

1. <span data-ttu-id="9cb1a-132">`Form1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="9cb1a-133">`AddMarginMapping` メソッドは、<xref:System.Windows.Forms.Control.Margin%2A> プロパティの新しいマッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="9cb1a-134">`OnMarginChange` メソッドは、<xref:System.Windows.Forms.Control.Margin%2A> プロパティを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> プロパティに変換します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="9cb1a-135">`Form1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="9cb1a-136">`AddRegionMapping` メソッドは、<xref:System.Windows.Forms.Control.Region%2A> プロパティの新しいマッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="9cb1a-137">`OnRegionChange` メソッドは、<xref:System.Windows.Forms.Control.Region%2A> プロパティを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> プロパティに変換します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="9cb1a-138">`Form1_Resize` メソッドは、フォームの <xref:System.Windows.Forms.Control.Resize> イベントを処理し、ホストされている要素に合うようにクリッピング領域のサイズを調整します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="9cb1a-139">既定のプロパティマッピングの削除</span><span class="sxs-lookup"><span data-stu-id="9cb1a-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="9cb1a-140"><xref:System.Windows.Forms.Integration.ElementHost> コントロールの <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>の <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> メソッドを呼び出すことによって、既定のプロパティマッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="9cb1a-141">既定のプロパティマッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="9cb1a-141">To remove a default property mapping</span></span>

- <span data-ttu-id="9cb1a-142">`Form1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="9cb1a-143">`RemoveCursorMapping` メソッドは、<xref:System.Windows.Forms.Control.Cursor%2A> プロパティの既定のマッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="9cb1a-144">既定のプロパティマッピングの拡張</span><span class="sxs-lookup"><span data-stu-id="9cb1a-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="9cb1a-145">既定のプロパティマッピングを使用し、独自のマッピングで拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="9cb1a-146">既定のプロパティマッピングを拡張するには</span><span class="sxs-lookup"><span data-stu-id="9cb1a-146">To extend a default property mapping</span></span>

- <span data-ttu-id="9cb1a-147">`Form1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="9cb1a-148">`ExtendBackColorMapping` メソッドは、既存の <xref:System.Windows.Forms.Control.BackColor%2A> プロパティのマッピングにカスタムプロパティトランスレーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="9cb1a-149">`OnBackColorChange` メソッドは、ホストされているコントロールの <xref:System.Windows.Controls.Control.Background%2A> プロパティに特定のイメージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="9cb1a-150">`OnBackColorChange` メソッドは、既定のプロパティマッピングが適用された後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="9cb1a-151">プロパティマッピングの初期化</span><span class="sxs-lookup"><span data-stu-id="9cb1a-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="9cb1a-152">`Form1` クラスの定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="9cb1a-153">`Form1_Load` メソッドは、<xref:System.Windows.Forms.Form.Load> イベントを処理し、次の初期化を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    - <span data-ttu-id="9cb1a-154"><xref:System.Windows.Controls.Button> 要素 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を作成します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    - <span data-ttu-id="9cb1a-155">チュートリアルの前の手順で定義したメソッドを呼び出して、プロパティマッピングを設定します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="9cb1a-156">マップされたプロパティに初期値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="9cb1a-157">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb1a-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cb1a-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cb1a-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="9cb1a-159">Windows フォームと WPF プロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="9cb1a-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="9cb1a-160">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="9cb1a-160">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="9cb1a-161">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="9cb1a-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
