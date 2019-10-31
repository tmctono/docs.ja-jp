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
ms.openlocfilehash: 748ab027fa8206c163578c89b94460665563cbce
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197869"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="3312a-102">チュートリアル: Windows フォームでの 3D WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="3312a-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="3312a-103">このチュートリアルでは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 複合コントロールを作成し、<xref:System.Windows.Forms.Integration.ElementHost> コントロールを使用して [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] コントロールとフォームでホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3312a-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="3312a-104">このチュートリアルでは、2つの子コントロールを含む [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> を実装します。</span><span class="sxs-lookup"><span data-stu-id="3312a-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="3312a-105"><xref:System.Windows.Controls.UserControl> には、3次元 (3-d) の円錐が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3312a-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="3312a-106">3d オブジェクトのレンダリングは、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]よりも [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ではるかに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="3312a-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="3312a-107">したがって、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]に3-d グラフィックスを作成するには、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> クラスをホストするのが理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="3312a-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="3312a-108">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="3312a-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="3312a-109">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>を作成しています。</span><span class="sxs-lookup"><span data-stu-id="3312a-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="3312a-110">Windows フォームホストプロジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="3312a-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="3312a-111">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>をホストしています。</span><span class="sxs-lookup"><span data-stu-id="3312a-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3312a-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="3312a-112">Prerequisites</span></span>

<span data-ttu-id="3312a-113">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="3312a-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="3312a-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="3312a-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="3312a-115">UserControl を作成する</span><span class="sxs-lookup"><span data-stu-id="3312a-115">Create the UserControl</span></span>

1. <span data-ttu-id="3312a-116">`HostingWpfUserControlInWf`という名前の**WPF ユーザーコントロールライブラリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3312a-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="3312a-117">[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]で UserControl1 を開きます。</span><span class="sxs-lookup"><span data-stu-id="3312a-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3. <span data-ttu-id="3312a-118">生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3312a-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="3312a-119">このコードは、2つの子コントロールを含む <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> を定義します。</span><span class="sxs-lookup"><span data-stu-id="3312a-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="3312a-120">最初の子コントロールは <xref:System.Windows.Controls.Label?displayProperty=nameWithType> コントロールです。2つ目は、3-d 円錐を表示する <xref:System.Windows.Controls.Viewport3D> コントロールです。</span><span class="sxs-lookup"><span data-stu-id="3312a-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="3312a-121">ホストプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="3312a-121">Create the host project</span></span>

1. <span data-ttu-id="3312a-122">`WpfUserControlHost` という名前の**Windows フォーム App (.NET Framework)** プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="3312a-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="3312a-123">**ソリューションエクスプローラー**で、windowsフォーム統合アセンブリへの参照を追加します。このアセンブリには、windowsフォーム integration .dll という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="3312a-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="3312a-124">次の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="3312a-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="3312a-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="3312a-125">PresentationCore</span></span>

    - <span data-ttu-id="3312a-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="3312a-126">PresentationFramework</span></span>

    - <span data-ttu-id="3312a-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="3312a-127">WindowsBase</span></span>

4. <span data-ttu-id="3312a-128">`HostingWpfUserControlInWf` への参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="3312a-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="3312a-129">ソリューションエクスプローラーで、`WpfUserControlHost` プロジェクトをスタートアッププロジェクトとして設定します。</span><span class="sxs-lookup"><span data-stu-id="3312a-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="3312a-130">UserControl をホストする</span><span class="sxs-lookup"><span data-stu-id="3312a-130">Host the UserControl</span></span>

1. <span data-ttu-id="3312a-131">Windows フォームデザイナーで、Form1 を開きます。</span><span class="sxs-lookup"><span data-stu-id="3312a-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="3312a-132">プロパティウィンドウで、 **[イベント]** をクリックし、<xref:System.Windows.Forms.Form.Load> イベントをダブルクリックしてイベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3312a-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="3312a-133">コードエディターが開き、新しく生成された `Form1_Load` イベントハンドラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3312a-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="3312a-134">Form1.cs のコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3312a-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="3312a-135">`Form1_Load` イベントハンドラーは、`UserControl1` のインスタンスを作成し、それを <xref:System.Windows.Forms.Integration.ElementHost> コントロールの子コントロールのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="3312a-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="3312a-136"><xref:System.Windows.Forms.Integration.ElementHost> コントロールが、フォームの子コントロールのコレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3312a-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="3312a-137">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="3312a-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="3312a-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="3312a-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="3312a-139">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="3312a-139">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="3312a-140">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="3312a-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="3312a-141">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="3312a-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="3312a-142">Windows フォームサンプルでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="3312a-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
