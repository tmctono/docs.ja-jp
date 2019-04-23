---
title: NavigationWindow のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 32d8aac99d40693e66c7b52a6c7d2c116d2f3baf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225808"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="b0e38-102">NavigationWindow のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b0e38-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="b0e38-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Navigation.NavigationWindow>コントロール。</span><span class="sxs-lookup"><span data-stu-id="b0e38-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="b0e38-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="b0e38-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b0e38-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0e38-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="b0e38-106">NavigationWindow のパーツ</span><span class="sxs-lookup"><span data-stu-id="b0e38-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="b0e38-107">次の表に、名前付きパーツ、<xref:System.Windows.Navigation.NavigationWindow>コントロール。</span><span class="sxs-lookup"><span data-stu-id="b0e38-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="b0e38-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="b0e38-108">Part</span></span>|<span data-ttu-id="b0e38-109">型</span><span class="sxs-lookup"><span data-stu-id="b0e38-109">Type</span></span>|<span data-ttu-id="b0e38-110">説明</span><span class="sxs-lookup"><span data-stu-id="b0e38-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b0e38-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="b0e38-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="b0e38-112">コンテンツの領域。</span><span class="sxs-lookup"><span data-stu-id="b0e38-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="b0e38-113">NavigationWindow の状態</span><span class="sxs-lookup"><span data-stu-id="b0e38-113">NavigationWindow States</span></span>  
 <span data-ttu-id="b0e38-114">次の表のビジュアルの状態、<xref:System.Windows.Navigation.NavigationWindow>コントロール。</span><span class="sxs-lookup"><span data-stu-id="b0e38-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="b0e38-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="b0e38-115">VisualState Name</span></span>|<span data-ttu-id="b0e38-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="b0e38-116">VisualStateGroup Name</span></span>|<span data-ttu-id="b0e38-117">説明</span><span class="sxs-lookup"><span data-stu-id="b0e38-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b0e38-118">有効</span><span class="sxs-lookup"><span data-stu-id="b0e38-118">Valid</span></span>|<span data-ttu-id="b0e38-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b0e38-119">ValidationStates</span></span>|<span data-ttu-id="b0e38-120">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="b0e38-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b0e38-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b0e38-121">InvalidFocused</span></span>|<span data-ttu-id="b0e38-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b0e38-122">ValidationStates</span></span>|<span data-ttu-id="b0e38-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="b0e38-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b0e38-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b0e38-124">InvalidUnfocused</span></span>|<span data-ttu-id="b0e38-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b0e38-125">ValidationStates</span></span>|<span data-ttu-id="b0e38-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="b0e38-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="b0e38-127">NavigationWindow ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="b0e38-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="b0e38-128">この例には、すべての要素で定義されているが含まれますが、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Navigation.NavigationWindow>既定では、特定の値が考えることが例として。</span><span class="sxs-lookup"><span data-stu-id="b0e38-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="b0e38-129">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0e38-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b0e38-130">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0e38-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e38-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0e38-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b0e38-132">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b0e38-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b0e38-133">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b0e38-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b0e38-134">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b0e38-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="b0e38-135">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b0e38-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
