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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770657"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="01cf4-102">NavigationWindow のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="01cf4-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="01cf4-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Navigation.NavigationWindow>コントロール。</span><span class="sxs-lookup"><span data-stu-id="01cf4-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="01cf4-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="01cf4-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="01cf4-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01cf4-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="01cf4-106">NavigationWindow のパーツ</span><span class="sxs-lookup"><span data-stu-id="01cf4-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="01cf4-107">次の表に、名前付きパーツ、<xref:System.Windows.Navigation.NavigationWindow>コントロール。</span><span class="sxs-lookup"><span data-stu-id="01cf4-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="01cf4-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="01cf4-108">Part</span></span>|<span data-ttu-id="01cf4-109">型</span><span class="sxs-lookup"><span data-stu-id="01cf4-109">Type</span></span>|<span data-ttu-id="01cf4-110">説明</span><span class="sxs-lookup"><span data-stu-id="01cf4-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="01cf4-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="01cf4-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="01cf4-112">コンテンツの領域。</span><span class="sxs-lookup"><span data-stu-id="01cf4-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="01cf4-113">NavigationWindow の状態</span><span class="sxs-lookup"><span data-stu-id="01cf4-113">NavigationWindow States</span></span>  
 <span data-ttu-id="01cf4-114">次の表のビジュアルの状態、<xref:System.Windows.Navigation.NavigationWindow>コントロール。</span><span class="sxs-lookup"><span data-stu-id="01cf4-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="01cf4-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="01cf4-115">VisualState Name</span></span>|<span data-ttu-id="01cf4-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="01cf4-116">VisualStateGroup Name</span></span>|<span data-ttu-id="01cf4-117">説明</span><span class="sxs-lookup"><span data-stu-id="01cf4-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="01cf4-118">有効</span><span class="sxs-lookup"><span data-stu-id="01cf4-118">Valid</span></span>|<span data-ttu-id="01cf4-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="01cf4-119">ValidationStates</span></span>|<span data-ttu-id="01cf4-120">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="01cf4-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="01cf4-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="01cf4-121">InvalidFocused</span></span>|<span data-ttu-id="01cf4-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="01cf4-122">ValidationStates</span></span>|<span data-ttu-id="01cf4-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="01cf4-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="01cf4-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="01cf4-124">InvalidUnfocused</span></span>|<span data-ttu-id="01cf4-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="01cf4-125">ValidationStates</span></span>|<span data-ttu-id="01cf4-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="01cf4-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="01cf4-127">NavigationWindow ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="01cf4-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="01cf4-128">この例には、すべての要素で定義されているが含まれますが、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Navigation.NavigationWindow>既定では、特定の値が考えることが例として。</span><span class="sxs-lookup"><span data-stu-id="01cf4-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="01cf4-129">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="01cf4-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="01cf4-130">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01cf4-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01cf4-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="01cf4-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="01cf4-132">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="01cf4-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="01cf4-133">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="01cf4-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="01cf4-134">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="01cf4-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="01cf4-135">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="01cf4-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
