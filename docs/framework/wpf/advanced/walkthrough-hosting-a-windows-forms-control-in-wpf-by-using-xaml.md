---
title: XAML を使用した WPF での Windows フォームコントロールのホスト
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 2c5764ac2dfd9f5747087cc76e3971c002f12b90
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794200"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="25de5-102">チュートリアル: WPF での、XAML を使用した Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="25de5-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="25de5-103">には、豊富な機能セットを備えたさまざまなコントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="25de5-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="25de5-104">ただし、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] のページで Windows フォームコントロールを使用することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="25de5-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="25de5-105">たとえば、既存の Windows フォームコントロールに多大な投資を行っている場合や、独自の機能を提供する Windows フォームコントロールがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="25de5-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="25de5-106">このチュートリアルでは、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を使用して [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ページで Windows フォーム <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> コントロールをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="25de5-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="25de5-107">このチュートリアルで示されているタスクの完全なコード一覧については、「 [XAML を使用した WPF での Windows フォームコントロールのホスト](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25de5-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="25de5-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="25de5-108">Prerequisites</span></span>  

<span data-ttu-id="25de5-109">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="25de5-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="25de5-110">Windows フォームコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="25de5-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="25de5-111">MaskedTextBox コントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="25de5-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="25de5-112">`HostingWfInWpfWithXaml`という名前の WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="25de5-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="25de5-113">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="25de5-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="25de5-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="25de5-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="25de5-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="25de5-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="25de5-116">WPF デザイナーで Mainwindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="25de5-116">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
4. <span data-ttu-id="25de5-117"><xref:System.Windows.Window> 要素に、次の名前空間マッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="25de5-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="25de5-118">`wf` 名前空間マッピングは、Windows フォームコントロールを含むアセンブリへの参照を確立します。</span><span class="sxs-lookup"><span data-stu-id="25de5-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="25de5-119"><xref:System.Windows.Controls.Grid> 要素で、次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="25de5-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="25de5-120"><xref:System.Windows.Forms.MaskedTextBox> コントロールは、<xref:System.Windows.Forms.Integration.WindowsFormsHost> コントロールの子として作成されます。</span><span class="sxs-lookup"><span data-stu-id="25de5-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="25de5-121">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="25de5-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25de5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="25de5-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="25de5-123">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="25de5-123">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="25de5-124">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="25de5-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="25de5-125">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="25de5-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="25de5-126">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="25de5-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="25de5-127">Windows フォーム コントロールおよび同等の WPF コントロール</span><span class="sxs-lookup"><span data-stu-id="25de5-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="25de5-128">XAML サンプルを使用した WPF での Windows フォームコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="25de5-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
