---
title: XAML を使用して WPF で Windows フォーム コントロールをホストする
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 99c077801a26043e17e0d51ecc0a97b9608784c0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095061"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="a1889-102">チュートリアル: WPF での XAML を使用した Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="a1889-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="a1889-103">には、豊富な機能セットを備えた多くのコントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a1889-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="a1889-104">ただし、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ページで Windows フォーム コントロールを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1889-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="a1889-105">たとえば、既存の Windows フォーム コントロールに多大な投資をしている場合や、独自の機能を提供する Windows フォーム コントロールを使用している場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1889-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="a1889-106">このチュートリアルでは、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] を使用して [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ページで Windows フォーム <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> コントロールをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1889-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="a1889-107">このチュートリアルで示されているタスクの完全なコード一覧については、[WPF での XAML を使用した Windows フォーム コントロールのホストのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1889-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="a1889-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a1889-108">Prerequisites</span></span>  

<span data-ttu-id="a1889-109">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="a1889-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="a1889-110">Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="a1889-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="a1889-111">MaskedTextBox コントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="a1889-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="a1889-112">`HostingWfInWpfWithXaml` という名前の WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1889-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="a1889-113">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="a1889-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="a1889-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="a1889-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="a1889-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="a1889-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="a1889-116">WPF デザイナーで MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="a1889-116">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
4. <span data-ttu-id="a1889-117"><xref:System.Windows.Window> 要素に、次の名前空間マッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="a1889-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="a1889-118">`wf` 名前空間マッピングを使用して、Windows フォーム コントロールを含むアセンブリへの参照を確立します。</span><span class="sxs-lookup"><span data-stu-id="a1889-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="a1889-119"><xref:System.Windows.Controls.Grid> 要素に、次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="a1889-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="a1889-120"><xref:System.Windows.Forms.MaskedTextBox> コントロールは、<xref:System.Windows.Forms.Integration.WindowsFormsHost> コントロールの子として作成されます。</span><span class="sxs-lookup"><span data-stu-id="a1889-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="a1889-121">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="a1889-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1889-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1889-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a1889-123">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="a1889-123">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a1889-124">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="a1889-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="a1889-125">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="a1889-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="a1889-126">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="a1889-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="a1889-127">Windows フォーム コントロールおよび同等の WPF コントロール</span><span class="sxs-lookup"><span data-stu-id="a1889-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="a1889-128">WPF での XAML を使用した Windows フォーム コントロールのホストのサンプル</span><span class="sxs-lookup"><span data-stu-id="a1889-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)
