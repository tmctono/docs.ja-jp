---
title: WPF で Windows フォームコントロールをホストする
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 5e994f65c0665a5726c4c8c19141da5ea3f5e6f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794180"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="16feb-102">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="16feb-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="16feb-103">には、豊富な機能セットを備えたさまざまなコントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="16feb-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="16feb-104">ただし、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] のページで Windows フォームコントロールを使用することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="16feb-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="16feb-105">たとえば、既存の Windows フォームコントロールに多大な投資を行っている場合や、独自の機能を提供する Windows フォームコントロールがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="16feb-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>

<span data-ttu-id="16feb-106">このチュートリアルでは、コードを使用して [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ページで Windows フォーム <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> コントロールをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16feb-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="16feb-107">このチュートリアルで示されているタスクの完全なコード一覧については、「 [WPF の Windows フォームコントロールのホスト](https://go.microsoft.com/fwlink/?LinkID=160057)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16feb-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="16feb-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="16feb-108">Prerequisites</span></span>

<span data-ttu-id="16feb-109">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="16feb-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="16feb-110">Windows フォームコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="16feb-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="16feb-111">MaskedTextBox コントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="16feb-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="16feb-112">`HostingWfInWpf`という名前の WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="16feb-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="16feb-113">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="16feb-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="16feb-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="16feb-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="16feb-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="16feb-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="16feb-116">WPF デザイナーで Mainwindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="16feb-116">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="16feb-117"><xref:System.Windows.Controls.Grid> 要素に `grid1`という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="16feb-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="16feb-118">デザインビューまたは XAML ビューで、<xref:System.Windows.Window> 要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="16feb-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="16feb-119">プロパティウィンドウで、 **[イベント]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="16feb-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="16feb-120"><xref:System.Windows.FrameworkElement.Loaded> イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="16feb-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="16feb-121"><xref:System.Windows.FrameworkElement.Loaded> イベントを処理する次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="16feb-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="16feb-122">ファイルの先頭に、次の `Imports` または `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="16feb-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="16feb-123">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="16feb-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="16feb-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="16feb-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="16feb-125">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="16feb-125">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="16feb-126">チュートリアル: WPF での XAML を使用した Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="16feb-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="16feb-127">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="16feb-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="16feb-128">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="16feb-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="16feb-129">Windows フォーム コントロールおよび同等の WPF コントロール</span><span class="sxs-lookup"><span data-stu-id="16feb-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="16feb-130">WPF サンプルでの Windows フォームコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="16feb-130">Hosting a Windows Forms Control in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160057)
