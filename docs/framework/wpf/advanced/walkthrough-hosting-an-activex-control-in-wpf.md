---
title: 'チュートリアル: WPF での ActiveX コントロールのホスト'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 8679181d720d9550cf60034a7cf1809b79198e83
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197892"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="b3f45-102">チュートリアル: WPF での ActiveX コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="b3f45-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="b3f45-103">ブラウザーとの対話を強化するために、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ベースのアプリケーションで Microsoft ActiveX コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3f45-103">To enable improved interaction with browsers, you can use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="b3f45-104">このチュートリアルでは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ページのコントロールとして Microsoft Windows Media Player をホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-104">This walkthrough demonstrates how you can host the Microsoft Windows Media Player as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="b3f45-105">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="b3f45-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="b3f45-106">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="b3f45-106">Creating the project.</span></span>

- <span data-ttu-id="b3f45-107">ActiveX コントロールを作成しています。</span><span class="sxs-lookup"><span data-stu-id="b3f45-107">Creating the ActiveX control.</span></span>

- <span data-ttu-id="b3f45-108">WPF ページで ActiveX コントロールをホストする。</span><span class="sxs-lookup"><span data-stu-id="b3f45-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="b3f45-109">このチュートリアルを完了すると、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ベースのアプリケーションで Microsoft ActiveX コントロールを使用する方法を理解できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b3f45-109">When you have completed this walkthrough, you will understand how to use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3f45-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b3f45-110">Prerequisites</span></span>
 <span data-ttu-id="b3f45-111">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b3f45-111">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="b3f45-112">Microsoft Windows Media Player、Visual Studio がインストールされているコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b3f45-112">Microsoft Windows Media Player installed on the computer where Visual Studio is installed.</span></span>

- <span data-ttu-id="b3f45-113">Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="b3f45-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="b3f45-114">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="b3f45-114">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="b3f45-115">プロジェクトを作成し、設定するには</span><span class="sxs-lookup"><span data-stu-id="b3f45-115">To create and set up the project</span></span>

1. <span data-ttu-id="b3f45-116">`HostingAxInWpf`という名前の WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="b3f45-117">ソリューションに Windows フォームコントロールライブラリプロジェクトを追加し、プロジェクトに `WmpAxLib`という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="b3f45-118">WmpAxLib プロジェクトで、Windows Media Player アセンブリへの参照を追加します。このアセンブリには、wmp という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="b3f45-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="b3f45-119">**ツールボックス**を開きます。</span><span class="sxs-lookup"><span data-stu-id="b3f45-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="b3f45-120">**ツールボックス**内を右クリックし、 **[項目の選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f45-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="b3f45-121">**[COM コンポーネント]** タブをクリックし、 **[Windows Media Player]** コントロールを選択して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f45-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="b3f45-122">Windows Media Player コントロールが **[ツールボックス]** に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b3f45-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="b3f45-123">ソリューションエクスプローラーで、 **UserControl1**ファイルを右クリックし、[名前の**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f45-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="b3f45-124">言語に応じて、名前を `WmpAxControl.vb` または `WmpAxControl.cs`に変更します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="b3f45-125">すべての参照の名前を変更するように求めるメッセージが表示されたら、 **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f45-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="b3f45-126">ActiveX コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="b3f45-126">Creating the ActiveX Control</span></span>
<span data-ttu-id="b3f45-127">コントロールがデザインサーフェイスに追加されると、Visual Studio は Microsoft ActiveX コントロールの <xref:System.Windows.Forms.AxHost> ラッパークラスを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-127">Visual Studio automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a Microsoft ActiveX control when the control is added to a design surface.</span></span> <span data-ttu-id="b3f45-128">次の手順では、WMPLib という名前のマネージアセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

### <a name="to-create-the-activex-control"></a><span data-ttu-id="b3f45-129">ActiveX コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="b3f45-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="b3f45-130">Windows フォームデザイナーで WmpAxControl .vb または WmpAxControl.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="b3f45-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="b3f45-131">**[ツールボックス]** から、Windows Media Player コントロールをデザイン画面に追加します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="b3f45-132">プロパティウィンドウで、Windows Media Player コントロールの <xref:System.Windows.Forms.Control.Dock%2A> プロパティの値を <xref:System.Windows.Forms.DockStyle.Fill>に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="b3f45-133">WmpAxLib コントロールライブラリプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="b3f45-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="b3f45-134">WPF ページで ActiveX コントロールをホストする</span><span class="sxs-lookup"><span data-stu-id="b3f45-134">Hosting the ActiveX Control on a WPF Page</span></span>

### <a name="to-host-the-activex-control"></a><span data-ttu-id="b3f45-135">ActiveX コントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="b3f45-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="b3f45-136">HostingAxInWpf プロジェクトで、生成された ActiveX 相互運用性アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-136">In the HostingAxInWpf project, add a reference to the generated ActiveX interoperability assembly.</span></span>

     <span data-ttu-id="b3f45-137">このアセンブリは WMPLib という名前で、Windows Media Player コントロールをインポートしたときに、WmpAxLib プロジェクトの Debug フォルダーに追加されました。</span><span class="sxs-lookup"><span data-stu-id="b3f45-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="b3f45-138">Windowsフォーム統合アセンブリへの参照を追加します。このアセンブリには、Windowsフォーム統合 dll という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="b3f45-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="b3f45-139">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] アセンブリへの参照を追加します。このアセンブリには、「system.string」という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="b3f45-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="b3f45-140">WPF デザイナーで Mainwindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="b3f45-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="b3f45-141"><xref:System.Windows.Controls.Grid> 要素に `grid1`という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="b3f45-142">デザインビューまたは XAML ビューで、<xref:System.Windows.Window> 要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="b3f45-143">プロパティウィンドウで、 **[イベント]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f45-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="b3f45-144"><xref:System.Windows.FrameworkElement.Loaded> イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f45-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="b3f45-145"><xref:System.Windows.FrameworkElement.Loaded> イベントを処理する次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="b3f45-146">このコードでは、<xref:System.Windows.Forms.Integration.WindowsFormsHost> コントロールのインスタンスを作成し、その子として `AxWindowsMediaPlayer` コントロールのインスタンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="b3f45-147">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="b3f45-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f45-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3f45-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="b3f45-149">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="b3f45-149">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="b3f45-150">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="b3f45-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="b3f45-151">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="b3f45-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
