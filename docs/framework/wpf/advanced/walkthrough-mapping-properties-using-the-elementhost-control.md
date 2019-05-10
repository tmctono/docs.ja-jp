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
ms.openlocfilehash: 3c74878a91f89e14837b42a45a35ab35bcd5cf68
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650826"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="99ad6-102">チュートリアル: ElementHost コントロールを使用したプロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="99ad6-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="99ad6-103">このチュートリアルは、使用する方法を示します、<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>プロパティにマップする[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]、ホスト型に対応するプロパティをプロパティ[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]要素。</span><span class="sxs-lookup"><span data-stu-id="99ad6-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="99ad6-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="99ad6-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="99ad6-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="99ad6-105">Creating the project.</span></span>

- <span data-ttu-id="99ad6-106">新しいプロパティ マッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-106">Defining a new property mapping.</span></span>

- <span data-ttu-id="99ad6-107">既定のプロパティ マッピングを削除しています。</span><span class="sxs-lookup"><span data-stu-id="99ad6-107">Removing a default property mapping.</span></span>

- <span data-ttu-id="99ad6-108">既定のプロパティ マッピングを拡張します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-108">Extending a default property mapping.</span></span>

<span data-ttu-id="99ad6-109">このチュートリアルで示すタスクの完全なコード一覧については、次を参照してください。 [ElementHost コントロールのサンプルを使用してプロパティをマッピング](https://go.microsoft.com/fwlink/?LinkID=160018)します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="99ad6-110">マップが完了したらができます[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]を対応するプロパティ[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ホストされている要素のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="99ad6-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99ad6-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="99ad6-111">Prerequisites</span></span>

<span data-ttu-id="99ad6-112">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="99ad6-112">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="99ad6-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="99ad6-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="99ad6-114">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="99ad6-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="99ad6-115">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="99ad6-115">To create the project</span></span>

1. <span data-ttu-id="99ad6-116">作成、 **Windows フォーム アプリ**という名前のプロジェクト`PropertyMappingWithElementHost`します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="99ad6-117">**ソリューション エクスプ ローラー**、次の参照を追加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="99ad6-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    - <span data-ttu-id="99ad6-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="99ad6-118">PresentationCore</span></span>

    - <span data-ttu-id="99ad6-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="99ad6-119">PresentationFramework</span></span>

    - <span data-ttu-id="99ad6-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="99ad6-120">WindowsBase</span></span>

    - <span data-ttu-id="99ad6-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="99ad6-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="99ad6-122">先頭に次のコードをコピー、`Form1`コード ファイル。</span><span class="sxs-lookup"><span data-stu-id="99ad6-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="99ad6-123">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="99ad6-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="99ad6-124">イベント ハンドラーを追加するためのフォームをダブルクリックして、<xref:System.Windows.Forms.Form.Load>イベント。</span><span class="sxs-lookup"><span data-stu-id="99ad6-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="99ad6-125">Windows フォーム デザイナーに戻るし、フォームのイベント ハンドラーを追加<xref:System.Windows.Forms.Control.Resize>イベント。</span><span class="sxs-lookup"><span data-stu-id="99ad6-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="99ad6-126">詳細については、「[方法 :デザイナーを使用してイベント ハンドラーを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="99ad6-127">宣言、<xref:System.Windows.Forms.Integration.ElementHost>フィールドに、`Form1`クラス。</span><span class="sxs-lookup"><span data-stu-id="99ad6-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="99ad6-128">新しいプロパティのマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-128">Defining New Property Mappings</span></span>

<span data-ttu-id="99ad6-129"><xref:System.Windows.Forms.Integration.ElementHost>コントロールはいくつかの既定のプロパティのマッピングを提供します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="99ad6-130">新しいプロパティの割り当てを追加するには呼び出すことによって、<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>メソッドを<xref:System.Windows.Forms.Integration.ElementHost>コントロールの<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="99ad6-131">新しいプロパティのマッピングを定義するには</span><span class="sxs-lookup"><span data-stu-id="99ad6-131">To define new property mappings</span></span>

1. <span data-ttu-id="99ad6-132">定義に次のコードをコピー、`Form1`クラス。</span><span class="sxs-lookup"><span data-stu-id="99ad6-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="99ad6-133">`AddMarginMapping`メソッドは、新しいマッピングを追加、<xref:System.Windows.Forms.Control.Margin%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="99ad6-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="99ad6-134">`OnMarginChange`メソッドは、変換、<xref:System.Windows.Forms.Control.Margin%2A>プロパティを[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.FrameworkElement.Margin%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="99ad6-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="99ad6-135">定義に次のコードをコピー、`Form1`クラス。</span><span class="sxs-lookup"><span data-stu-id="99ad6-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="99ad6-136">`AddRegionMapping`メソッドは、新しいマッピングを追加、<xref:System.Windows.Forms.Control.Region%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="99ad6-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="99ad6-137">`OnRegionChange`メソッドは、変換、<xref:System.Windows.Forms.Control.Region%2A>プロパティを[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.UIElement.Clip%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="99ad6-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="99ad6-138">`Form1_Resize`メソッドの処理、フォームの<xref:System.Windows.Forms.Control.Resize>イベントと、ホストされている要素に合わせてクリッピング領域のサイズします。</span><span class="sxs-lookup"><span data-stu-id="99ad6-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="99ad6-139">既定のプロパティ マッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="99ad6-140">既定のプロパティ マッピングを削除する、<xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>メソッドを<xref:System.Windows.Forms.Integration.ElementHost>コントロールの<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="99ad6-141">既定のプロパティ マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="99ad6-141">To remove a default property mapping</span></span>

- <span data-ttu-id="99ad6-142">定義に次のコードをコピー、`Form1`クラス。</span><span class="sxs-lookup"><span data-stu-id="99ad6-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="99ad6-143">`RemoveCursorMapping`メソッドの既定のマッピングを削除する、<xref:System.Windows.Forms.Control.Cursor%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="99ad6-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="99ad6-144">既定のプロパティ マッピングの拡張</span><span class="sxs-lookup"><span data-stu-id="99ad6-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="99ad6-145">既定のプロパティ マッピングを使用しても、独自のマッピングでは拡張できます。</span><span class="sxs-lookup"><span data-stu-id="99ad6-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="99ad6-146">既定のプロパティ マッピングを拡張するには</span><span class="sxs-lookup"><span data-stu-id="99ad6-146">To extend a default property mapping</span></span>

- <span data-ttu-id="99ad6-147">定義に次のコードをコピー、`Form1`クラス。</span><span class="sxs-lookup"><span data-stu-id="99ad6-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="99ad6-148">`ExtendBackColorMapping`メソッドでは、カスタム プロパティ トランスレーターを追加、既存<xref:System.Windows.Forms.Control.BackColor%2A>プロパティ マッピングします。</span><span class="sxs-lookup"><span data-stu-id="99ad6-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="99ad6-149">`OnBackColorChange`メソッドは、ホストされるコントロールに、特定のイメージを割り当てます<xref:System.Windows.Controls.Control.Background%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="99ad6-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="99ad6-150">`OnBackColorChange`既定のプロパティ マッピングが適用された後、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="99ad6-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="99ad6-151">プロパティ マッピングを初期化します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="99ad6-152">定義に次のコードをコピー、`Form1`クラス。</span><span class="sxs-lookup"><span data-stu-id="99ad6-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="99ad6-153">`Form1_Load`メソッド ハンドル、<xref:System.Windows.Forms.Form.Load>イベントと、次の初期化を実行します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    - <span data-ttu-id="99ad6-154">作成、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button>要素。</span><span class="sxs-lookup"><span data-stu-id="99ad6-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    - <span data-ttu-id="99ad6-155">プロパティ マッピングを設定するチュートリアルの前半で定義されているメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="99ad6-156">マップされたプロパティに初期値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="99ad6-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="99ad6-157">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="99ad6-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="99ad6-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="99ad6-159">Windows フォームと WPF プロパティの割り当て</span><span class="sxs-lookup"><span data-stu-id="99ad6-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="99ad6-160">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="99ad6-160">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="99ad6-161">チュートリアル: Windows フォームでの WPF 複合コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="99ad6-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)