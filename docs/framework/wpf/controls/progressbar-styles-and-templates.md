---
title: ProgressBar のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: f948cf2b4f4cd2a4cb73b0cd5fc754240c850b83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099418"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="30482-102">ProgressBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="30482-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="30482-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.ProgressBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="30482-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="30482-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="30482-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="30482-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30482-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="30482-106">ProgressBar のパーツ</span><span class="sxs-lookup"><span data-stu-id="30482-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="30482-107">次の表に、名前付きパーツ、<xref:System.Windows.Controls.ProgressBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="30482-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="30482-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="30482-108">Part</span></span>|<span data-ttu-id="30482-109">型</span><span class="sxs-lookup"><span data-stu-id="30482-109">Type</span></span>|<span data-ttu-id="30482-110">説明</span><span class="sxs-lookup"><span data-stu-id="30482-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="30482-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="30482-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="30482-112">進行状況を示すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="30482-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="30482-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="30482-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="30482-114">進行状況インジケーターのパスを定義するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="30482-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="30482-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="30482-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="30482-116">進行状況バーを embellishes するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="30482-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="30482-117">ProgressBar の状態</span><span class="sxs-lookup"><span data-stu-id="30482-117">ProgressBar States</span></span>  
 <span data-ttu-id="30482-118">次の表のビジュアルの状態、<xref:System.Windows.Controls.ProgressBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="30482-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="30482-119">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="30482-119">VisualState Name</span></span>|<span data-ttu-id="30482-120">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="30482-120">VisualStateGroup Name</span></span>|<span data-ttu-id="30482-121">説明</span><span class="sxs-lookup"><span data-stu-id="30482-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="30482-122">不確定です。</span><span class="sxs-lookup"><span data-stu-id="30482-122">Determinate</span></span>|<span data-ttu-id="30482-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="30482-123">CommonStates</span></span>|<span data-ttu-id="30482-124"><xref:System.Windows.Controls.ProgressBar> に基づいて進行状況を報告、<xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="30482-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="30482-125">不確定です</span><span class="sxs-lookup"><span data-stu-id="30482-125">Indeterminate</span></span>|<span data-ttu-id="30482-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="30482-126">CommonStates</span></span>|<span data-ttu-id="30482-127"><xref:System.Windows.Controls.ProgressBar> 繰り返しのパターンを持つ汎用の進行状況を報告します。</span><span class="sxs-lookup"><span data-stu-id="30482-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="30482-128">有効</span><span class="sxs-lookup"><span data-stu-id="30482-128">Valid</span></span>|<span data-ttu-id="30482-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="30482-129">ValidationStates</span></span>|<span data-ttu-id="30482-130">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="30482-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="30482-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="30482-131">InvalidFocused</span></span>|<span data-ttu-id="30482-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="30482-132">ValidationStates</span></span>|<span data-ttu-id="30482-133"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="30482-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="30482-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="30482-134">InvalidUnfocused</span></span>|<span data-ttu-id="30482-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="30482-135">ValidationStates</span></span>|<span data-ttu-id="30482-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="30482-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="30482-137">ProgressBar の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="30482-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="30482-138">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.ProgressBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="30482-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="30482-139">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="30482-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="30482-140">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30482-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30482-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="30482-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="30482-142">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="30482-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="30482-143">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="30482-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="30482-144">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="30482-144">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="30482-145">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="30482-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
