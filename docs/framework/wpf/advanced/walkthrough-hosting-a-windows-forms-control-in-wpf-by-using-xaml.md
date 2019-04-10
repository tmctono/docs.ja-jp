---
title: 'チュートリアル: WPF での XAML を使用した Windows フォーム コントロールのホスト'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 61a234a679d9937cb38a753a3d73f2ecc9ec891a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190368"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="514c7-102">チュートリアル: WPF での XAML を使用した Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="514c7-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="514c7-103">豊富な機能セットには、多くのコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="514c7-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="514c7-104">ただしを使用する可能性がありますも[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]のコントロールに対して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ページ。</span><span class="sxs-lookup"><span data-stu-id="514c7-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="514c7-105">たとえば、既存のかなりの投資を必要に応じて[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロール、またはする必要があります、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]独自の機能を提供するコントロール。</span><span class="sxs-lookup"><span data-stu-id="514c7-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="514c7-106">このチュートリアルは、Windows フォームをホストする方法を示します<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>の control 権限、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]を使用してページ[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="514c7-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="514c7-107">このチュートリアルで示すタスクの完全なコード一覧については、次を参照してください。[を使用して XAML サンプルで WPF での Windows フォーム コントロールをホストしている](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)します。</span><span class="sxs-lookup"><span data-stu-id="514c7-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="514c7-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="514c7-108">Prerequisites</span></span>  

<span data-ttu-id="514c7-109">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="514c7-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="514c7-110">Windows フォームのコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="514c7-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="514c7-111">MaskedTextBox コントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="514c7-111">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="514c7-112">という名前の WPF アプリケーション プロジェクトを作成する`HostingWfInWpfWithXaml`します。</span><span class="sxs-lookup"><span data-stu-id="514c7-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2.  <span data-ttu-id="514c7-113">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="514c7-113">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="514c7-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="514c7-114">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="514c7-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="514c7-115">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="514c7-116">MainWindow.xaml を開き、[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="514c7-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="514c7-117"><xref:System.Windows.Window>要素では、次の名前空間マッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="514c7-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="514c7-118">`wf`名前空間のマッピングは、Windows フォーム コントロールを格納するアセンブリへの参照を確立します。</span><span class="sxs-lookup"><span data-stu-id="514c7-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="514c7-119"><xref:System.Windows.Controls.Grid>要素は、次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="514c7-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="514c7-120"><xref:System.Windows.Forms.MaskedTextBox>コントロールの子として作成されますが、<xref:System.Windows.Forms.Integration.WindowsFormsHost>コントロール。</span><span class="sxs-lookup"><span data-stu-id="514c7-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  <span data-ttu-id="514c7-121">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="514c7-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="514c7-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="514c7-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="514c7-123">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="514c7-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="514c7-124">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="514c7-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="514c7-125">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="514c7-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="514c7-126">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="514c7-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="514c7-127">Windows フォーム コントロールおよび同等の WPF コントロール</span><span class="sxs-lookup"><span data-stu-id="514c7-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="514c7-128">XAML のサンプルを使用して、WPF での Windows フォーム コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="514c7-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
