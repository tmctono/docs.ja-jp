---
title: 'チュートリアル: WPF での Windows フォーム コントロールのホスト'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: af5a0d58e789e609a25aa828493a3b0722cc83e1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605477"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="cf05a-102">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="cf05a-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="cf05a-103">豊富な機能セットには、多くのコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf05a-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="cf05a-104">ただしを使用する可能性がありますも[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]のコントロールに対して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ページ。</span><span class="sxs-lookup"><span data-stu-id="cf05a-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="cf05a-105">たとえば、既存のかなりの投資を必要に応じて[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロール、またはする必要があります、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]独自の機能を提供するコントロール。</span><span class="sxs-lookup"><span data-stu-id="cf05a-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>

<span data-ttu-id="cf05a-106">このチュートリアルは、ホストする方法を示します、 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>の control 権限、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コードを使用してページ。</span><span class="sxs-lookup"><span data-stu-id="cf05a-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="cf05a-107">このチュートリアルで示すタスクの完全なコード一覧については、次を参照してください。 [WPF のサンプルでの Windows フォーム コントロールをホストしている](https://go.microsoft.com/fwlink/?LinkID=160057)します。</span><span class="sxs-lookup"><span data-stu-id="cf05a-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cf05a-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cf05a-108">Prerequisites</span></span>

<span data-ttu-id="cf05a-109">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="cf05a-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="cf05a-110">Windows フォームのコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="cf05a-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="cf05a-111">MaskedTextBox コントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="cf05a-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="cf05a-112">という名前の WPF アプリケーション プロジェクトを作成する`HostingWfInWpf`します。</span><span class="sxs-lookup"><span data-stu-id="cf05a-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="cf05a-113">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="cf05a-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="cf05a-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="cf05a-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="cf05a-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="cf05a-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="cf05a-116">MainWindow.xaml を開き、[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cf05a-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

4. <span data-ttu-id="cf05a-117">名前、<xref:System.Windows.Controls.Grid>要素`grid1`します。</span><span class="sxs-lookup"><span data-stu-id="cf05a-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="cf05a-118">デザイン ビューまたは XAML ビューで、選択、<xref:System.Windows.Window>要素。</span><span class="sxs-lookup"><span data-stu-id="cf05a-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="cf05a-119">[プロパティ] ウィンドウ、**イベント**タブ。</span><span class="sxs-lookup"><span data-stu-id="cf05a-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="cf05a-120">ダブルクリックして、<xref:System.Windows.FrameworkElement.Loaded>イベント。</span><span class="sxs-lookup"><span data-stu-id="cf05a-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="cf05a-121">処理するために次のコードを挿入、<xref:System.Windows.FrameworkElement.Loaded>イベント。</span><span class="sxs-lookup"><span data-stu-id="cf05a-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="cf05a-122">次のコードを追加、ファイルの上部にある`Imports`または`using`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="cf05a-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="cf05a-123">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="cf05a-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf05a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf05a-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="cf05a-125">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="cf05a-125">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="cf05a-126">チュートリアル: XAML を使用して、WPF での Windows フォーム コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="cf05a-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="cf05a-127">チュートリアル: WPF で Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="cf05a-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="cf05a-128">チュートリアル: Windows フォームでの WPF 複合コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="cf05a-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="cf05a-129">Windows フォーム コントロールおよび同等の WPF コントロール</span><span class="sxs-lookup"><span data-stu-id="cf05a-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="cf05a-130">WPF のサンプル Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="cf05a-130">Hosting a Windows Forms Control in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160057)
