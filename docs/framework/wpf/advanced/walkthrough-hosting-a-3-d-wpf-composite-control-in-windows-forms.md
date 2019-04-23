---
title: 'チュートリアル: Windows フォームでの 3D WPF 複合コントロールのホスト'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: e5b98a33f29759a81ba1cbc1fefbd45c0e5bf736
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330169"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="15d3f-102">チュートリアル: Windows フォームでの 3D WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="15d3f-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="15d3f-103">このチュートリアルでは、作成する方法、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]複合を制御し、ホストすることで[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールとフォームを使用して、<xref:System.Windows.Forms.Integration.ElementHost>コントロール。</span><span class="sxs-lookup"><span data-stu-id="15d3f-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="15d3f-104">このチュートリアルでは、実装、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 2 つの子コントロールを格納しています。</span><span class="sxs-lookup"><span data-stu-id="15d3f-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="15d3f-105"><xref:System.Windows.Controls.UserControl> 3 次元 (3 D) の円錐形が表示されます。</span><span class="sxs-lookup"><span data-stu-id="15d3f-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="15d3f-106">3-D オブジェクトのレンダリングが容易、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]よりで[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="15d3f-107">そのため、にとってホスト、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>の 3-D グラフィックスを作成するクラス[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="15d3f-108">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="15d3f-108">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="15d3f-109">作成、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

-   <span data-ttu-id="15d3f-110">Windows フォーム ホスト プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-110">Creating the Windows Forms host project.</span></span>

-   <span data-ttu-id="15d3f-111">ホストしている、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15d3f-112">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="15d3f-112">Prerequisites</span></span>

<span data-ttu-id="15d3f-113">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="15d3f-113">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="15d3f-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="15d3f-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="15d3f-115">UserControl を作成します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-115">Create the UserControl</span></span>

1. <span data-ttu-id="15d3f-116">作成、 **WPF ユーザー コントロール ライブラリ**という名前のプロジェクト`HostingWpfUserControlInWf`します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="15d3f-117">UserControl1.xaml を開き、[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3. <span data-ttu-id="15d3f-118">生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="15d3f-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="15d3f-119">このコードを定義、 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 2 つの子コントロールを格納しています。</span><span class="sxs-lookup"><span data-stu-id="15d3f-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="15d3f-120">最初の子コントロールは、<xref:System.Windows.Controls.Label?displayProperty=nameWithType>コントロールは、2 つ目は、 <xref:System.Windows.Controls.Viewport3D> 3-D 円錐を表示するコントロール。</span><span class="sxs-lookup"><span data-stu-id="15d3f-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="15d3f-121">ホスト プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-121">Create the host project</span></span>

1. <span data-ttu-id="15d3f-122">追加、 **WPF アプリ (.NET Framework)** という名前のプロジェクト`WpfUserControlHost`をソリューションにします。</span><span class="sxs-lookup"><span data-stu-id="15d3f-122">Add a **WPF App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="15d3f-123">詳細については、「[チュートリアル:初めての WPF デスクトップ アプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-123">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="15d3f-124">**ソリューション エクスプ ローラー**、WindowsFormsIntegration.dll という WindowsFormsIntegration アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-124">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="15d3f-125">次に参照を追加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="15d3f-125">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    -   <span data-ttu-id="15d3f-126">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="15d3f-126">PresentationCore</span></span>

    -   <span data-ttu-id="15d3f-127">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="15d3f-127">PresentationFramework</span></span>

    -   <span data-ttu-id="15d3f-128">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="15d3f-128">WindowsBase</span></span>

4. <span data-ttu-id="15d3f-129">`HostingWpfUserControlInWf` への参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-129">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="15d3f-130">ソリューション エクスプローラで、設定、`WpfUserControlHost`プロジェクトをスタートアップ プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="15d3f-130">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="15d3f-131">ユーザー コントロールをホストします。</span><span class="sxs-lookup"><span data-stu-id="15d3f-131">Host the UserControl</span></span>

1. <span data-ttu-id="15d3f-132">Windows フォーム デザイナーで、Form1 を開きます。</span><span class="sxs-lookup"><span data-stu-id="15d3f-132">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="15d3f-133">[プロパティ] ウィンドウで次のようにクリックします。**イベント**、し、ダブルクリック、<xref:System.Windows.Forms.Form.Load>イベント ハンドラーを作成するイベント。</span><span class="sxs-lookup"><span data-stu-id="15d3f-133">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="15d3f-134">コード エディターが新しく生成されたに`Form1_Load`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="15d3f-134">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="15d3f-135">Form1.cs のコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="15d3f-135">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="15d3f-136">`Form1_Load`イベント ハンドラーのインスタンスを作成する`UserControl1`し、追加の接続を受け付ける、<xref:System.Windows.Forms.Integration.ElementHost>子コントロールのコントロールのコレクション。</span><span class="sxs-lookup"><span data-stu-id="15d3f-136">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="15d3f-137"><xref:System.Windows.Forms.Integration.ElementHost>コントロールの子コントロールのフォームのコレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="15d3f-137">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="15d3f-138">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="15d3f-138">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="15d3f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="15d3f-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="15d3f-140">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="15d3f-140">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="15d3f-141">チュートリアル: Windows フォームでの WPF 複合コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="15d3f-141">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="15d3f-142">チュートリアル: WPF で Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="15d3f-142">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="15d3f-143">Windows フォームのサンプルで WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="15d3f-143">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)