---
title: 'チュートリアル: WPF での XAML を使用した Windows フォーム コントロールのホスト'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 71c11a377d49a5e010ab9f33547e0ef63e2c5eaf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605462"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="6dd87-102">チュートリアル: WPF での XAML を使用した Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="6dd87-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="6dd87-103">豊富な機能セットには、多くのコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="6dd87-104">ただしを使用する可能性がありますも[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]のコントロールに対して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ページ。</span><span class="sxs-lookup"><span data-stu-id="6dd87-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="6dd87-105">たとえば、既存のかなりの投資を必要に応じて[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロール、またはする必要があります、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]独自の機能を提供するコントロール。</span><span class="sxs-lookup"><span data-stu-id="6dd87-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="6dd87-106">このチュートリアルは、Windows フォームをホストする方法を示します<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>の control 権限、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]を使用してページ[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="6dd87-107">このチュートリアルで示すタスクの完全なコード一覧については、次を参照してください。[を使用して XAML サンプルで WPF での Windows フォーム コントロールをホストしている](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="6dd87-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6dd87-108">Prerequisites</span></span>  

<span data-ttu-id="6dd87-109">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="6dd87-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="6dd87-110">Windows フォームのコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="6dd87-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="6dd87-111">MaskedTextBox コントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="6dd87-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="6dd87-112">という名前の WPF アプリケーション プロジェクトを作成する`HostingWfInWpfWithXaml`します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="6dd87-113">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="6dd87-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="6dd87-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="6dd87-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="6dd87-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="6dd87-116">MainWindow.xaml を開き、[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4. <span data-ttu-id="6dd87-117"><xref:System.Windows.Window>要素では、次の名前空間マッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="6dd87-118">`wf`名前空間のマッピングは、Windows フォーム コントロールを格納するアセンブリへの参照を確立します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="6dd87-119"><xref:System.Windows.Controls.Grid>要素は、次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="6dd87-120"><xref:System.Windows.Forms.MaskedTextBox>コントロールの子として作成されますが、<xref:System.Windows.Forms.Integration.WindowsFormsHost>コントロール。</span><span class="sxs-lookup"><span data-stu-id="6dd87-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="6dd87-121">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6dd87-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd87-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6dd87-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6dd87-123">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="6dd87-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6dd87-124">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="6dd87-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="6dd87-125">チュートリアル: WPF で Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="6dd87-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="6dd87-126">チュートリアル: Windows フォームでの WPF 複合コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="6dd87-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="6dd87-127">Windows フォーム コントロールおよび同等の WPF コントロール</span><span class="sxs-lookup"><span data-stu-id="6dd87-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="6dd87-128">XAML のサンプルを使用して、WPF での Windows フォーム コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="6dd87-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
