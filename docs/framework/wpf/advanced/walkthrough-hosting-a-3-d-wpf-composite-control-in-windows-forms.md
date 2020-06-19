---
title: Windows フォームで 3D WPF 複合コントロールをホストする
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: aaa726ac90fd75a12054c18be6ec08a1372c1128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794212"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="940d9-102">チュートリアル: Windows フォームで 3D WPF 複合コントロールをホストする</span><span class="sxs-lookup"><span data-stu-id="940d9-102">Walkthrough: Host a 3D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="940d9-103">このチュートリアルでは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 複合コントロールを作成し、<xref:System.Windows.Forms.Integration.ElementHost> コントロールを使用して Windows フォーム コントロールおよびフォームでホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="940d9-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in Windows Forms controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="940d9-104">このチュートリアルでは、2 つの子コントロールを含む [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> を実装します。</span><span class="sxs-lookup"><span data-stu-id="940d9-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="940d9-105"><xref:System.Windows.Controls.UserControl> を使用すると、3 次元 (3D) の円錐が表示されます。</span><span class="sxs-lookup"><span data-stu-id="940d9-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3D) cone.</span></span> <span data-ttu-id="940d9-106">3D オブジェクトのレンダリングは、Windows フォームよりも [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を使用する方がはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="940d9-106">Rendering 3D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with Windows Forms.</span></span> <span data-ttu-id="940d9-107">そのため、Windows フォームで 3D グラフィックを作成するために [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> クラスをホストすることは理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="940d9-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3D graphics in Windows Forms.</span></span>

<span data-ttu-id="940d9-108">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="940d9-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="940d9-109">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> の作成。</span><span class="sxs-lookup"><span data-stu-id="940d9-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="940d9-110">Windows フォーム ホスト プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="940d9-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="940d9-111">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> のホスト。</span><span class="sxs-lookup"><span data-stu-id="940d9-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="940d9-112">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="940d9-112">Prerequisites</span></span>

<span data-ttu-id="940d9-113">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="940d9-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="940d9-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="940d9-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="940d9-115">UserControl を作成する</span><span class="sxs-lookup"><span data-stu-id="940d9-115">Create the UserControl</span></span>

1. <span data-ttu-id="940d9-116">`HostingWpfUserControlInWf` という名前の **WPF ユーザー コントロール ライブラリ** プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="940d9-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="940d9-117">WPF デザイナーで UserControl1.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="940d9-117">Open UserControl1.xaml in the WPF Designer.</span></span>

3. <span data-ttu-id="940d9-118">生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="940d9-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="940d9-119">このコードでは、2 つの子コントロールを含む <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> を定義します。</span><span class="sxs-lookup"><span data-stu-id="940d9-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="940d9-120">1 つ目の子コントロールは <xref:System.Windows.Controls.Label?displayProperty=nameWithType> コントロールです。2 つ目は 3D の円錐を表示する <xref:System.Windows.Controls.Viewport3D> コントロールです。</span><span class="sxs-lookup"><span data-stu-id="940d9-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="940d9-121">ホスト プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="940d9-121">Create the host project</span></span>

1. <span data-ttu-id="940d9-122">**Windows フォーム アプリ (.NET Framework)** プロジェクトを `WpfUserControlHost` という名前のソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="940d9-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="940d9-123">**ソリューション エクスプローラー**で、WindowsFormsIntegration.dll という名前の WindowsFormsIntegration アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="940d9-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="940d9-124">次の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="940d9-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="940d9-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="940d9-125">PresentationCore</span></span>

    - <span data-ttu-id="940d9-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="940d9-126">PresentationFramework</span></span>

    - <span data-ttu-id="940d9-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="940d9-127">WindowsBase</span></span>

4. <span data-ttu-id="940d9-128">`HostingWpfUserControlInWf` への参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="940d9-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="940d9-129">ソリューション エクスプローラーで、`WpfUserControlHost` プロジェクトをスタートアップ プロジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="940d9-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="940d9-130">UserControl をホストする</span><span class="sxs-lookup"><span data-stu-id="940d9-130">Host the UserControl</span></span>

1. <span data-ttu-id="940d9-131">Windows フォーム デザイナーで、Form1 を開きます。</span><span class="sxs-lookup"><span data-stu-id="940d9-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="940d9-132">プロパティ ウィンドウで **[イベント]** をクリックし、<xref:System.Windows.Forms.Form.Load> イベントをダブルクリックしてイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="940d9-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="940d9-133">コード エディターが開き、新しく生成された `Form1_Load` イベント ハンドラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="940d9-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="940d9-134">Form1.cs のコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="940d9-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="940d9-135">`Form1_Load` イベント ハンドラーによって `UserControl1` のインスタンスが作成され、それが <xref:System.Windows.Forms.Integration.ElementHost> コントロールの子コントロールのコレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="940d9-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="940d9-136"><xref:System.Windows.Forms.Integration.ElementHost> コントロールがフォームの子コントロールのコレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="940d9-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="940d9-137">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="940d9-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="940d9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="940d9-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="940d9-139">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="940d9-139">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="940d9-140">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="940d9-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="940d9-141">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="940d9-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="940d9-142">Windows フォームでの WPF 複合コントロールのホストのサンプル</span><span class="sxs-lookup"><span data-stu-id="940d9-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
